## 🚀 **Run It**

```bash
docker compose up -d
```

Then test your proxy:

```bash
curl -x http://localhost:3128 http://example.com
```

Or configure your browser/system to use:

```
HTTP Proxy: localhost
Port: 3128
```

---

## 🧠 Optional Enhancements

### 🔐 Basic Authentication

Add to your `squid.conf`:

```conf
auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/passwords
auth_param basic realm proxy
acl authenticated proxy_auth REQUIRED
http_access allow authenticated
http_access deny all
```

Then create passwords file:

```bash
sudo apt install apache2-utils
htpasswd -c passwords myuser
```

Mount it:

```yaml
- ./passwords:/etc/squid/passwords:ro
```

---

### 📈 Monitoring

To see logs live:

```bash
docker compose logs -f squid
```

To enter the container:

```bash
docker exec -it squid bash
```
