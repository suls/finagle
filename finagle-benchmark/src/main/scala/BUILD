scala_library(name='scala',
  dependencies=[
    '3rdparty/jvm/com/google/caliper',
    '3rdparty/jvm/org/openjdk/jmh:jmh-core',
    '3rdparty/jvm/org/scala-lang:scala-library',
    'finagle/finagle-benchmark/src/main/thrift:thrift-scala',
    'finagle/finagle-commons-stats',
    'finagle/finagle-core',
    'finagle/finagle-exp',
    'finagle/finagle-memcached',
    'finagle/finagle-ostrich4',
    'finagle/finagle-stats',
    'finagle/finagle-thriftmux',
    'finagle/finagle-zipkin',
  ],
  sources=rglobs('*.scala')
)

# depend on this for resources/real_latencies.data
jar_library(name='metrics-samples',
  jars = [
    jar(org='com.twitter.common', name='metrics-data-sample', rev='0.0.1'),
  ],
)

jvm_binary(
  name='p2csim',
  main='com.twitter.finagle.loadbalancer.Simulation',
  dependencies=[':scala', ':metrics-samples']
)

jvm_binary(
  name='hello-server',
  main='com.twitter.finagle.thrift.HelloServer',
  dependencies=[':scala']
)
