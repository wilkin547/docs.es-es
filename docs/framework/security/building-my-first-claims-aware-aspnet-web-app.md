---
title: Crear mi primera aplicación web de ASP.NET para notificaciones
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 900ee49b4bf51eeb6e3b0c0cf6879cc12a0cb071
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045590"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a>Crear mi primera aplicación web de ASP.NET para notificaciones
## <a name="applies-to"></a>Se aplica a  
  
- Windows Identity Foundation (WIF)  
  
- ASP.NET  
  
 En este tema se describe el escenario de compilación de aplicaciones web ASP.NET compatibles con notificaciones mediante WIF. En un escenario de aplicación compatible con notificaciones suele haber tres participantes: la propia aplicación, el usuario final y el servicio de token de seguridad (STS). En la ilustración siguiente se describe este escenario:  
  
 ![Diagrama que muestra los componentes básicos de una aplicación Web de WIF.](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1. La aplicación para notificaciones usa WIF para identificar las solicitudes no autenticadas y redirigirlas al STS.  
  
2. El usuario final proporciona las credenciales al STS y, tras su correcta autenticación, el STS emite un token para el usuario.  
  
3. Se redirige al usuario del STS a la aplicación para notificaciones con el token emitido por el STS en la solicitud.  
  
4. La aplicación para notificaciones se configura para confiar en el STS y en los token que emite. Asimismo, dicha aplicación usa WIF para validar el token y analizarlo. Los desarrolladores usan la API y los tipos de WIF adecuados, por ejemplo, **ClaimsPrincipal**, para las necesidades de la aplicación, como la implementación de autorización correspondiente.  
  
 A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework. Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en .NET, lo que facilita el uso de notificaciones. Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones. Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.  
  
 El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente. Microsoft ofrece dos STS estándar del sector:  
  
- [Servicios de federación de Active Directory (AD FS) (AD FS) 2,0](https://go.microsoft.com/fwlink/?LinkID=247516)
  
- [Access Control Service de Windows Azure (ACS)](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales. ACS es un servicio de nube que se ofrece como parte de la plataforma Microsoft Azure. Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones. Por ejemplo, puede usar el STS de desarrollo local que forma parte de la [herramienta de identidad y acceso para Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) , que está disponible en línea de forma gratuita.  
  
 Para compilar la primera aplicación ASP.NET compatible con notificaciones mediante WIF, siga las instrucciones de uno de los sitios siguientes:  
  
- [Cómo: Compilación de una aplicación web MVC de ASP.NET compatible con notificaciones mediante WIF](how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
- [Cómo: Creación de una aplicación de formularios Web Forms ASP.NET compatible con notificaciones mediante WIF](how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
- [Cómo: Creación de una aplicación ASP.NET compatible con notificaciones mediante la autenticación basada en formularios](claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a>Vea también

- [Introducción a WIF](getting-started-with-wif.md)
