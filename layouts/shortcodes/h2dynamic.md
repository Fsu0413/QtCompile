{{- $content := T "fsqtbuild_i18n_h2dynamic" -}}
{{- if .Get 0 -}}
{{- $content = printf ( T "fsqtbuild_i18n_h2dynamicarg") ( .Get 1 ) -}}
{{- end -}}
## {{ print $content -}}
