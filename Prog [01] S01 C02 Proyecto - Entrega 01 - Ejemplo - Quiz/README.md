# 2025-1 Programación Movil - Quiz

Este aplicativo móvil es una plataforma interactiva dedicada a los aficionados del deporte, principalmente del fútbol, donde los usuarios podrán poner a prueba sus conocimientos sobre diversas disciplinas deportivas. El sistema se basa en una serie de preguntas de opción múltiple sobre temas como historia, jugadores, equipos, competiciones y estadísticas. Los usuarios podrán competir de manera individual <b>o en tiempo real con otros jugadores</b>, comparando sus resultados y obteniendo puntos por cada respuesta correcta.

Además, la aplicación contará con diferentes niveles de dificultad, desde preguntas más fáciles hasta desafíos complejos para expertos. Los usuarios podrán seguir su progreso a lo largo del tiempo, acceder a estadísticas personalizadas. Con una interfaz amigable y actualizaciones constantes con nuevos contenidos, el aplicativo promete ser una herramienta divertida y educativa para todos los apasionados del fútbol y otros deportes.

- [Configuración del Ambiente de Desarrollo](#configuración-del-ambiente-de-desarrollo)
- [Diagrama de Despliegue](#diagrama-de-despliegue)
- [Requerimientos No Funcionales](#requerimientos-no-funcionales)

## Configuración del Ambiente de Desarrollo

Paso a paso que usaremos en el proyecto.

![Android Studio](imgs/android.webp)

*<b>Figura 1:</b> Instalación de Android Studio*

## Diagrama de Despliegue

La arquitectura a usar será una aplicación web y una aplicación móvil. La aplicación móvil accede a la aplicación web a través de Internet, mientras que la aplicación web consulta y almacena datos en la base de datos. Este modelo de la Figura 2 ilustra cómo los clientes interactúan con la aplicación y cómo se gestionan los datos en el servidor.

![Android Studio](https://www.plantuml.com/plantuml/png/VOvBJWCn44JtFaN9-s73ZWNA2B50GW9cmW7ik0TPyiVnXoWW3iGvk1Wz6HGGGVIswxsgLQagr-QT2D4Gv439sIhnAi37BpkfJOLyQFO5_VqDXgRt4gfWHxfFwLTiox4pep5ksKBdXw3HuarywTVaFjwd62BwO7AqvhJfyTPwXRdlGFkehIDk-fRS9GeOQoQg62a_Kpwr_Cpmx4MbKfajot9q9kv2TydxS05v5KDfhYhiyTHKDWf6rLYaE0v0vsYg32py4VA4mYliniQ2uNfS_yNCtVyHAmgcUVS9)

*<b>Figura 2:</b> Diagrama de despliegue*

## Requerimientos No Funcionales

A continuación, se presentan los requerimientos no funcionales para la arquitectura descrita en el diagrama, considerando el uso de **Flutter** para la aplicación móvil.

### 1. Escalabilidad  
El servidor web debe ser capaz de manejar múltiples solicitudes simultáneamente sin afectar el rendimiento.

### 2. Disponibilidad  
La aplicación debe estar disponible al menos el **99.9%** del tiempo para garantizar el acceso continuo de los clientes.

### 3. Seguridad  
La comunicación entre la aplicación móvil y la aplicación web debe estar protegida mediante **HTTPS** y autenticación segura (**OAuth 2.0, JWT**).

### 4. Compatibilidad  
La aplicación móvil desarrollada en **Flutter** debe ser compatible con **Android** e **iOS** sin pérdida de funcionalidad.

### 5. Rendimiento  
La respuesta del servidor a las solicitudes del cliente no debe exceder los **200 ms** en condiciones normales de uso.

### 6. Mantenimiento  
El sistema debe permitir actualizaciones sin interrumpir el servicio mediante despliegues continuos (**CI/CD**).

### 7. Usabilidad  
La interfaz de la aplicación móvil debe seguir las directrices de **Material Design** para una experiencia intuitiva.

### 8. Integridad de Datos  
La base de datos debe garantizar la consistencia de los datos mediante mecanismos de transacción **ACID**.

### 9. Registro y Monitoreo  
El servidor web debe contar con un sistema de **logging y monitoreo en tiempo real** para detectar fallos.

### 10. Optimización de Red  
La comunicación entre el cliente y el servidor debe minimizar el uso de datos mediante **compresión y caching de respuestas**.

## Diagrama de Casos de Uso

El siguiente diagrama de casos de uso representa las principales interacciones dentro del Sistema de Quizzes, basado en el modelo de clases previamente definido. En este sistema, los usuarios pueden registrarse, iniciar sesión, crear y responder quizzes, así como consultar su historial de intentos. Por otro lado, los administradores tienen permisos adicionales para gestionar preguntas, temas y administrar cuentas de usuario. Estas funcionalidades garantizan una experiencia dinámica y organizada para la creación y resolución de quizzes dentro de la plataforma móvil.

![Casos de Uso](https://www.plantuml.com/plantuml/png/NP4xRiCm38PtdeBmdg5vP2nIP2YwzG5t9op29M1B1KajANgg7g4Ngw0wW1Lj7_yF-lKucPDwdYUWmPDYrricbTGX6VR6Ufq_X5cYc2k5f3Mj4m3bmIcE4sFtLdAU2GFZIvRBXQt3By2oil50LfHN7kicQlnVSRvhXQSeWv2YiSdlJroaRIkTbKbhnvBlRbliCyN0ZRDldVUIVeXvKg6fENAr3wtzoEQI8Ya-AuyvEbt58tm3zCQAcyrzlSyAjclOhM6_XWD0VSq5ZmsLyCGnb3_w0m00)

A continuación se detallan los casos de uso:

| ID   | Caso de Uso                 | Descripción |
|------|-----------------------------|-------------|
| UC1  | Registrarse                 | Permite crear una cuenta en el sistema proporcionando los datos personales. |
| UC2  | Iniciar sesión              | Permite autenticarse en el sistema ingresando el nombre de usuario y contraseña. |
| UC3  | Crear Quiz                  | Permite diseñar y crear quizzes, agregando preguntas y respuestas. |
| UC4  | Responder Quiz              | Permite seleccionar y responder quizzes disponibles en el sistema. |
| UC5  | Ver historial de Quizzes    | Permite consultar los quizzes realizados y visualizar sus resultados. |
| UC6  | Gestionar Preguntas         | Permite agregar, editar o eliminar preguntas dentro del sistema. |

Y el diagrama de clases es el siguiente:

![Clases](https://www.plantuml.com/plantuml/png/bPBDJiCm48JlVWehLzG3rrvQ95wW0iwLSPPg9V-awpL88DwTJPC0Zer4Uwayu_bsjF4-iI7EtYdhJ4hwAG7f3wNbTuFzLcFWwP352CR3LZymOJXDwY2PjqXzgO8tw4e9lJcjiY_PkOBugUOIZt50ssnHDq0RGwdqa2pXm1X3ZJvaIAFJf2Ss31u2bq0UwnoNcz-eEyVZIXXVuGgOZKHWHNoEqO49atgUQzLJ3XdV_uNVxUO11EB8rNlvO_Jmy_tQz6KbhIbdyOzhfQvwUJNTRQSt6ztvxe9L2tTjBBeQ3tzwTVZtmjNqH8hq751g3w7Ftdq1)

## Prototipos

En función a los casos de uso se proponen los siguientes prototipos:

Caso de Uso: Nombre de CU

