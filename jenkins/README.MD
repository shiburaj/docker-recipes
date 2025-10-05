# 🚀 **How to Run**

1. Navigate into the folder:

   ```bash
   cd jenkins
   ```

2. Build and start the containers:

   ```bash
   docker compose up -d --build
   ```

3. Access Jenkins:
   👉 [http://localhost:8080](http://localhost:8080)

4. Jenkins will already have:

   * The specified plugins installed
   * No setup wizard
   * Timezone set
   * Persistent data under `jenkins_home`

---

## 🧠 Optional Tips

* To **add plugins later**, just edit `plugins.txt` and rerun:

  ```bash
  docker compose build jenkins
  docker compose up -d
  ```
* To **see logs**:

  ```bash
  docker compose logs -f jenkins
  ```
* To **get admin password** (first time):

  ```bash
  docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
  ```

