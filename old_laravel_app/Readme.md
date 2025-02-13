# Laravel 5.4 Docker Setup Guide

Follow these steps to set up a **Laravel 10.10** app with Docker.  

---

### **1. Prerequisites**

Before proceeding with the setup, ensure you have the following installed:

- Docker
- Docker Compose

### **2. Clone the Repository**
```bash
git clone <your-repository-url> laravel-docker
cd laravel-docker
```

---

### **3. Clone Laravel App Inside `projects` Directory**
The project uses some specific Composer packages that need to be installed.

Run the following commands to install the required packages:
```bash
cd projects
git clone <laravel-app-repository-url> laravel-app
/laravel-app
composer install
composer require bmatovu/laravel-xml
composer require viewflex/zoap
```

This will install the necessary dependencies defined in `composer.json`.

---

### **4. Nginx Configuration (`nginx/default.conf`)**  

Update needful changes on `nginx/default.conf` file.

---

### **5. Build and Start Docker Containers**
```bash
docker-compose up -d --build
```

---

### **6. Verify the Setup**

To check if everything is working correctly, access the container logs:

```bash
docker-compose logs -f
```

Look for any errors. If there are no issues, your setup should be complete.

---

### **7. Access Laravel App**
After running the containers, open **http://localhost:84** in your browser.

### Conclusion

Following these steps, you should have your Docker environment set up with the required dependencies without needing to modify the source code. If you encounter any issues, refer to the troubleshooting section above or reach out to the support team for assistance.