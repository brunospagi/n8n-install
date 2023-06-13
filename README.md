**Manual de Instalação N8N**


</p>
sudo apt update && sudo apt upgrade y
</p>
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
</p>
sudo apt-get install -y nodejs
</p>
node -v
</p>
sudo npm install n8n -g
</p>
npm update -g n8n
</p>
sudo apt install npm
</p>
npm install pm2 -g
</p>
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
</p>
sudo apt install ./google-chrome-stable_current_amd64.deb
</p>
sudo nano /etc/nginx/sites-available/n8n
</p>
</p>
</p>

```
server {

  server_name n8n.dominio.com.br;

  location / {

    proxy_pass http://127.0.0.1:5678;

    proxy_http_version 1.1;

    proxy_set_header Upgrade $http_upgrade;

    proxy_set_header Connection 'upgrade';

    proxy_set_header Host $host;

    proxy_set_header X-Real-IP $remote_addr;

    proxy_set_header X-Forwarded-Proto $scheme;

    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    proxy_cache_bypass $http_upgrade;

    proxy_buffering off;

    proxy_cache off;

  }

  }
  ```

</p>
</p>
</p>
sudo ln -s /etc/nginx/sites-available/n8n /etc/nginx/sites-enabled
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>
</p>
pm2 start n8n --cron-restart="0 0 * * *" -- start
</p>

**EXECUTE COMANDO ABAIXO PARA NÃO CAIR QUANDO REINICIAR A VPS**

</p>
sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save
</p>
cd 
</p>
git clone https://github.com/EngajamentoFlow/quepasa
</p>
export N8N_EDITOR_BASE_URL=https://seudominio.com.br
</p>
export WEBHOOK_URL=https://seudominio.com.br
</p>
pm2 restart all --update-env
</p>


<hr />
