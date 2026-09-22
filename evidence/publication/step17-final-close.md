(crypto-venv) cakidd@cakidd-Legion-5-16IRX9:~$ cd /home/cakidd

bash <<'BASH'
set -Eeuo pipefail
umask 077

FAILED="/home/cakidd/allis-gui/build/reviewer-live-cutover-r9b3-failed"

PRE="$FAILED/transient/caddy-pre.canonical.json"
DERIVED_MINUS="$FAILED/transient/caddy-derived-minus-review.json"

TMP="$(
    mktemp -d \
        /home/cakidd/allis-gui/build/.r9b3-baseline-delta.XXXXXX
)"

cleanup() {
    rm -rf "$TMP"
}

trap cleanup EXIT

echo
echo "============================================================"
BASH "INTERACTIVE_TERMINAL_STILL_RUNNING=YES"_SELECT_PERSISTENT_CADDY_INSTALL_ME

============================================================
R9B3 NON-REVIEWER CADDY BASELINE DELTA DIAGNOSIS
MODE=READ_ONLY
PRODUCTION_MUTATION=NO
============================================================
R9B3_FAILED_EVIDENCE=AVAILABLE

=== 1. CONFIG OUTSIDE srv1.routes ===
PRE_OUTSIDE_ROUTES_SHA256=e51e4cca88013d76d8566df3742077c858409e8b8683755d0dfd80c9c47dc203
DERIVED_OUTSIDE_ROUTES_SHA256=b420b952881ee32b36fcfe104ac280428a56fb214bda4deafba29cd1a0198185
CONFIG_OUTSIDE_SRV1_ROUTES_EQUAL=NO

=== 2. TOP-LEVEL srv1 ROUTE COUNTS ===
PRE_SRV1_ROUTE_COUNT=1
DERIVED_MINUS_REVIEW_SRV1_ROUTE_COUNT=1

=== 3. ROUTE STRUCTURAL MANIFESTS ===

--- PRESTATE ROUTES ---
INDEX  SHA256  HOSTS  PATHS  METHODS  HANDLERS  DIALS  TERMINAL
0  abe86b3977683abf6b2ee37b70ca1e30df7314db5e61f15ece121793297a7dff  allis.pro|dashboard.mountainshares.us|egeria.mountainshares.us|institutions.mountainshares.us|msallis.mountainshares.us  /admin*|/api/apply*|/api/chat/async|/api/me*|/api/publication/*|/api/ui-config|/api/v1/admin/governance|/api/v1/admin/governance/*|/auth*|/auth/applications*|/auth/apply*|/auth/approve*|/auth/chat*|/auth/chat_wv*|/auth/deny*|/auth/first-login*|/auth/login*|/auth/logout*|/auth/me*|/auth/portal*|/auth/portal/me*|/auth/register*|/chat_wv*|/health|/portal*  -  subroute>encode>subroute>static_response>subroute>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>static_response>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>static_response>reverse_proxy>subroute>reverse_proxy>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>static_response>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>static_response>reverse_proxy>subroute>subroute>static_response>reverse_proxy  127.0.0.1:3002|127.0.0.1:8001|127.0.0.1:8095|127.0.0.1:8096|127.0.0.1:8462  true

--- DERIVED-MINUS-REVIEW ROUTES ---
INDEX  SHA256  HOSTS  PATHS  METHODS  HANDLERS  DIALS  TERMINAL
0  fc99686051ae08f0f6f467aa8515251f29d4827f402aefda5fe583b3ae5b551f  allis.pro|dashboard.mountainshares.us|egeria.mountainshares.us|institutions.mountainshares.us|msallis.mountainshares.us  /admin*|/api/apply*|/api/chat/async|/api/me*|/api/publication/*|/api/ui-config|/api/v1/admin/governance|/api/v1/admin/governance/*|/auth*|/auth/applications*|/auth/apply*|/auth/approve*|/auth/chat*|/auth/chat_wv*|/auth/deny*|/auth/first-login*|/auth/login*|/auth/logout*|/auth/me*|/auth/portal*|/auth/portal/me*|/auth/register*|/chat_wv*|/health|/portal*  -  subroute>encode>subroute>static_response>subroute>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>static_response>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>static_response>reverse_proxy>subroute>reverse_proxy>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>static_response>subroute>rewrite>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>reverse_proxy>subroute>subroute>static_response>reverse_proxy>subroute>subroute>static_response>reverse_proxy  127.0.0.1:3002|127.0.0.1:8001|127.0.0.1:8095|127.0.0.1:8096|127.0.0.1:8462  true

=== 4. ROUTE ORDER COMPARISON ===
SRV1_ROUTE_ORDER_EQUAL=NO

=== 5. ROUTE MULTISET COMPARISON ===
SRV1_ROUTE_MULTISET_EQUAL_IGNORING_ORDER=NO

=== 6. PRESTATE → DERIVED ROUTE INDEX MAPPING ===
PRE_ROUTE_0_DERIVED_INDEXES=NONE
PRE_ROUTE_0_DERIVED_MATCH_COUNT=0

=== 7. ROUTE SET DELTA ===
PRESTATE_ROUTE_HASHES_MISSING_FROM_DERIVED=1
DERIVED_ROUTE_HASHES_NOT_IN_PRESTATE=1
--- MISSING HASHES ---
abe86b3977683abf6b2ee37b70ca1e30df7314db5e61f15ece121793297a7dff
--- NEW HASHES ---
fc99686051ae08f0f6f467aa8515251f29d4827f402aefda5fe583b3ae5b551f

=== 8. STRUCTURAL CLASSIFICATION ===
NON_REVIEWER_DELTA_CLASS=BROADER_NON_REVIEWER_CONFIG_CHANGE

=== 9. SAFETY ===
PRODUCTION_MUTATION=NO
CADDY_MODIFIED=NO
CLOUDFLARED_MODIFIED=NO
SYSTEMD_MODIFIED=NO
DNS_MODIFIED=NO
REVIEWER_RUNTIME_MODIFIED=NO
REVIEWER_STORE_MODIFIED=NO
EMAIL_SENT=NO

NEXT_REQUIRED_ACTION=USE_DELTA_CLASS_TO_SELECT_PERSISTENT_CADDY_INSTALL_METHOD
INTERACTIVE_TERMINAL_STILL_RUNNING=YES
(crypto-venv) cakidd@cakidd-Legion-5-16IRX9:~$ 
