A [Dash example](https://plot.ly/dash/getting-started) deployed to AWS Lambda and API Gateway using [Zappa](https://github.com/Miserlou/Zappa)

Example at [https://dash.struce.com]('https://dash.struce.com/])

Modify the zappa_settings.json so it points to your bucket

```bash
virtualenv -p ($which python3) env
source env/bin/activate
pip install -r requirements.txt
zappa deploy
```

Status: follow the progress on this issue: [https://github.com/plotly/dash/issues/22](https://github.com/plotly/dash/issues/22)


Notes:
1. dash.ly should not be installed otherwise the deploy will fail
2. Without custom domain, you will need to do the following:
```
if __name__ == '__main__':
    app.run_server(debug=True)
else:
    app.config['requests_pathname_prefix'] = '/dev' + app.config['requests_pathname_prefix']
```
