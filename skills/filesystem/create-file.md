# skills/filesystem/create-file.md

# Skill: filesystem.create-file

Creates or overwrites a file at a given relative path with exact contents.

Inputs:
- path (string) — relative path
- contents (string)

Operation:
mkdir -p "$(dirname "$path")"
cat > "$path" <<'EOF'
$contents
EOF

Verification:
test -f "$path"
git diff -- "$path"

Rollback:
rm -f "$path"
git checkout -- "$path"