
install:
	-rbenv install jruby-9.2.8.0
	rbenv local jruby-9.2.8.0
	gem install bundle
	bundle install
start-server:
	bundle exec norikra start
#submit-query:
#	bundle exec norikra-client query add \
#		test_query "\
#		  SELECT \
#		    category, \
#		    score, \
#		    count(*) AS count \
#		  FROM app_log.win:time_batch(20 sec) \
#		  WHERE score > 0.5 \
#		  GROUP BY category \
#		"
submit-query:
	bundle exec norikra-client query add test_query1 "SELECT avg(cost),max(cost),min(cost),count(*) AS count FROM app_log.win:time_batch(1 min)"
	bundle exec norikra-client query add test_query2 "SELECT category,avg(cost),max(cost),min(cost),avg(score),count(*) AS count FROM app_log.win:time_batch(1 min) GROUP BY category"
delete-query:
	bundle exec norikra-client query remove test_query1
	bundle exec norikra-client query remove test_query2
check-query:
	bundle exec norikra-client query list
fetch1:
	bundle exec norikra-client event fetch test_query1
	bundle exec norikra-client event fetch test_query2
fetch-all:
	bundle exec norikra-client event sweep
