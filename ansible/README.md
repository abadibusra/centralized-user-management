# Centralized User Management with OpenLDAP + Node.js + Ansible

This project automates the **setup of an OpenLDAP server** and a **web-based centralized user management application**.  
Everything is deployed and managed from a **control node using Ansible**.  

---

## 🛠️ What It Does
1. **Sets up OpenLDAP** on a Debian server (via `ldap.yml`).  
2. **Deploys a Node.js web app** (via `userapp.yml`) where admins can:
   - Log in securely
   - Add, list, and delete LDAP users
   - Sync changes directly into LDAP
3. All deployments are automated → no manual `docker compose` or `ldapadd` needed.

---

## 📂 Project Structure
ansible/
├── ldap.yml # Install + configure OpenLDAP
├── userapp.yml # Deploy Node.js user management app
├── inventory # Define your servers
├── vars/
│ ├── ldap_main.yml # LDAP domain/org/admin pass
│ └── ldap_debconf.yml # Slapd preseeding
app/
├── server.js # Express API + LDAP integration
├── Dockerfile
├── docker-compose.yml
├── package.json
├── public/ # Frontend UI
│ ├── index.html
│ └── app.js
└── .env.example # Template env file for app
