MetricTank
=================

Cassandra-backed, metrics2.0 based, multi-tenant timeseries database for Graphite and friends

generating metrictank rpm:

golang > 1.10 is needed

```
# yum install ruby-devel gcc make rpm-build rubygems git
# gem install --no-ri --no-rdoc fpm

go get github.com/grafana/metrictank/...

cd $GOPATH/src/github.com/grafana/metrictank
make bin

mkdir -p /tmp/metrictank

cp build/* /tmp/metritank/bin/
cp scripts/config/schema-*l /tmp/opt/metritank/conf/
cp scripts/config/metrictank-package.ini /tmp/metritank/conf/metrictank.ini.sample

#  fpm -s dir -t rpm -v $(git describe --long --abbrev=7) -n metrictank \
--description "metrictank, the gorilla-inspired timeseries database backend for graphite" \
--config-files /opt/metrictank/conf --prefix /opt/metrictank -C /tmp/metritank .

```


Role Variables
--------------



Example Playbook
----------------


License
-------

MIT

Author Information
------------------

Alexandre Biancalana (@biancalana)
