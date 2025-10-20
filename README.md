# K8s-Security-Contexts
These are out resources default namespace resources
<img width="537" height="99" alt="image" src="https://github.com/user-attachments/assets/025d34b5-0d96-478c-801a-67232a59a087" />


Checking which user is running the pod
<img width="390" height="41" alt="image" src="https://github.com/user-attachments/assets/88016bbb-a725-46d6-9f59-0d6695e92afb" />
Lets the Kubernnetes Documentation to remind ourselves how to configure security context
<img width="1807" height="829" alt="image" src="https://github.com/user-attachments/assets/642790ac-d25e-49a2-80ad-0675ef384277" />
editting pod yaml and replacing
<img width="475" height="275" alt="image" src="https://github.com/user-attachments/assets/25a537bc-b1fe-41e1-95f4-ec9bdee240b1" />
<img width="547" height="56" alt="image" src="https://github.com/user-attachments/assets/62962463-b73a-4f72-8bc5-a32fc7bef16b" />
Creating Multi-Container Pod with 2 security contexts 
To configure two security contexts: one at the Pod level and one at the Container level — define securityContext under both the Pod spec (for defaults) and inside each container 
<img width="243" height="278" alt="image" src="https://github.com/user-attachments/assets/bb499c5c-26cd-41ea-8623-b6bebe39fdc2" />
Now were adding capabilities. Make sure you only add them under container spec and not the pods spec
<img width="293" height="346" alt="image" src="https://github.com/user-attachments/assets/3775f41f-3120-486a-a48e-4c9b3b633211" />





