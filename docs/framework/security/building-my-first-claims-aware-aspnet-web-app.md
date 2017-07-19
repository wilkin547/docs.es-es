---
title: "Crear mi primera aplicaci&#243;n web de ASP.NET para notificaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# Crear mi primera aplicaci&#243;n web de ASP.NET para notificaciones
## Se aplica a  
  
-   Windows Identity Foundation \(WIF\)  
  
-   ASP.NET  
  
 En este tema se describe el escenario de compilación de aplicaciones web ASP.NET compatibles con notificaciones mediante WIF.  En un escenario de aplicación compatible con notificaciones suele haber tres participantes: la propia aplicación, el usuario final y el servicio de token de seguridad \(STS\).  En la ilustración siguiente se describe este escenario:  
  
 ![Aplicación web de WIF básica](../../../docs/framework/security/media/wifbasicwebapp.png "WIFBasicWebApp")  
  
1.  La aplicación para notificaciones usa WIF para identificar las solicitudes no autenticadas y redirigirlas al STS.  
  
2.  El usuario final proporciona las credenciales al STS y, tras su correcta autenticación, el STS emite un token para el usuario.  
  
3.  Se redirige al usuario del STS a la aplicación para notificaciones con el token emitido por el STS en la solicitud.  
  
4.  La aplicación para notificaciones se configura para confiar en el STS y en los token que emite.  Asimismo, dicha aplicación usa WIF para validar el token y analizarlo.  Los desarrolladores usan la API y los tipos de WIF adecuados según las necesidades de la aplicación \(por ejemplo, **ClaimsPrincipal**\), como la implementación de una autorización correspondiente.  
  
 A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework.  Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en la plataforma .NET, lo que facilita el uso de las notificaciones.  Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones.  Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.  
  
 El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente.  Microsoft ofrece dos STS estándar del sector:  
  
-   [Servicios de federación de Active Directory \(AD FS\) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247516\)  
  
-   [Servicio de control de acceso \(ACS\) de Microsoft Azure](http://go.microsoft.com/fwlink/?LinkID=247517) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247517\).  
  
 AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales.  ACS es un servicio de nube que se ofrece como parte de la plataforma Microsoft Azure.  Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones.  Por ejemplo, se puede usar el STS de desarrollo local que forma parte de [Identity and Access Tool de Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=245849\), disponible en línea de forma gratuita.  
  
 Para compilar la primera aplicación ASP.NET compatible con notificaciones mediante WIF, siga las instrucciones de uno de los sitios siguientes:  
  
-   [Cómo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [Cómo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [Cómo: compilar aplicaciones ASP.NET para notificaciones mediante la autenticación basada en formularios](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## Vea también  
 [Introducción a WIF](../../../docs/framework/security/getting-started-with-wif.md)