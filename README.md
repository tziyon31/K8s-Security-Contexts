# 🛡️ Kubernetes Security Contexts

A practical walkthrough for understanding and configuring **Pod and Container-level security contexts** in Kubernetes — including user permissions and capabilities.

---

## 📘 Step 1 – Viewing Default Namespace Resources

**We start by listing all resources in the default namespace to get an overview of existing pods.**

<br><br>

<p align="center">
  <img width="537" height="99" alt="namespace resources" src="https://github.com/user-attachments/assets/025d34b5-0d96-478c-801a-67232a59a087" />
</p>

<br><br>

---

## 👤 Step 2 – Checking Which User Runs the Pod

**We verify which Linux user (UID) the pod is currently running as.**  
This helps identify whether privileges are properly restricted.

<br><br>

<p align="center">
  <img width="390" height="41" alt="running user" src="https://github.com/user-attachments/assets/88016bbb-a725-46d6-9f59-0d6695e92afb" />
</p>

<br><br>

---

## 📚 Step 3 – Reviewing Kubernetes Documentation

**We refer to the official Kubernetes documentation to recall the structure and options for `securityContext`.**  
Understanding which settings apply to the Pod vs. the Container is essential for secure configurations.

<br><br>

<p align="center">
  <img width="1807" height="829" alt="kubernetes docs" src="https://github.com/user-attachments/assets/642790ac-d25e-49a2-80ad-0675ef384277" />
</p>

<br><br>

---

## 🧱 Step 4 – Editing the Pod YAML

**We edit the Pod manifest to explicitly define the security context configuration.**  
This includes setting a custom user ID and defining a baseline security policy.

<br><br>

<p align="center">
  <img width="475" height="275" alt="yaml edit 1" src="https://github.com/user-attachments/assets/25a537bc-b1fe-41e1-95f4-ec9bdee240b1" />
</p>

<br><br>

<p align="center">
  <img width="547" height="56" alt="yaml edit 2" src="https://github.com/user-attachments/assets/62962463-b73a-4f72-8bc5-a32fc7bef16b" />
</p>

<br><br>

---

## 🧩 Step 5 – Creating a Multi-Container Pod with Two Security Contexts

**To configure two security contexts — one at the Pod level and one at the Container level — define `securityContext` under both the Pod spec (for defaults) and inside each container.**

<br><br>

<p align="center">
  <img width="243" height="278" alt="multi-container pod" src="https://github.com/user-attachments/assets/bb499c5c-26cd-41ea-8623-b6bebe39fdc2" />
</p>

<br><br>

---

## 🔒 Step 6 – Adding Linux Capabilities and Changing User

**We now extend container privileges by adding Linux capabilities such as `NET_ADMIN` or `SYS_TIME`.**  
⚠️ Always add them **under the container’s `securityContext`**, not the Pod’s, since capabilities are container-specific.

<br><br>

<img width="277" height="377" alt="image" src="https://github.com/user-attachments/assets/f22a9df1-0e9e-4620-b06b-43c1ab45a338" />


<br><br>

---

## 🧠 Key Takeaways

- Use **Pod-level securityContext** for shared defaults (e.g., `runAsUser`, `fsGroup`).  
- Use **Container-level securityContext** to override or add specific privileges.  
- Capabilities like `NET_ADMIN` and `SYS_TIME` must be defined **per container**.  
- Applying least privilege ensures both functionality and security balance.

---

<p align="center"><b>With layered security contexts, each container runs safely and independently within its own permissions boundary.</b></p>
