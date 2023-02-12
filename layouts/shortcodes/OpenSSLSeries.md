| {{ T "OpenSSL Version" }} | {{ T "Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} | {{ T "Variant" }} |
|-|-|-|-|-|-|
{{- range sort site.Data.Fsu0413OpenSSLBuilds "sort" }}
|{{- .data.version -}}
|{{- .data.platform -}}
|{{- .data.buildHost -}}
|{{- .data.toolchain -}}
|{{- .data.arch -}}
|{{- .data.variant -}}
|{{ end }}
