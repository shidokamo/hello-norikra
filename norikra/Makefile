
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
	bundle exec norikra-client query add test_query "SELECT category,score,count(*) AS c FROM app_log.win:time_batch(20 sec) WHERE score > 0.5 GROUP BY category"
submit-query2:
	bundle exec norikra-client query add test_query2 "SELECT category,cost,count(*) AS c FROM app_log.win:time_batch(1 min) GROUP BY category"
submit-query3:
	bundle exec norikra-client query add test_query3 "SELECT category,cost,count(*) AS c FROM app_log.win:time_batch(21 sec) GROUP BY category"
check-query:
	bundle exec norikra-client query list
fetch:
	bundle exec norikra-client event fetch test-query2
