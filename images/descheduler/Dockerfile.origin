FROM registry.svc.ci.openshift.org/openshift/release:golang-1.10 AS builder
WORKDIR /go/src/github.com/kubernetes-incubator/descheduler
COPY . .
RUN make build

FROM registry.svc.ci.openshift.org/openshift/origin-v4.0:base
COPY --from=builder /go/src/github.com/kubernetes-incubator/descheduler/_output/local/bin/linux/amd64/descheduler /usr/bin/
CMD ["/usr/bin/descheduler"]
