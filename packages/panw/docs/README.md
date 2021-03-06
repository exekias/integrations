# Palo Alto Network Integration

This integration is for Palo Alto Networks PAN-OS firewall monitoring logs received over Syslog or read from a file. It currently supports messages of Traffic and Threat types.

## Compatibility

This module has been tested with logs generated by devices running PAN-OS versions 7.1 to 9.0 but limited compatibility is expected for earlier versions.

The ingest-geoip Elasticsearch plugin is required to run this module.

## Logs

### PAN-OS

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.nat.ip | Client NAT ip address | ip |
| client.nat.port | Client NAT port | long |
| client.packets | Packets sent from the client to the server. | long |
| client.port | Port of the client. | long |
| client.user.name | Short name or login of the user. | keyword |
| container.id | Unique container id. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.address | Destination network address. | keyword |
| destination.as.number | Unique number allocated to the autonomous system. | long |
| destination.as.organization.name | Organization name. | keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.geo.city_name | City name. | keyword |
| destination.geo.continent_name | Name of the continent. | keyword |
| destination.geo.country_iso_code | Country ISO code. | keyword |
| destination.geo.country_name | Country name. | keyword |
| destination.geo.location | Longitude and latitude. | geo_point |
| destination.geo.name | User-defined description of a location. | keyword |
| destination.geo.region_iso_code | Region ISO code. | keyword |
| destination.geo.region_name | Region name. | keyword |
| destination.ip | IP address of the destination. | ip |
| destination.nat.ip | Destination NAT ip | ip |
| destination.nat.port | Destination NAT Port | long |
| destination.packets | Packets sent from the destination to the source. | long |
| destination.port | Port of the destination. | long |
| destination.user.email | User email address. | keyword |
| destination.user.name | Short name or login of the user. | keyword |
| ecs.version | ECS version this event conforms to. | keyword |
| error.message | Error message. | text |
| event.action | The action captured by the event. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.created | Time when the event was first read by an agent or by your pipeline. | date |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.ingested | Timestamp when an event arrived in the central data store. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.outcome | The outcome of the event. The lowest level categorization field in the hierarchy. | keyword |
| event.severity | Numeric severity of the event. | long |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.timezone | Event time zone. | keyword |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| file.type | File type (file, dir, or symlink). | keyword |
| hostname | Name of host parsed from syslog message. | keyword |
| http.request.referer | Referrer for this HTTP request. | keyword |
| input.type | Type of Filebeat input. | keyword |
| labels | Custom key/value pairs. | object |
| log.file.path | Path to the log file. | keyword |
| log.flags | Flags for the log file. | keyword |
| log.level | Log level of the log event. | keyword |
| log.offset | Offset of the entry in the log file. | long |
| log.original | Original log message with light interpretation only (encoding, newlines). | keyword |
| log.source.address | Source address from which the log event was read / sent from. | keyword |
| message | Log message optimized for viewing in a log viewer. | text |
| network.application | Application level protocol name. | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.packets | Total packets transferred in both directions. | long |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| observer.egress.interface.name | Interface name | keyword |
| observer.egress.zone | Observer Egress zone | keyword |
| observer.hostname | Hostname of the observer. | keyword |
| observer.ingress.interface.name | Interface name | keyword |
| observer.ingress.zone | Observer ingress zone | keyword |
| observer.product | The product name of the observer. | keyword |
| observer.serial_number | Observer serial number. | keyword |
| observer.type | The type of the observer the data is coming from. | keyword |
| observer.vendor | Vendor name of the observer. | keyword |
| panw.panos.action | Action taken for the session. | keyword |
| panw.panos.destination.interface | Destination interface for this session. | keyword |
| panw.panos.destination.nat.ip | Post-NAT destination IP. | ip |
| panw.panos.destination.nat.port | Post-NAT destination port. | long |
| panw.panos.destination.zone | Destination zone for this session. | keyword |
| panw.panos.endreason | The reason a session terminated. | keyword |
| panw.panos.file.hash | Binary hash for a threat file sent to be analyzed by the WildFire service. | keyword |
| panw.panos.flow_id | Internal numeric identifier for each session. | keyword |
| panw.panos.network.nat.community_id | Community ID flow-hash for the NAT 5-tuple. | keyword |
| panw.panos.network.pcap_id | Packet capture ID for a threat. | keyword |
| panw.panos.ruleset | Name of the rule that matched this session. | keyword |
| panw.panos.sequence_number | Log entry identifier that is incremented sequentially. Unique for each log type. | long |
| panw.panos.source.interface | Source interface for this session. | keyword |
| panw.panos.source.nat.ip | Post-NAT source IP. | ip |
| panw.panos.source.nat.port | Post-NAT source port. | long |
| panw.panos.source.zone | Source zone for this session. | keyword |
| panw.panos.sub_type | Specifies the sub type of the log | keyword |
| panw.panos.threat.id | Palo Alto Networks identifier for the threat. | keyword |
| panw.panos.threat.name | Palo Alto Networks name for the threat. | keyword |
| panw.panos.threat.resource | URL or file name for a threat. | keyword |
| panw.panos.type | Specifies the type of the log | keyword |
| panw.panos.url.category | For threat URLs, it's the URL category. For WildFire, the verdict on the file and is either 'malicious', 'grayware', or 'benign'. | keyword |
| related.hash | All the hashes seen on your event. | keyword |
| related.host | All the host identifiers seen on your event. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| related.user | All the user names seen on your event. | keyword |
| rule.name | Rule name | keyword |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.nat.ip | Server NAT ip | ip |
| server.nat.port | Server NAT port | long |
| server.packets | Packets sent from the server to the client. | long |
| server.port | Port of the server. | long |
| server.user.name | Short name or login of the user. | keyword |
| source.address | Source network address. | keyword |
| source.as.number | Unique number allocated to the autonomous system. | long |
| source.as.organization.name | Organization name. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.geo.city_name | City name. | keyword |
| source.geo.continent_name | Name of the continent. | keyword |
| source.geo.country_iso_code | Country ISO code. | keyword |
| source.geo.country_name | Country name. | keyword |
| source.geo.location | Longitude and latitude. | geo_point |
| source.geo.name | User-defined description of a location. | keyword |
| source.geo.region_iso_code | Region ISO code. | keyword |
| source.geo.region_name | Region name. | keyword |
| source.ip | IP address of the source. | ip |
| source.nat.ip | Source NAT ip | ip |
| source.nat.port | Source NAT port | long |
| source.packets | Packets sent from the source to the destination. | long |
| source.port | Port of the source. | long |
| source.user.email | User email address. | keyword |
| source.user.name | Short name or login of the user. | keyword |
| syslog.facility | Syslog numeric facility of the event. | long |
| syslog.facility_label | Syslog text-based facility of the event. | keyword |
| syslog.priority | Syslog priority of the event. | long |
| syslog.severity_label | Syslog text-based severity of the event. | keyword |
| tags | List of keywords used to tag each event. | keyword |
| url.original | Unmodified original url as seen in the event source. | keyword |
| user_agent.original | Unparsed user_agent string. | keyword |

