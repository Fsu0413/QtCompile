| {{ T "MariaDB Version" }} | {{ T "Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} |
|-|-|-|-|-|
{{- range sort site.Data.Fsu0413MariaDBBuilds "sort" }}
|{{- .data.version -}}
|{{- .data.platform -}}
|{{- .data.buildHost -}}
|{{- .data.toolchain -}}
|{{- .data.arch -}}
|{{ end }}
