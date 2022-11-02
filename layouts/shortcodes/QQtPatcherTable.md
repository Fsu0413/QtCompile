| {{ T "Qt Version" }} | {{ T "Build Host" }} `mkspecs` | {{ T "Build Target" }} `mkspecs` | {{ T "Notes" }} | {{ T "Tested" }} |
|-|-|-|-|-|
{{- range .Site.Data.QQtPatcher.Table }}
|{{- .QtVersion -}}
|{{- .host -}}
|{{- if .target -}}{{- .target -}}{{- else -}}-{{- end -}}
|{{- if .Notes -}}{{- .Notes -}}{{- end -}}
|{{- if .NotTested -}}{{- else -}}√{{- end -}}
|{{ end }}
