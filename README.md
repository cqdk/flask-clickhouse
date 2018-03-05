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

## Several database connections

    app = Flask(__name__)
    ch1 = ClickHouse(app)
    ch2 = ClickHouse(app, config_prefix='CLICKHOUSE2')
    ch3 = ClickHouse(app, config_prefix='CLICKHOUSE3')

## Config options

    The app is configured according to the configuration variables
    ``PREFIX_HOST``, ``PREFIX_PORT``, ``PREFIX_DATABASE``,
    ``PREFIX_USER``, ``PREFIX_PASSWORD``, ``PREFIX_CLIENT_NAME``,
    ``PREFIX_CONNECT_TIMEOUT``, ``PREFIX_SEND_RECEIVE_TIMEOUT``,
    ``PREFIX_SYNC_REQUEST_TIMEOUT``, ``PREFIX_COMPRESS_BLOCK_SIZE``,
    ``PREFIX_COMPRESSION``, ``PREFIX_SECURE``, ``PREFIX_VERIFY``,
    ``PREFIX_SSL_VERSION``, ``PREFIX_CA_CERTS`` and  ``PREFIX_CIPHERS``,
    where "PREFIX" defaults to "CLICKHOUSE".


## More Info

* [ClickHouse Driver](https://github.com/mymarilyn/clickhouse-driver)
* [Flask Documentation](http://flask.pocoo.org/docs/)
