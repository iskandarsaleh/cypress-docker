DOCKERIMGNAME=cypresstestdocker
DOCKERRUNCMD=docker-compose run --rm $(DOCKERIMGNAME)
CYPRESSRUNCMD=npx cypress run
CYPRESSGUICMD=npx cypress open

test:
	$(CYPRESSRUNCMD)
	
test-gui:
	$(CYPRESSGUICMD)

test-local:
	$(CYPRESSRUNCMD) --env configFile=development

test-qa:
	$(CYPRESSRUNCMD) --env configFile=qa

test-staging:
	$(CYPRESSRUNCMD) --env configFile=staging

test-production:
	$(CYPRESSRUNCMD) --env configFile=production

test-local-gui:
	$(CYPRESSGUICMD) --env configFile=development

test-qa-gui:
	$(CYPRESSGUICMD) --env configFile=qa

test-record:
	$(CYPRESSRUNCMD) --record

combine-reports:
	node scripts/generate-reports.js

slack-alert:
	node scripts/slack/slack-alert.js

docker-build:
	docker build . -t $(DOCKERIMGNAME)

docker-bash:
	$(DOCKERRUNCMD) /bin/bash

docker-test:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD)
	
docker-test-local:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD) --env configFile=development

docker-test-qa:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD) --env configFile=qa

docker-test-staging:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD) --env configFile=staging

docker-test-production:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD) --env configFile=production

docker-test-record:
	$(DOCKERRUNCMD) $(CYPRESSRUNCMD) --record