---
title: "Compilar mi primer servicio WCF con reconocimiento de notificaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Compilar mi primer servicio WCF con reconocimiento de notificaciones
## Se aplica a  
  
-   Windows Identity Foundation \(WIF\)  
  
-   Windows Communication Foundation \(WCF\)  
  
## Información general  
 En este tema se describe el escenario para compilar servicios WCF para notificaciones mediante WIF.  En un escenario de servicio Web para notificaciones suele haber tres participantes: el propio servicio Web, el usuario final y el servicio de token de seguridad \(STS\).  En la ilustración siguiente se describe este escenario:  
  
 ![Servicio WCF de notificaciones de WIF básico](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.png "WIFBasicClaimsAwareWCFService")  
  
1.  El cliente de servicio WCF \(a veces denominado agente\) usa WIF para enviar credenciales al STS que a su vez, y tras llevarse la autenticación a cabo correctamente, emite un token para el agente.  
  
2.  El agente envía este token emitido por el STS al servicio WCF.  
  
3.  El servicio WCF para notificaciones se configura de forma que confíe en el STS y en los token que emite.  Asimismo, usa WIF para validar el token y analizarlo.  Los desarrolladores usan la API y los tipos de WIF adecuados, por ejemplo **ClaimsPrincipal**, según las necesidades de la aplicación, como la implementación de una autorización correspondiente.  
  
 A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework.  Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en la plataforma .NET, lo que facilita el uso de las notificaciones.  Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones.  Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.  
  
 El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente.  Microsoft ofrece dos STS estándar del sector:  
  
-   [Servicios de federación de Active Directory \(AD FS\) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247516\)  
  
-   [Servicio de control de acceso \(ACS\) de Windows Azure](http://go.microsoft.com/fwlink/?LinkID=247517) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247517\).  
  
 AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales.  El control de acceso de Active Directory de Azure \(también conocido como Servicio de control de acceso o ACS\) es un servicio en la nube que se ofrece como parte de Microsoft Azure.  Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones.  Por ejemplo, se puede usar el STS de desarrollo local que forma parte de [Identity and Access Tool de Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=245849\), disponible en línea de forma gratuita.  
  
 Para crear su primer servicio WCF para notificaciones mediante WIF, consulte [How To: Build Claims\-Aware WCF Service Using WIF](http://msdn.microsoft.com/es-es/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).  
  
## Vea también  
 [Introducción a WIF](../../../docs/framework/security/getting-started-with-wif.md)