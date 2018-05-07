---
title: Crear mi primera aplicación web de ASP.NET para notificaciones
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7e36ec5b824f60057ce7b1f18c695607cf9b88a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a>Crear mi primera aplicación web de ASP.NET para notificaciones
## <a name="applies-to"></a>Se aplica a  
  
-   Windows Identity Foundation (WIF)  
  
-   ASP.NET  
  
 En este tema se describe el escenario de compilación de aplicaciones web ASP.NET compatibles con notificaciones mediante WIF. En un escenario de aplicación compatible con notificaciones suele haber tres participantes: la propia aplicación, el usuario final y el servicio de token de seguridad (STS). En la ilustración siguiente se describe este escenario:  
  
 ![Aplicación web de WIF básica](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")  
  
1.  La aplicación para notificaciones usa WIF para identificar las solicitudes no autenticadas y redirigirlas al STS.  
  
2.  El usuario final proporciona las credenciales al STS y, tras su correcta autenticación, el STS emite un token para el usuario.  
  
3.  Se redirige al usuario del STS a la aplicación para notificaciones con el token emitido por el STS en la solicitud.  
  
4.  La aplicación para notificaciones se configura para confiar en el STS y en los token que emite. Asimismo, dicha aplicación usa WIF para validar el token y analizarlo. Los desarrolladores usan la API y los tipos de WIF adecuados, por ejemplo, **ClaimsPrincpal**, para las necesidades de la aplicación, como la implementación de autorización correspondiente.  
  
 A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework. Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en .NET, lo que facilita el uso de notificaciones. Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones. Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.  
  
 El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente. Microsoft ofrece dos STS estándar del sector:  
  
-   [Servicios de federación de Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) ()http://go.microsoft.com/fwlink/?LinkID=247516)  
  
-   [Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).  
  
 AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales. ACS es un servicio de nube que se ofrece como parte de la plataforma Microsoft Azure. Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones. Por ejemplo, puede usar el STS de desarrollo Local que forma parte de la [Identity and Access Tool para Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) que está disponible de forma gratuita en línea.  
  
 Para compilar la primera aplicación ASP.NET compatible con notificaciones mediante WIF, siga las instrucciones de uno de los sitios siguientes:  
  
-   [Crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [Crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [Compilar aplicaciones ASP.NET para notificaciones mediante la autenticación basada en formularios](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a>Vea también  
 [Introducción a WIF](../../../docs/framework/security/getting-started-with-wif.md)
