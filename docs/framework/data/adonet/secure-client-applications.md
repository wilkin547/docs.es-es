---
description: 'Más información sobre: aplicaciones cliente seguras'
title: Aplicaciones cliente seguras
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: a40a6444c2e317b03f03688ca46de157ded6f0ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718959"
---
# <a name="secure-client-applications"></a>Aplicaciones cliente seguras

Por lo general las aplicaciones constan de varios elementos que deben estar protegidos ante las vulnerabilidades que pueden provocar pérdidas de datos o poner en peligro el sistema de cualquier otro modo. La creación de interfaces de usuario seguras puede impedir un gran número de problemas ya que bloquea a los atacantes antes de que puedan tener acceso a los datos o a los recursos del sistema.  
  
## <a name="validate-user-input"></a>Validar datos introducidos por el usuario  

 Al construir una aplicación en la que se obtiene acceso a datos, debe presuponer que todos los datos proporcionados por el usuario son malintencionados, a no ser que se demuestre lo contrario. De no ser así, la aplicación puede estar expuesta a ataques. .NET Framework contiene clases que ayudan a exigir un dominio de valores para los controles de información introducida por el usuario, como la limitación del número de caracteres que se pueden introducir. Los enlaces de eventos permiten escribir procedimientos para comprobar la validez de los valores. Los datos introducidos por el usuario se pueden validar y tipar fuertemente, lo que limita la exposición de una aplicación ante ataques de inyección de script y SQL.  
  
> [!IMPORTANT]
> También debe validar los datos introducidos por el usuario en el origen de datos, además de la aplicación cliente. Un atacante puede evitar la aplicación y atacar directamente al origen de datos.  
  
 [Seguridad e introducción de datos por el usuario](../../../standard/security/security-and-user-input.md)  
 Describe cómo controlar errores sutiles y potencialmente peligrosos relacionados con la introducción de datos por parte del usuario.  
  
 [Validación de la entrada del usuario en ASP.NET Web Pages](/previous-versions/aspnet/7kh55542(v=vs.100))  
 Información general sobre la validación de datos introducidos por el usuario con controles de validación de ASP.NET.  
  
 [Datos proporcionados por el usuario en Windows Forms](/dotnet/desktop/winforms/user-input-in-windows-forms)  
 Proporciona vínculos e información para validar entrada de mouse y teclado en aplicaciones de Windows Forms.  
  
 [Expresiones regulares de .NET Framework](../../../standard/base-types/regular-expressions.md)  
 Describe cómo utilizar la clase <xref:System.Text.RegularExpressions.Regex> para comprobar la validez de los datos introducidos por el usuario.  
  
## <a name="windows-applications"></a>Aplicaciones para Windows  

 En versiones anteriores, las aplicaciones Windows normalmente se ejecutaban con todos los permisos. .NET Framework proporciona la infraestructura para restringir la ejecución del código en una aplicación Windows mediante la seguridad de acceso del código (CAS). Sin embargo, CAS no es suficiente por sí solo para proteger la aplicación.  
  
 [Seguridad de Windows Forms](/dotnet/desktop/winforms/windows-forms-security)  
 Describe cómo proteger las aplicaciones de Windows Forms y proporciona vínculos a temas relacionados.  
  
 [Aplicaciones de Windows Forms y aplicaciones no administradas](/dotnet/desktop/winforms/advanced/windows-forms-and-unmanaged-applications)  
 Describe cómo interactuar con aplicaciones no administradas en una aplicación de Windows Forms.  
  
 [Implementación de ClickOnce para Windows Forms](/dotnet/desktop/winforms/clickonce-deployment-for-windows-forms)  
 Describe cómo usar la implementación de `ClickOnce` en una aplicación de Windows Forms y describe las implicaciones en la seguridad.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET y servicios Web XML  

 Por lo general, las aplicaciones ASP.NET deben restringir el acceso a algunas porciones del sitio web y proporcionan otros mecanismos para la protección de datos y la seguridad del sitio. Estos vínculos proporcionan información útil para proteger la aplicación ASP.NET.  
  
 Los servicios Web XML proporcionan datos que pueden consumir las aplicaciones ASP.NET, las aplicaciones de Windows Forms u otros servicios Web. Debe administrar la seguridad del propio servicio Web así como la de la aplicación cliente.  
  
 Para obtener más información, vea los recursos siguientes.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Protección de sitios web de ASP.NET](/previous-versions/aspnet/91f66yxt(v=vs.100))|Describe cómo proteger aplicaciones ASP.NET.|  
|[Proteger servicios Web XML creados con ASP.NET](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))|Describe cómo implementar la seguridad en un servicio Web ASP.NET.|  
|[Introducción a los ataques de scripts](/previous-versions/aspnet/w1sw53ds(v=vs.100))|Describe cómo protegerse ante ataques de script, que intentan insertar caracteres malintencionados en una página web.|  
|[Prácticas de seguridad básicas para aplicaciones web](/previous-versions/aspnet/zdh19h94(v=vs.100))|Información general sobre la seguridad y vínculos para profundizar en el tema.|  
  
## <a name="remoting"></a>Comunicación remota  

 La comunicación remota de .NET permite crear fácilmente aplicaciones ampliamente distribuidas, tanto si los componentes de las aplicaciones están todos en un equipo como si están repartidos por el mundo. Puede generar aplicaciones cliente que utilizan los objetos de otros procesos en el mismo equipo o en cualquier otro equipo que se puede alcanzar a través de su red. También puede usar .NET Remoting para comunicar con otros dominios de aplicación en el mismo proceso.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Configuración de aplicaciones remotas](/previous-versions/dotnet/netframework-4.0/b8tysty8(v=vs.100))|Describe cómo configurar aplicaciones de comunicación remota para evitar problemas habituales.|  
|[Seguridad en comunicación remota](/previous-versions/dotnet/netframework-4.0/9hwst9th(v=vs.100))|Describe la autenticación y el cifrado, así como temas adicionales de seguridad relacionados con la comunicación remota.|  
|[Consideraciones de seguridad y de interacción remota](../../misc/security-and-remoting-considerations.md)|Describe problemas de seguridad con objetos protegidos y con el cruce entre dominios de aplicación.|  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)
- [Recomendaciones para las estrategias de acceso a datos](/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Protección de aplicaciones](/visualstudio/ide/securing-applications)
- [Proteger la información de conexión](protecting-connection-information.md)
- [Información general de ADO.NET](ado-net-overview.md)
