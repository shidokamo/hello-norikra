
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
submit-query1:
	bundle exec norikra-client query add test_query1 "SELECT category,avg(cost),count(*) AS c FROM app_log.win:time_batch(20 sec) GROUP BY category"
#	bundle exec norikra-client query add test_query1 "SELECT category,avg(cost),min(cost),max(cost),count(*) AS c FROM app_log.win:time_batch(20 sec) GROUP BY category"
check-query:
	bundle exec norikra-client query list
fetch1:
	bundle exec norikra-client event fetch test-query1
