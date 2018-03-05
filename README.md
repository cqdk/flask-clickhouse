# Flask-ClickHouse

ClickHouse support for Flask applications

## Quickstart

    from flask import Flask
    from flask_clickhouse import ClickHouse

    app = Flask(__name__)
    ch = ClickHouse(app)

    @app.route('/')
    def index():
        data = ch.execute('SELECT * FROM my_table')
        return render_template('index.html', data=data)

## More Info

* [ClickHouse Driver](https://github.com/mymarilyn/clickhouse-driver)
* [Flask Documentation](http://flask.pocoo.org/docs/)
