{{/* layouts/shortcodes/scryfall.html */}}
{{- $content := .Inner -}}

{{- /* Replace ![[Card Name]] with card image */ -}}
{{- range findRE `!\[\[(.+?)\]\]` $content -}}
  {{- $fullMatch := . -}}
  {{- $name := replaceRE `^!\[\[(.+?)\]\]$` `$1` $fullMatch -}}
  {{- $enc := urlquery $name -}}
  {{- $image := printf `![%s](https://api.scryfall.com/cards/named?format=image&version=normal&exact=%s)` $name $enc -}}
  {{- $content = replace $content $fullMatch $image -}}
{{- end -}}

{{- /* Replace [[Card Name]] with card link */ -}}
{{- range findRE `\[\[(.+?)\]\]` $content -}}
  {{- $fullMatch := . -}}
  {{- $name := replaceRE `^\[\[(.+?)\]\]$` `$1` $fullMatch -}}
  {{- $enc := urlquery $name -}}
  {{- $link := printf `[%s](https://scryfall.com/search?q=!"%s")` $name $enc -}}
  {{- $content = replace $content $fullMatch $link -}}
{{- end -}}

{{- $content -}}
