IMAGE = bhuisgen/rpi-alpine-zabbix-agent

clean-local:
	docker rmi $(CLEAN_OPTIONS) $(IMAGE):$(TAG) || true

build-local:
	docker build $(BUILD_OPTIONS) -t $(IMAGE):$(TAG) .

pull-local:
	docker pull $(IMAGE):$(TAG) $(PULL_OPTIONS)

push-local: build-local
	docker push $(PUSH_OPTIONS) $(IMAGE):$(TAG)
