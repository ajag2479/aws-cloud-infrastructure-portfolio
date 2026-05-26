# Módulo 01: AWS IAM & Governance (4 Labs)

## 📌 Visión General del Módulo
La gestión de identidades y accesos es la primera línea de defensa en la nube. En este módulo, implementé los cuatro laboratorios fundamentales de **AWS Identity and Access Management (IAM)** utilizando la consola de AWS. El objetivo principal fue migrar de un entorno inseguro (uso de la cuenta raíz) hacia una arquitectura de accesos controlada bajo las mejores prácticas del **AWS Well-Architected Framework (Pilar de Seguridad)**.

---

## 🛠️ Detalle de los Laboratorios Practicados

### Lab 1: Creación y Aseguramiento de Usuarios IAM
* **Caso de Uso/Problema:** Seguir operando la infraestructura cloud desde la cuenta raíz (*Root Account*) expone a la organización a un riesgo catastrófico de seguridad.
* **Solución Implementada:** Creé un usuario administrador dedicado para las tareas diarias de ingeniería, aplicando inmediatamente políticas de contraseñas robustas y activando **Multi-Factor Authentication (MFA)** de manera obligatoria. La cuenta raíz fue archivada de forma segura con una clave compleja y MFA de hardware.
* **Evidencia Visual:**
  ![Configuración de Usuario y MFA Activo](img/lab1-usuario.png)

### Lab 2: Control de Accesos Basado en Grupos (RBAC)
* **Caso de Uso/Problema:** Asignar políticas de permisos directamente a los usuarios individuales genera inconsistencias en auditorías y fallas de seguridad a medida que el equipo técnico crece.
* **Solución Implementada:** Diseñé una arquitectura de control de acceso basado en roles/funciones (*Role-Based Access Control*). Creé grupos específicos (ej. `SysOps-Admins`, `Developers`, `Auditors`) y asocié las políticas de AWS directamente a los grupos. Los usuarios heredan permisos de forma automática únicamente al ser añadidos a su respectivo grupo.
* **Evidencia Visual:**
  ![Estructura de Grupos y Miembros en IAM](img/lab2-grupo.png)

### Lab 3: Roles de IAM para Servicios (Acceso Seguro sin Credenciales Estáticas)
* **Caso de Uso/Problema:** Permitir que un servicio (como una instancia EC2) acceda a un recurso (como un bucket de S3) usando Access Keys estáticas en código expone las credenciales a filtraciones en repositorios públicos.
* **Solución Implementada:** Implementé una solución de seguridad *Zero-Trust* mediante la creación de un **IAM Role** de confianza para el servicio EC2 con permisos de lectura en S3. Esto permite que la instancia consuma credenciales efímeras y rotativas automáticamente a través del *AWS Instance Metadata Service (IMDS)*, eliminando por completo el uso de llaves estáticas en texto plano.
* **Evidencia Visual:**
  ![Rol de Entidad de Confianza asignado](img/lab3-rol.png)

### Lab 4: Políticas Personalizadas (Customer Managed Policies)
* **Caso de Uso/Problema:** Las políticas administradas por AWS (*AWS Managed Policies*) suelen ser demasiado amplias (como `AmazonS3FullAccess`), violando el cumplimiento de normas de seguridad estrictas.
* **Solución Implementada:** Escribí y guardé una política personalizada en formato **JSON** aplicando estrictamente el **Principio de Mínimo Privilegio (Least Privilege)**. La política restringe el acceso de un grupo de desarrolladores para que *únicamente* puedan listar (`ListBucket`) y leer objetos (`GetObject`) dentro de un bucket S3 específico de desarrollo, denegando acciones de eliminación (`DeleteObject`) y acceso a otros buckets de la empresa.
* **Evidencia Visual:**
  ![Estructura JSON de la Política Personalizada](img/lab4-politica.png)

---

## 🧠 Conclusiones y Conceptos Clave Demostrados

Al completar este bloque, adquirí destreza técnica verificable en los siguientes pilares que los equipos de ingeniería buscan:

1. **Principio de Mínimo Privilegio:** Evité por completo el uso de permisos tipo administrador general (`*`) y opté por el acceso mínimo requerido para cumplir la función del negocio.
2. **Seguridad Zero-Trust:** Entiendo que las credenciales estáticas son un riesgo; la implementación de Roles mediante credenciales efímeras soluciona este vector de ataque.
3. **Gobernanza de Identidades:** La separación de usuarios por grupos asegura que las auditorías de seguridad en la nube (como las de *AWS CloudTrail*) sean claras y rastreables a personas específicas.
