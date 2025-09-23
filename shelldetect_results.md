skriptk1d@MacBookPro shai-hulud-detect % shellcheck -x shai-hulud-detector.sh

In shai-hulud-detector.sh line 33:
    local script_dir="$(cd "$(dirname "$0")" && pwd)"
          ^--------^ SC2155 (warning): Declare and assign separately to avoid masking return values.


In shai-hulud-detector.sh line 192:
    depth=0
    ^---^ SC2034 (warning): depth appears unused. Verify use (or export if used externally).


In shai-hulud-detector.sh line 219:
        path[$currentdepth]=$key
             ^-----------^ SC2004 (style): $/${} is unnecessary on arithmetic variables.


In shai-hulud-detector.sh line 305:
                if [[ -n "$postinstall_cmd" ]] && ([[ "$postinstall_cmd" == *"curl"* ]] || [[ "$postinstall_cmd" == *"wget"* ]] || [[ "$postinstall_cmd" == *"node -e"* ]] || [[ "$postinstall_cmd" == *"eval"* ]]); then
                                                  ^-- SC2235 (style): Use { ..; } instead of (..) to avoid subshell overhead.


In shai-hulud-detector.sh line 472:
            local context=$(get_file_context "$file")
                  ^-----^ SC2155 (warning): Declare and assign separately to avoid masking return values.


In shai-hulud-detector.sh line 473:
            local content_sample=$(head -20 "$file" | tr '\n' ' ')
                  ^------------^ SC2155 (warning): Declare and assign separately to avoid masking return values.


In shai-hulud-detector.sh line 610:
            if [[ "$(basename $org_file)" == "pnpm-lock.yaml" ]]; then
                              ^-------^ SC2086 (info): Double quote to prevent globbing and word splitting.

Did you mean:
            if [[ "$(basename "$org_file")" == "pnpm-lock.yaml" ]]; then


In shai-hulud-detector.sh line 613:
                transform_pnpm_yaml $org_file > $lockfile
                                    ^-------^ SC2086 (info): Double quote to prevent globbing and word splitting.
                                                ^-------^ SC2086 (info): Double quote to prevent globbing and word splitting.

Did you mean:
                transform_pnpm_yaml "$org_file" > "$lockfile"


In shai-hulud-detector.sh line 632:
            suspicious_hashes=$(grep -c '"integrity": "sha[0-9]\+-[A-Za-z0-9+/=]*"' "$lockfile" 2>/dev/null || echo "0")
            ^---------------^ SC2034 (warning): suspicious_hashes appears unused. Verify use (or export if used externally).


In shai-hulud-detector.sh line 649:
            if [[ "$(basename $org_file)" == "pnpm-lock.yaml" ]]; then
                              ^-------^ SC2086 (info): Double quote to prevent globbing and word splitting.

Did you mean:
            if [[ "$(basename "$org_file")" == "pnpm-lock.yaml" ]]; then


In shai-hulud-detector.sh line 650:
                rm $lockfile
                   ^-------^ SC2086 (info): Double quote to prevent globbing and word splitting.

Did you mean:
                rm "$lockfile"


In shai-hulud-detector.sh line 716:
                    local target="${confusable#*:}"
                          ^----^ SC2034 (warning): target appears unused. Verify use (or export if used externally).


In shai-hulud-detector.sh line 778:
                    local package_part="${package_name#*/}"
                          ^----------^ SC2034 (warning): package_part appears unused. Verify use (or export if used externally).


In shai-hulud-detector.sh line 827:
    local suspicious_ip_patterns=(
          ^--------------------^ SC2034 (warning): suspicious_ip_patterns appears unused. Verify use (or export if used externally).


In shai-hulud-detector.sh line 857:
                    if grep -q "https\?://[^[:space:]]*$domain\|[[:space:]]$domain[[:space:/]\"\']" "$file" 2>/dev/null; then
                                                                           ^-- SC1087 (error): Use braces when expanding arrays, e.g. ${array[idx]} (or ${var}[.. to quiet).


In shai-hulud-detector.sh line 860:
                        suspicious_usage=$(grep "https\?://[^[:space:]]*$domain\|[[:space:]]$domain[[:space:/]\"\']" "$file" 2>/dev/null | grep -v "^[[:space:]]*#\|^[[:space:]]*//" 2>/dev/null | head -1 2>/dev/null) || true
                                                                                            ^-- SC1087 (error): Use braces when expanding arrays, e.g. ${array[idx]} (or ${var}[.. to quiet).


In shai-hulud-detector.sh line 864:
                            line_info=$(grep -n "https\?://[^[:space:]]*$domain\|[[:space:]]$domain[[:space:/]\"\']" "$file" 2>/dev/null | grep -v "^[[:space:]]*#\|^[[:space:]]*//" 2>/dev/null | head -1 2>/dev/null) || true
                                                                                            ^-- SC1087 (error): Use braces when expanding arrays, e.g. ${array[idx]} (or ${var}[.. to quiet).


In shai-hulud-detector.sh line 869:
                            if [[ "$file" == *".min.js"* ]] || [[ $(echo "$suspicious_usage" | wc -c 2>/dev/null) -gt 150 ]]; then
                                                                    ^-- SC2000 (style): See if you can use ${#variable} instead.

For more information:
  https://www.shellcheck.net/wiki/SC1087 -- Use braces when expanding arrays,...
  https://www.shellcheck.net/wiki/SC2034 -- depth appears unused. Verify use ...
  https://www.shellcheck.net/wiki/SC2155 -- Declare and assign separately to ...
