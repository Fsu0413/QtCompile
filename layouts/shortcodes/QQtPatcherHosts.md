| {{ T "Qt Version" }} | {{ T "Build Host" }} `mkspecs` | {{ T "Build Host" }} | {{ T "Toolchain Version" }} | {{ T "QQtPatcher Version" }} |
|-|-|-|-|-|
{{- range site.Data.QQtPatcher.Build }}
|{{- .QtVersion -}}
|{{- .mkspec -}}
|{{- .os -}}
|{{- .toolchain -}}
|{{- .version -}}
|{{ end }}
