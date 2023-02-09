| {{ T "MariaDB Version" }} | {{ T "Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} |
|-|-|-|-|-|
{{- range site.Data.mariaDBBuilds }}
|{{- .version -}}
|{{- .platform -}}
|{{- .host -}}
|{{- .toolchain -}}
|{{- .arch -}}
|{{ end }}
