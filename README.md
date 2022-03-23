# NPM Workspace Behavior Change

It appears that pre npm 8.5.0, it was "safe" to include helper scripts, with the same name as child package scripts that allowed running of ALL matching child scripts. This behavior appears to have changed and can result in some pretty exciting, but unexpected behavior.

Was this change intentional and was I relying on a "load-bearing" bug?


# npm 8.4.1

Run:
`npm run release --workspaces --if-present --include-workspace-root`

Output:

```
○ npm run release --workspaces --if-present --include-workspace-root

[RELEASE]: Package B
[BUILD]: Package B
```

# npm 8.5.0

Output
```
○ npm run release --workspaces --if-present --include-workspace-root
[RELEASE]: Package B

... Infinitely ...
Highly Unexpected for this to log...
Highly Unexpected for this to log...
Highly Unexpected for this to log...

```
