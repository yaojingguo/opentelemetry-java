# OpenTelemetry
[![Gitter chat][gitter-image]][gitter-url]
![Continuous Build](https://github.com/open-telemetry/opentelemetry-java/workflows/Continuous%20Build/badge.svg)
[![Coverage Status][codecov-image]][codecov-url]
[![Maven Central][maven-image]][maven-url]

We hold regular meetings. See details at [community page](https://github.com/open-telemetry/community#java-sdk).

## Overview

OpenTelemetry is the merging of OpenCensus and OpenTracing into one
project.

This project contains the following top level components:

* [OpenTelemetry API](api/):
  * [tracing api](api/src/main/java/io/opentelemetry/api/trace/) includes `Tracer`, `Span` and `SpanContext`.
  * [baggage api](/api/src/main/java/io/opentelemetry/api/baggage) defines a collection of entries in the form of key-value pairs of data that can be propagated to provide contextual information.
  * [metrics api](api/src/main/java/io/opentelemetry/api/metrics/).
* [extensions](extensions/) define additional API extensions, which are not part of the core API.
* [sdk](sdk/) define the reference implementation complying to the OpenTelemetry API.
* [sdk-extensions](sdk-extensions/) define additional SDK extensions, which are not part of the core SDK.
* [OpenTracing shim](opentracing-shim/) defines a bridge layer from OpenTracing to the OpenTelemetry API.
* [examples](examples/) on how to use the APIs, SDK, and standard exporters.

We would love to hear from the larger community: please provide feedback proactively.

### Note about extensions

Both API and SDK extensions consist of various additional components which are excluded from the core artifacts
to keep them from growing too large.
We still aim to provide the same level of quality and guarantee for them as for the core components.
Please don't hesitate to use them if you find them useful. 

## Project setup and contribute

Please refer to the [contribution guide](CONTRIBUTING.md)
on how to setup and contribute!

## Quick Start

Please refer to the [quick start guide](QUICKSTART.md) on how use the OpenTelemetry API.

## Published Releases

Published releases are available on maven central.

### Maven

```xml
  <dependencies>
    <dependency>
      <groupId>io.opentelemetry</groupId>
      <artifactId>opentelemetry-api</artifactId>
      <version>0.10.0</version>
    </dependency>
  </dependencies>
```

### Gradle

```groovy
dependencies {
	implementation('io.opentelemetry:opentelemetry-api:0.10.0')
}
```

## Snapshots

Snapshots based out the `master` branch are available for `opentelemetry-api`, `opentelemetry-sdk` and the rest of the artifacts:

### Maven

```xml
  <repositories>
    <repository>
      <id>oss.sonatype.org-snapshot</id>
      <url>https://oss.jfrog.org/artifactory/oss-snapshot-local</url>
    </repository>
  </repositories>

  <dependencies>
    <dependency>
      <groupId>io.opentelemetry</groupId>
      <artifactId>opentelemetry-api</artifactId>
      <version>0.11.0-SNAPSHOT</version>
    </dependency>
  </dependencies>
```

### Gradle

```groovy
repositories {
	maven { url 'https://oss.jfrog.org/artifactory/oss-snapshot-local' }
}

dependencies {
	implementation('io.opentelemetry:opentelemetry-api:0.11.0-SNAPSHOT')
}
```

Libraries will usually only need `opentelemetry-api`, while applications
may want to use `opentelemetry-sdk`.

## Releases

OpenTelemetry Java is under active development. Releases aren't guaranteed
to conform to a specific version of the specification. Future releases will
not attempt to maintain backwards compatibility with previous releases.

Check out information about the [latest release](https://github.com/open-telemetry/opentelemetry-java/releases).

This is a **current** feature status list:

| Component                   | Version |
| --------------------------- | ------- |
| Tracing API                 | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Tracing SDK                 | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Metrics API                 | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Metrics SDK                 | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| OTLP Exporter               | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Jaeger Trace Exporter       | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Zipkin Trace Exporter       | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Prometheus Metrics Exporter | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| Context Propagation         | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| OpenTracing Bridge          | v<!--VERSION_STABLE-->0.10.0<!--/VERSION_STABLE-->  |
| OpenCensus Bridge           | N/A     |

See the project [milestones](https://github.com/open-telemetry/opentelemetry-java/milestones)
for details on upcoming releases. The dates and features described in issues
and milestones are estimates, and subject to change.

### Summary

We plan to merge projects and pave the path for future improvements as a unified
community of tracing vendors, users and library authors who wants apps be
managed better. We are open to feedback and suggestions from all of you!

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

Approvers ([@open-telemetry/java-approvers](https://github.com/orgs/open-telemetry/teams/java-approvers)):

- [Armin Ruech](https://github.com/arminru), Dynatrace
- [Pavol Loffay](https://github.com/pavolloffay), Traceable.ai
- [Tyler Benson](https://github.com/tylerbenson), DataDog
- [Giovanni Liva](https://github.com/thisthat), Dynatrace

*Find more about the approver role in [community repository](https://github.com/open-telemetry/community/blob/master/community-membership.md#approver).*

Maintainers ([@open-telemetry/java-maintainers](https://github.com/orgs/open-telemetry/teams/java-maintainers)):

- [Bogdan Drutu](https://github.com/BogdanDrutu), Splunk
- [Carlos Alberto](https://github.com/carlosalberto), LightStep
- [John Watson](https://github.com/jkwatson), Splunk
- [Anuraag Agrawal](https://github.com/anuraaga), AWS

*Find more about the maintainer role in [community repository](https://github.com/open-telemetry/community/blob/master/community-membership.md#maintainer).*

### Thanks to all the people who have contributed

[![contributors](https://contributors-img.web.app/image?repo=open-telemetry/opentelemetry-java)](https://github.com/open-telemetry/opentelemetry-java/graphs/contributors)

[circleci-image]: https://circleci.com/gh/open-telemetry/opentelemetry-java.svg?style=svg 
[circleci-url]: https://circleci.com/gh/open-telemetry/opentelemetry-java
[gitter-image]: https://badges.gitter.im/open-telemetry/opentelemetry-java.svg 
[gitter-url]: https://gitter.im/open-telemetry/opentelemetry-java?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge
[codecov-image]: https://codecov.io/gh/open-telemetry/opentelemetry-java/branch/master/graph/badge.svg
[codecov-url]: https://codecov.io/gh/open-telemetry/opentelemetry-java/branch/master/
[maven-image]: https://maven-badges.herokuapp.com/maven-central/io.opentelemetry/opentelemetry-api/badge.svg
[maven-url]: https://maven-badges.herokuapp.com/maven-central/io.opentelemetry/opentelemetry-api
