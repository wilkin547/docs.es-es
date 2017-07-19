---
title: "Controlador de token web de JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# Controlador de token web de JSON
La extensión del controlador de token web JSON para Windows Identity Foundation permite crear y validar tokens web JSON \(JWT\) en las aplicaciones.  El controlador de token JWT se puede configurar para ejecutarse en la canalización de WIF igual que otros controladores de tokens de seguridad integrados, pero también se puede usar de forma independiente para validar tokens en aplicaciones ligeras.  El controlador de token JWT es especialmente útil cuando se usa un esquema de token portador de OAuth 2.0, como la autenticación en Microsoft Azure Active Directory.  
  
 El controlador de token JWT está disponible como paquete NuGet.  Consulte [Descargar el paquete del controlador de token web de JSON](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md) para obtener más información.  
  
## Escenarios  
 El controlador de token JWT habilita los escenarios clave siguientes:  
  
-   **Validar un token JWT en una aplicación de servidor**: en este escenario, una empresa llamada Litware tiene una aplicación de servidor que usa WIF para controlar las solicitudes de inicio de sesión web.  Litware desea habilitar la aplicación para usar tokens JWT para la autenticación.  La aplicación se actualiza con el controlador de token JWT y, a continuación, la configuración de la aplicación se actualiza para agregar dicho controlador en la canalización de WIF.  Una vez que se realizan las actualizaciones y se especifica una nueva solicitud en la canalización de WIF, el token JWT se valida con el nuevo controlador y la autenticación se lleva a cabo correctamente.  
  
-   **Validar un token JWT en un servicio Web REST**: en este escenario, una empresa llamada Litware tiene un servicio Web REST protegido por Microsoft Azure Active Directory.  Microsoft Azure AD debe autenticar las solicitudes al servicio Web. Tras una autenticación correcta, se emite un token JWT.  Litware tiene una aplicación cliente que requiere acceso al servicio Web.  El cliente realiza una solicitud al servicio Web y presenta su token JWT de Microsoft Azure AD que el servicio Web valida a continuación mediante el controlador de token JWT.  Una vez que el controlador de token JWT ha validado el token, el servicio Web devuelve el recurso deseado al cliente.  
  
## Características  
 El controlador de token JWT ofrece las características siguientes:  
  
-   **Validar un token JWT**: los tokens JWT pueden validarse fácilmente mediante la lógica de validación del controlador de token, ya sea como parte de la canalización WIF de la aplicación o al llamarse con independencia de WIF.  
  
-   **Crear un token JWT**: el controlador de token JWT se puede usar para crear tokens JWT con fines de autorización en servicios descendentes.