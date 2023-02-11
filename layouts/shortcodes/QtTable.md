| {{ T "Qt Version" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} | {{ T "Variant" }} | {{ T "Uploaded" }} |
|-|-|-|-|-|-|
{{- range sort site.Data.Fsu0413QtBuilds "sort" }}
|{{- .data.QtVersion -}}
|{{- .data.buildHost -}}
|{{- .data.toolchain -}}
|{{- .data.arch -}}
|{{- .data.variant -}}
|{{- .data.uploaded -}}
|{{- end -}}
