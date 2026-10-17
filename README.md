# Sistema de Gestión de Citas Escolares (SistemaCitasColegio)

Este proyecto implementa un sistema para la programación, atención y seguimiento de citas académicas y de apoyo psicopedagógico en una institución educativa. Está construido bajo la arquitectura Modelo-Vista-Controlador (MVC), aplicando Diseño por Contrato (DbC) y un sistema formal de Checked Exceptions.

---

## Requisitos del Sistema y Prerrequisitos

* Java Development Kit (JDK): Versión 17 o 21.
* Servidor de Aplicaciones (Para Interfaz Web): Apache Tomcat 10.x o superior.
* Herramienta de Construcción / IDE: Apache Ant (incluido en NetBeans / Eclipse / IntelliJ) o compilación directa vía CLI.
* Navegador Web: Google Chrome, Mozilla Firefox o Microsoft Edge.

---

## Configuración del Servidor (Apache Tomcat)

Para desplegar la aplicación web con la interfaz JSP y Servlets:

1. Configurar el Runtime en el IDE:
   * Abrir NetBeans / Eclipse.
   * Ir a Tools > Servers > Add Server.
   * Seleccionar Apache Tomcat e indicar la ruta de instalación local del servidor.
2. Asociar el Servidor al Proyecto:
   * Haz clic derecho sobre el proyecto SistemaCitasColegio > Properties.
   * En la sección Run, selecciona Apache Tomcat en la opción Server.
3. Mapeo de Rutas (Context Path):
   * El puerto por defecto es 8080.
   * La aplicación se desplegará en la URL: http://localhost:8080/SistemaCitasColegio/

---

## Pasos de Ejecución

### Opción 1: Ejecución de Batería de Pruebas Unitarias (Consola / CLI)

No requiere servidor web. Se ejecuta directamente desde la terminal del sistema operativo:

1. Abrir la terminal de comandos (CMD / PowerShell / Terminal).
2. Navegar a la carpeta raíz del proyecto:
   cd /d "C:\Ruta\A\Tu\Proyecto\SistemaCitasColegio"
3. Compilar las clases del sistema y la suite de pruebas:
   javac -encoding UTF-8 -d build/classes test/com/colegio/service/EjecutarPruebas.java src/com/colegio/exception/*.java src/com/colegio/service/*.java src/com/colegio/model/*.java
4. Ejecutar la suite de pruebas unitarias:
   java -cp build/classes com.colegio.service.EjecutarPruebas

---

### Opción 2: Ejecución de la Aplicación Web (Navegador)

1. Desde NetBeans / IDE:
   * Presiona la tecla F6 o haz clic derecho en el proyecto y selecciona Run.
   * El IDE compilará el archivo .war, iniciará Apache Tomcat y abrirá la aplicación en tu navegador predeterminado.
2. Acceso Manual:
   * Abrir el navegador e ingresar a: http://localhost:8080/SistemaCitasColegio/login.jsp

---

## Credenciales de Prueba (Simulación de Roles)

| Rol de Usuario | Correo Electrónico | Contraseña | ID Asignado |
| :--- | :--- | :--- | :--- |
| Estudiante | estudiante@colegio.edu | estudiante123 | 101 |
| Administrador / Profesional | admin@colegio.edu | admin123 | 201 |

---

## Estructura del Repositorio

```text
SistemaCitasColegio/
├── src/
│   └── com/colegio/
│       ├── controller/    # Servlets HTTP (MVC)
│       ├── exception/     # Checked Exceptions personalizadas (DbC)
│       ├── model/         # Entidades del dominio (Cita)
│       └── service/       # Lógica de negocio e interfaz Notificable
├── test/
│   └── com/colegio/
│       └── service/       # Clase EjecutarPruebas.java (8/8 Test Suite)
├── web/                   # Vistas JSP y archivos de estilos web
├── build.xml               # Script de automatización Apache Ant
└── README.md              # Guía de configuración y ejecución
