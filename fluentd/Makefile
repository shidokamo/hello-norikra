LOG_INTERVAL = 1
LOG_DIR := .
export LOG_INTERVAL LOG_DIR

default:fluentd

install:
	pipenv install
	bundle install --path=./vendor/bundle
log:
	pipenv run python -u code/app.py
clean:
	-rm -rf *.log*
	-rm -rf country
fluentd:
	bundle exec fluentd -c fluent.conf


