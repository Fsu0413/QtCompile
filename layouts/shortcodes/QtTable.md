{{- $isLegacy := false -}}
{{- if .Get 0 -}}
{{- $isLegacy = true -}}
{{- end -}}
| {{ T "Qt Version" }} | {{ T "Target Platform" }} | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "Architecture" }} | {{ T "Variant" }} | {{ T "Uploaded" }} |
|-|-|-|-|-|-|-|
{{- range sort (cond $isLegacy site.Data.Fsu0413QtBuildsLegacy site.Data.Fsu0413QtBuilds) "sort" }}
|{{- .data.version -}}
|{{- .data.platform -}}
|{{- .data.buildHost -}}
|{{- .data.toolchain -}}
|{{- .data.arch -}}
|{{- .data.variant -}}
|{{- .data.uploaded -}}
|{{- end -}}
