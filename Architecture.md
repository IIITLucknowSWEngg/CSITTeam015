@@ -0,0 +1,51 @@
# Container Diagram
## User
![container-diagram-User](https://www.planttext.com/api/plantuml/png/b5NDZjem4BxdALnwg8I4zeuGMW9eLMdP8jXgpvDa21QE4zccb6VheO_KL-Zatmw1XHFAp7pV_7mpvj-Vly_QW3B7H7XV8jnnYMopdB_FtbvUbqnXQ4360XkV_-DrmOR3IPYAL8rz0U5XEXnwdk5689kdqW25ARRW42j8s8Yjzwd4DVa4_NhUDpQB8fOfde0wix06Q7Byr0JKb9AdqckB6ApIW1FvBCi633HBYa_wOfD9wn8yX1mudRAlWiTx4uWZsYmV63GK9mnAV6Ny55oKDbj_PozWy0JdWkL8nkgRg2olIqET-JGcb14rftxn4BLD_Qv0QYYQPjlINx2RrbwPytvvgDAAfSaIAqHvKQtDbLVwACaQpWbAu_1afUrHghVKy5qrOeTFMev7ILUemZrq2amgurra9Cm230IWqLx4AzhKeLrn5ZvbgPrDXZCAaPukH758SbNkHTTgE0IL73SvgCdbRuDAWc3wh0qcJeUDhv6xY77KBYoKeeajBNccZCk3K-PHxzbLkJFoEiwxE7sG1ovZkxAWD7rQ6JM_GL7aqdkU4H3DYQItvMwVaz5ewjpqc0toevw347hWLM_6xI3RaqVs7341LY0XHcPjLm_KljaMqspH9Q1pd8HPgvGU6rrhsvEaxm09kCqVArkf7cZtrDeQwyiaaDSpWCvSQ7i9ka68dZuKDsXrPoEgO-aBxJHkpU8Au0QYMgdUuNKxlZtqvdrg2VgcNP1qxwAMuEASRepKlObnUJVbZkrepv-sQEWlEg-4E9w9FV_B_my00F__0m00)
## Merchant
![container-diagram-Merchant](https://www.planttext.com/api/plantuml/png/b5RRRXen47tVhvZIXqf8A8cg92L2A5oYA5AIhd9Hditk05QytfLjGlcsFlIJ-WiTmrviTZU59_3Cd6FxdF70tzz_hhLXogmI4No9SSubmjFDv6NqU7j_0meZm-H2O9aR_xoVGhSxY5AHggknOD7xiDiD0iEDG9YaqZ0gKp3bRA5O0Zq8bwd4a7A2FeFW6upY63B54wOs41K0JObNZQetPn6N2s1P9dZ434-b3ge3THxI6QUDHbdM0QOXsIvf1OD1bIgGmo5ydPtrexZlKhpXhCIlSRO3vy7FaVQ0C0hlu9OPNBFDbc95mNnDF4xMSlI_Nvx6CtlhCIc5CWQg_k0HUfTwKKng5jcDuNcNtrARAfw7xJLvfDASnMuHn-mqZcl7T7di4OyX67CX86IR1ANnY4XWSGpHdVn0RMeql0mVHwPN90XL-rnvz1YgnzJmUMwrnoQTn7y9oTKfCsp6DBgDt69iKRhlx7HCEnH9ouuNU35dDKCzl7Nq0A1df4TWdJo0m37GWrSE7aHI6BV7aOVRA4ZVcry6bMG2z4ORJ3nnnqo-dxpIUtlUvdRNejXkIPGbU1UnpD7bsVcFSy-Y9LTnBwGHk04h5pbO2aJV3wK9Lte9hMsLKTPBViPArtv2iHjzIvxHKT2i4QNROzNSw_M6tWYwWewTGHCcXEu4-NpxlCZDsCg6iKE01oRP0i5fwGQeEsagJDc_TO0xKIg0sxSDkzJdHmMjEhOHk3SiN5pHf65Alm8S6-1Dqu4OdkrST-qbQD0WufwsrFO4Va8MdxmfRj1Ho4NaJxsfr1Ml4BEbj2wPBsGhR4ymJyKMKDlTdST9i52bz3EemRvWlwcQhcMV8e4cQPAif9KPOStDidooGPCt5bnxUeLXjHThNRkcZFqhz0y00F__0m00)
```plantuml
   @startuml
   !define RECTANGLE rectangle
   !define BOLD *<color:Black>*
   title Container Diagram - Blink It Clone
   ' User-facing applications
   RECTANGLE "Mobile App" as mobileApp <<Mobile Application>> #b19cd9
   RECTANGLE "Web App" as webApp <<Web Application>> #b19cd9
   RECTANGLE "User API Gateway" as userGateway <<API Gateway>> #9370db
   ' Backend services
   RECTANGLE "Order Service" as orderService <<Microservice>> #dda0dd
   RECTANGLE "Inventory Service" as inventoryService <<Microservice>> #dda0dd
   RECTANGLE "Delivery Service" as deliveryService <<Microservice>> #dda0dd
   RECTANGLE "User Service" as userService <<Microservice>> #dda0dd
   RECTANGLE "Notification Service" as notificationService <<Microservice>> #dda0dd
   ' Database containers
   RECTANGLE "Order Database" as orderDB <<Database>> #e6e6fa
   RECTANGLE "Inventory Database" as inventoryDB <<Database>> #e6e6fa
   RECTANGLE "User Database" as userDB <<Database>> #e6e6fa
   ' External systems
   RECTANGLE "Payment Gateway" as paymentGateway <<External System>> #c71585
   RECTANGLE "Push Notification Service" as pushNotification <<External System>> #c71585
   ' Relationships between containers
   mobileApp --> userGateway : "API Calls"
   webApp --> userGateway : "API Calls"
   userGateway --> orderService : "Manage Orders"
   userGateway --> inventoryService : "Check Inventory"
   userGateway --> deliveryService : "Schedule Delivery"
   userGateway --> userService : "User Profile Management"
   userGateway --> notificationService : "Send Notifications"
   orderService --> orderDB : "Read/Write Data"
   inventoryService --> inventoryDB : "Read/Write Data"
   userService --> userDB : "Read/Write Data"
   orderService --> paymentGateway : "Process Payments"
   notificationService --> pushNotification : "Send Push Notifications"
   @enduml
 
