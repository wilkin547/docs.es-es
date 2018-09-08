---
title: Aplicaciones cliente seguras
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: a3b035d59a39ca20f6a81fbd40d39069a7cc43c2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208561"
---
# <a name="secure-client-applications"></a>Aplicaciones cliente seguras
Por lo general las aplicaciones constan de varios elementos que deben estar protegidos ante las vulnerabilidades que pueden provocar pérdidas de datos o poner en peligro el sistema de cualquier otro modo. La creación de interfaces de usuario seguras puede impedir un gran número de problemas ya que bloquea a los atacantes antes de que puedan tener acceso a los datos o a los recursos del sistema.  
  
## <a name="validate-user-input"></a>Validar datos introducidos por el usuario  
 Al construir una aplicación en la que se obtiene acceso a datos, debe presuponer que todos los datos proporcionados por el usuario son malintencionados, a no ser que se demuestre lo contrario. De no ser así, la aplicación puede estar expuesta a ataques. .NET Framework contiene clases que ayudan a exigir un dominio de valores para los controles de información introducida por el usuario, como la limitación del número de caracteres que se pueden introducir. Los enlaces de eventos permiten escribir procedimientos para comprobar la validez de los valores. Los datos introducidos por el usuario se pueden validar y tipar fuertemente, lo que limita la exposición de una aplicación ante ataques de inyección de script y SQL.  
  
> [!IMPORTANT]
>  También debe validar los datos introducidos por el usuario en el origen de datos, además de la aplicación cliente. Un atacante puede evitar la aplicación y atacar directamente al origen de datos.  
  
 [Seguridad e introducción de datos por el usuario](../../../../docs/standard/security/security-and-user-input.md)  
 Describe cómo controlar errores sutiles y potencialmente peligrosos relacionados con la introducción de datos por parte del usuario.  
  
 [Validar la entrada del usuario en ASP.NET Web Pages](https://msdn.microsoft.com/library/4ad3dacb-89e0-4cee-89ac-40a3f2a85461)  
 Información general sobre la validación de datos introducidos por el usuario con controles de validación de ASP.NET.  
  
 [Datos proporcionados por el usuario en Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 Proporciona vínculos e información para validar entrada de mouse y teclado en aplicaciones de Windows Forms.  
  
 [Expresiones regulares de .NET Framework](../../../../docs/standard/base-types/regular-expressions.md)  
 Describe cómo utilizar la clase <xref:System.Text.RegularExpressions.Regex> para comprobar la validez de los datos introducidos por el usuario.  
  
## <a name="windows-applications"></a>Aplicaciones para Windows  
 En versiones anteriores, las aplicaciones Windows normalmente se ejecutaban con todos los permisos. .NET Framework proporciona la infraestructura para restringir la ejecución del código en una aplicación Windows mediante la seguridad de acceso del código (CAS). Sin embargo, CAS no es suficiente por sí solo para proteger la aplicación.  
  
 [Windows Forms Security](../../../../docs/framework/winforms/windows-forms-security.md)  
 Describe cómo proteger las aplicaciones de Windows Forms y proporciona vínculos a temas relacionados.  
  
 [Aplicaciones de Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 Describe cómo interactuar con aplicaciones no administradas en una aplicación de Windows Forms.  
  
 [Las aplicaciones de implementación de ClickOnce para Windows Forms](https://msdn.microsoft.com/library/34d8c770-48f2-460c-8d67-4ea5684511df)  
 Describe cómo usar la implementación de `ClickOnce` en una aplicación de Windows Forms y describe las implicaciones en la seguridad.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET y servicios Web XML  
 Por lo general, las aplicaciones ASP.NET deben restringir el acceso a algunas porciones del sitio web y proporcionan otros mecanismos para la protección de datos y la seguridad del sitio. Estos vínculos proporcionan información útil para proteger la aplicación ASP.NET.  
  
 Los servicios Web XML proporcionan datos que pueden consumir las aplicaciones ASP.NET, las aplicaciones de Windows Forms u otros servicios Web. Debe administrar la seguridad del propio servicio Web así como la de la aplicación cliente.  
  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[NIB: Seguridad de ASP.NET](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d)|Describe cómo proteger aplicaciones ASP.NET.|  
|[Protección de servicios Web XML creados con ASP.NET](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c)|Describe cómo implementar la seguridad en un servicio Web ASP.NET.|  
|[Información general de vulnerabilidades de seguridad de secuencia de comandos](https://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|Describe cómo protegerse ante ataques de script, que intentan insertar caracteres malintencionados en una página web.|  
|[NIB: Basic prácticas de seguridad para aplicaciones Web ASP.NET](https://msdn.microsoft.com/library/94a52ab8-731d-417e-b997-721baf43df38)|Información general sobre la seguridad y vínculos para profundizar en el tema.|  
  
## <a name="remoting"></a>Comunicación remota  
 La comunicación remota de .NET permite crear fácilmente aplicaciones ampliamente distribuidas, tanto si los componentes de las aplicaciones están todos en un equipo como si están repartidos por el mundo. Puede generar aplicaciones cliente que utilizan los objetos de otros procesos en el mismo equipo o en cualquier otro equipo que se puede alcanzar a través de su red. También puede usar .NET Remoting para comunicar con otros dominios de aplicación en el mismo proceso.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Configuración de aplicaciones remotas](https://msdn.microsoft.com/library/92c0c097-d984-4315-835b-7490ecdf1097)|Describe cómo configurar aplicaciones de comunicación remota para evitar problemas habituales.|  
|[Seguridad en la comunicación remota](https://msdn.microsoft.com/library/9574262c-d4b1-41c5-8600-24ff147c0add)|Describe la autenticación y el cifrado, así como temas adicionales de seguridad relacionados con la comunicación remota.|  
|[Consideraciones de seguridad y comunicación remota](../../../../docs/framework/misc/security-and-remoting-considerations.md)|Describe problemas de seguridad con objetos protegidos y con el cruce entre dominios de aplicación.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Recomendaciones de estrategias de acceso a datos](https://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [Proteger aplicaciones](/visualstudio/ide/securing-applications)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
