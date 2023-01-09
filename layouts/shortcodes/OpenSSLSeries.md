| {{ T "OpenSSL Version" }} | {{ T "Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} | {{ T "Variant" }} |
|-|-|-|-|-|-|
{{- range site.Data.opensslBuilds }}
|{{- .version -}}
|{{- .platform -}}
|{{- .host -}}
|{{- .toolchain -}}
|{{- .arch -}}
|{{- .variant -}}
|{{ end }}
