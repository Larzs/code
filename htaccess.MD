# .htaccess

```markdown
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.html [L]
</IfModule>
```

```markdown
RewriteCond %{REQUEST_URI} !/maintenance.html$ 
RewriteCond %{REMOTE_HOST} !^###\.###\.###\.###
RewriteCond %{REMOTE_HOST} !^###\.###\.###\.###

RewriteRule $ /maintenance.html [R=302,L] 
```
