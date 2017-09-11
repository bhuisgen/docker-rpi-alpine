IMAGE = bhuisgen/rpi-alpine-hostapd

clean-local:
	docker rmi $(CLEAN_OPTIONS) $(IMAGE):$(TAG) || true

build-local:
	docker build $(BUILD_OPTIONS) -t $(IMAGE):$(TAG) .

pull-local:
	docker pull $(PULL_OPTIONS) $(IMAGE):$(TAG)

push-local: build-local
	docker push $(PUSH_OPTIONS) $(IMAGE):$(TAG)
