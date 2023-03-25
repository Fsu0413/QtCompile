{{- $year := .Get 0 -}}
{{- $month := .Get 1 -}}
{{- $day := .Get 2 -}}
{{- $lang := site.Language.Lang -}}
{{- if (eq $lang "en") -}}
    {{- $monthStr := index (slice
        "Jan" "Feb" "Mar" "Apr" "May" "Jun" "Jul" "Aug" "Sep" "Oct" "Nov" "Dec"
    ) (sub $month 1) -}}
    {{- $daySuffix := index (slice
		"st" "nd" "rd" "th" "th" "th" "th" "th" "th" "th"
		"th" "th" "th" "th" "th" "th" "th" "th" "th" "th"
		"st" "nd" "rd" "th" "th" "th" "th" "th" "th" "th"
		"st"
    ) (sub $day 1) -}}
    {{ $day -}}{{- $daySuffix }} {{ $monthStr }}, {{ $year }}
{{- else -}}
    {{ $year }} 年 {{ $month }} 月 {{ $day }} 日
{{- end -}}
