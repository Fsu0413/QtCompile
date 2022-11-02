{{- $t := .Get 1 -}}
{{- $d := ( print "QTBUG-" (.Get 0 ) ) -}}
{{- $title := cond (eq (len $t) 0) $d $t -}}
[{{- $title -}}](https://bugreports.qt.io/browse/QTBUG-{{- .Get 0 -}})
