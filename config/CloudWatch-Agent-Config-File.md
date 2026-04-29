# CloudWatch Agent Config File

{
"metrics": {
"namespace": "KavMonitoring",
"metrics_collected": {
"cpu": {
"measurement": ["cpu_usage_idle", "cpu_usage_user", "cpu_usage_system"],
"metrics_collection_interval": 60,
"totalcpu": true
},
"mem": {
"measurement": ["mem_used_percent", "mem_available"],
"metrics_collection_interval": 60
},
"disk": {
"measurement": ["disk_used_percent", "disk_free"],
"metrics_collection_interval": 60,
"resources": ["/"]
}
}
}
}
