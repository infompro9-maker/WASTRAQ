# WASTRAQ
This repository contains the code and documentation for the WASTRAQ  project, which focuses on waste management and resource optimization.
server {
  listen 80;
  server_name your-domain.com;
  
  # Frontend
  location / {
    root /path/to/your/frontend/build;
    try_files $uri /index.html;
  }

  # Backend
  location /api/ {
    proxy_pass http://localhost:8000;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
  }
}
