{{- $QtVersion := .Get 0 -}}
| {{ T "Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} | {{ T "Variant" }} | `mkspecs` | {{ T "Uploaded" }} | {{ T "Configuration" }} |
|-|-|-|-|-|-|-|-|
{{- range sort site.Data.Fsu0413QtBuilds "sort" -}}
{{- if eq .data.QtVersion $QtVersion }}
|{{- .data.platform -}}
|{{- .data.buildHost -}}
|{{- .data.toolchain -}}
|{{- .data.arch -}}
|{{- .data.variant -}}
|{{- .data.mkspecs -}}
|{{- .data.uploaded -}}
|{{- .data.configuration -}}
|{{ end -}}
{{- end -}}
