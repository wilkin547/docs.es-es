---
title: Proteger WCF Data Services
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- securing application [WCF Data Services]
- WCF Data Services, security
ms.assetid: 99fc2baa-a040-4549-bc4d-f683d60298af
ms.openlocfilehash: 56ece9c2c81f05047e85ab681e7cfe0da65f35b9
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839586"
---
# <a name="securing-wcf-data-services"></a>Proteger WCF Data Services
En este tema se describen consideraciones de seguridad específicas del desarrollo. de la implementación y la ejecución de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] y de aplicaciones que acceden a servicios compatibles con [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. También debe seguir las recomendaciones para crear aplicaciones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] seguras.  
  
 Cuando planee cómo proteger un servicio de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], debe tratar tanto la autenticación, el proceso para detectar y comprobar la identidad de una entidad de seguridad, como la autorización, el proceso para determinar si una entidad de seguridad autenticada puede acceder a los recursos solicitados. También debe plantearse si va a cifrar el mensaje mediante SSL.  
  
## <a name="authenticating-client-requests"></a>Autenticar las solicitudes de clientes  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no implementa ningún tipo de autenticación proprio, sino que confía en las medidas de autenticación del host de servicio de datos. Es decir, el servicio asume que cualquier solicitud recibida ya la ha autenticado el host de red y que este ha identificado correctamente la entidad de seguridad para la solicitud adecuadamente a través de las interfaces proporcionadas por [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Estas opciones de autenticación y enfoques se describen en [OData y autenticación](https://go.microsoft.com/fwlink/?LinkId=200381).  
  
### <a name="authentication-options-for-a-wcf-data-service"></a>Opciones de autenticación para un servicio de datos de WCF  
 En la siguiente tabla se enumeran algunos de los mecanismos de autenticación disponibles para ayudar al usuario a autenticar solicitudes en el servicio de datos de WCF.  
  
|Opciones de autenticación|Descripción|  
|----------------------------|-----------------|  
|Autenticación anónima|Cuando está habilitada la autenticación HTTP anónima, cualquier entidad de seguridad puede conectarse al servicio de datos. No se necesitan credenciales para el acceso anónimo. Use esta opción solo cuando desee permitir a alguien el acceso al servicio de datos.|  
|Autenticación básica e implícita|Se necesitan credenciales formadas por un nombre de usuario y una contraseña para la autenticación. Admite autenticación de clientes que no sean de Windows. **Nota de seguridad:** las credenciales de autenticación básica (nombre de usuario y contraseña) se envían sin cifrar y se pueden interceptar. La autenticación implícita envía un hash basado en las credenciales proporcionadas. De esta forma, la protección es mayor que la de la autenticación básica. Ambas son susceptibles de sufrir ataques de tipo " Man in the middle". Cuando se usan estos métodos de autenticación, debe plantearse la comunicación cifrada entre el cliente y el servicio de datos mediante el uso de la Capa de sockets seguros (SSL). <br /><br /> Microsoft Internet Information Services (IIS) proporciona una implementación de la autenticación tanto básica como implícita para solicitudes HTTP en una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Esta implementación del proveedor de autenticación de Windows permite que una aplicación cliente de .NET Framework proporcione credenciales en el encabezado HTTP de la solicitud al servicio de datos para negociar sin ningún problema la autenticación de un usuario de Windows. Para obtener más información, consulte [referencia técnica de autenticación implícita](https://go.microsoft.com/fwlink/?LinkId=200408).<br /><br /> Cuando desee que el servicio de datos use la autenticación básica basada en algún servicio de autenticación personalizado y no en las credenciales de Windows, debe implementar un módulo HTTP de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] personalizado para autenticación.<br /><br /> Para obtener un ejemplo de cómo usar un esquema de autenticación básica personalizada con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vea la entrada en [autenticación básica personalizada](https://go.microsoft.com/fwlink/?LinkID=200388) en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y autenticación.|  
|Autenticación de Windows|Las credenciales basadas en Windows se intercambian mediante el uso de NTLM o Kerberos. Este mecanismo es más seguro que la autenticación básica o implícita, pero requiere que el cliente sea una aplicación basada en Windows. IIS también proporciona una implementación de autenticación de Windows para solicitudes HTTP en una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Para obtener más información, consulte [información general sobre la autenticación de formularios ASP.NET](https://msdn.microsoft.com/library/099c1587-6934-476e-ac95-28f534bc9708).<br /><br /> Para obtener un ejemplo de cómo usar la autenticación de Windows con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vea la entrada en [Windows autenticación](https://go.microsoft.com/fwlink/?LinkID=200384) en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y autenticación.|  
|Autenticación de formularios de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]|La autenticación de formularios permite autenticar a los usuarios mediante su propio código y, a continuación, conservar un token de autenticación en una cookie o en la dirección URL de la página. Autentique el nombre de usuario y la contraseña de los usuarios que usen un formulario de inicio de sesión que cree. Las solicitudes no autenticadas se redirigen a una página de inicio de sesión, en la que el usuario proporciona las credenciales y envía el formulario. Si la aplicación autentica la solicitud, el sistema emite un vale que contiene una clave con el fin de restablecer la identidad para posteriores solicitudes. Para obtener más información, consulte [proveedor de autenticación de formularios](https://msdn.microsoft.com/library/77e21ba2-bad1-4967-a8ec-74942dea7e47). **Nota de seguridad:** de forma predeterminada, la cookie que contiene el vale de autenticación de formularios no está protegida cuando se usa la autenticación de formularios en un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación Web. Debe plantearse exigir SSL para proteger tanto el vale de autenticación como las credenciales de inicio de sesión iniciales. <br /><br /> Para un ejemplo de cómo utilizar autenticación de formularios con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vea la entrada en [autenticación mediante formularios](https://go.microsoft.com/fwlink/?LinkID=200389) en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y autenticación.|  
|Autenticación basada en notificaciones|En la autenticación basada en notificaciones, el servicio de datos se basa en un servicio de proveedor de identidades de confianza "terceros" para autenticar al usuario. El proveedor de identidad autentica positivamente al usuario que solicita acceso a los recursos del servicio de datos y emite un token que concede acceso a los recursos solicitados. A continuación, este token se presenta en el servicio de datos, que concede acceso al usuario basándose en la relación de confianza con el servicio de identidad que emitió el token de acceso.<br /><br /> La ventaja de usar un proveedor de autenticación basado en notificaciones es que se pueden usar para autenticar distintos tipos de clientes en dominios de confianza. Si se usan tales proveedores de terceros, un servicio de datos puede descargar los requisitos de mantenimiento y autenticación de usuarios. OAuth 2.0 es un protocolo de autenticación basado en notificaciones compatible con el Control de acceso de AppFabric de Microsoft Azure para autorización federada como servicio. Este protocolo admite servicios basados en REST. Para obtener un ejemplo de cómo usar OAuth 2.0 con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vea la entrada en [OData y OAuth](https://go.microsoft.com/fwlink/?LinkId=200514) en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y autenticación.|  
  
<a name="clientAuthentication"></a>   
### <a name="authentication-in-the-client-library"></a>Autenticación de la biblioteca cliente  
 De forma predeterminada, la biblioteca de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no proporciona credenciales cuando se realiza una solicitud a un servicio de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Cuando el servicio de datos necesita credenciales de inicio de sesión para autenticar a un usuario, estas credenciales se puedan proporcionar en una clase <xref:System.Net.NetworkCredential> a la que se accede desde la propiedad <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>, como en el ejemplo siguiente:  
  
```csharp  
// Set the client authentication credentials.  
context.Credentials =  
    new NetworkCredential(userName, password, domain);  
```  
  
```vb  
' Set the client authentication credentials.  
context.Credentials = _  
    New NetworkCredential(userName, password, domain)  
```  
  
 Para obtener más información, consulte [Cómo: especificar las credenciales del cliente para una solicitud de servicio de datos](../../../../docs/framework/data/wcf/specify-client-creds-for-a-data-service-request-wcf.md).  
  
 Cuando el servicio de datos necesite credenciales de inicio de sesión que no se puedan especificar mediante el uso de un objeto <xref:System.Net.NetworkCredential>, como un token basado en notificaciones o una cookie, debe establecer manualmente los encabezados en la solicitud HTTP, que suelen ser los encabezados `Authorization` y `Cookie`. Para obtener más información sobre este tipo de escenario de autenticación, vea la entrada [OData y autenticación: enlaces del lado cliente](https://go.microsoft.com/fwlink/?LinkID=200385). Para obtener un ejemplo de cómo establecer los encabezados HTTP en un mensaje de solicitud, consulte [Cómo: establecer encabezados en la solicitud de cliente](../../../../docs/framework/data/wcf/how-to-set-headers-in-the-client-request-wcf-data-services.md).  
  
## <a name="impersonation"></a>Suplantación  
 Por lo general, el servicio de datos accede a los recursos necesarios, como los archivos del servidor o de la base de datos, mediante el uso de las credenciales del proceso de trabajo que hospeda el servicio de datos. Al usar la suplantación, las aplicaciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se pueden ejecutar con la identidad de Windows (cuenta de usuario) del usuario que realiza la solicitud. La suplantación se suele usar en aplicaciones que confían en IIS para autenticar al usuario y las credenciales de esta entidad de seguridad se usan para obtener acceso a los recursos necesarios. Para obtener más información, consulte [suplantación de ASP.NET](https://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d).  
  
## <a name="configuring-data-service-authorization"></a>Configurar la autorización del servicio de datos  
 La autorización es la concesión de acceso a los recursos de la aplicación a una entidad de seguridad o a un proceso que se identifique basándose en una autenticación correcta previa. Como regla general, solo debe conceder los derechos estrictamente necesarios a los usuarios del servicio de datos para realizar las operaciones que necesiten las aplicaciones cliente.  
  
### <a name="restrict-access-to-data-service-resources"></a>Restringir el acceso a los recursos del servicio de datos  
 De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] permite conceder acceso común de lectura y escritura a los recursos del servicio de datos (conjunto de entidades y operaciones de servicio) a cualquier usuario que pueda acceder al servicio de datos. Las reglas que definen el acceso de lectura y escritura se pueden definir por separado para cada conjunto de entidades expuesto por el servicio de datos, así como a las operaciones de servicio. Se recomienda limitar el acceso tanto de lectura como de escritura a solo los recursos que necesite la aplicación cliente. Para obtener más información, consulte [requisitos mínimos de acceso a recursos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements).  
  
### <a name="implement-role-based-interceptors"></a>Implementar interceptores basados en roles  
 Los interceptores permiten interceptar solicitudes en los recursos del servicio de datos antes de que actúe en ellos dicho servicio. Para obtener más información, consulte [interceptores](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md). Los interceptores le permiten tomar decisiones de autorización basadas el usuario autenticado que está realizando la solicitud. Para obtener un ejemplo de cómo restringir el acceso a los recursos de servicio de datos en función de una identidad de usuario autenticado, vea [Cómo: interceptar mensajes de servicio de datos](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
### <a name="restrict-access-to-the-persisted-data-store-and-local-resources"></a>Restringir el acceso al almacén de datos persistentes y a los recursos locales  
 A las cuentas que se usan para acceder al almacén persistente se les deben conceder solo los derechos estrictamente necesarios en una base de datos o en el sistema de archivos para admitir los requisitos del servicio de datos. Cuando se usa la autenticación anónima, se trata de la cuenta usada para ejecutar la aplicación de hospedaje. Para obtener más información, consulta [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md). Cuando se usa la suplantación, a los usuarios autenticados se les debe conceder acceso a estos recursos, normalmente como parte de un grupo de Windows.  
  
## <a name="other-security-considerations"></a>Otras consideraciones de seguridad  
  
### <a name="secure-the-data-in-the-payload"></a>Proteger los datos de la carga  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] se basa en el protocolo HTTP. En un mensaje HTTP, el encabezado puede contener valiosas credenciales de usuario, en función de la autenticación implementada por el servicio de datos. El cuerpo del mensaje también puede contener datos valiosos de clientes que se deben proteger. En ambos casos, se recomienda que use SSL para proteger esta información a través de la conexión.  
  
### <a name="ignored-message-headers-and-cookies"></a>Cookies y encabezados del mensaje ignorados  
 Los encabezados de solicitudes HTTP, que no sean los que declaran los tipos de contenido y las ubicaciones de los recursos, se ignoran y nunca los establece el servicio de datos.  
  
 Las cookies se pueden usar como parte de un esquema de autenticación, por ejemplo, con la autenticación de los formularios de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ignora, sin embargo, las cookies HTTP establecidas en una solicitud entrante. El host de un servicio de datos puede procesar la cookie, pero el tiempo de ejecución de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] nunca analiza ni devuelve cookies. La biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] tampoco procesa las cookies enviadas en la respuesta.  
  
### <a name="custom-hosting-requirements"></a>Requisitos personalizados de hospedaje  
 De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se crea como aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospedada en IIS. De esta forma, el servicio de datos puede sacar provecho de los comportamientos seguros de esta plataforma. Puede definir los [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] hospedados por un host personalizado. Para obtener más información, consulte [hospeda el servicio de datos](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md). Los componentes y la plataforma que hospedan un servicio de datos deben asegurar los siguientes comportamientos de seguridad para impedir ataques contra el servicio de datos:  
  
-   Limitar la longitud del URI aceptada en una solicitud del servicio de datos para todas las operaciones posibles.  
  
-   Limitar el tamaño de los mensajes HTTP tanto entrantes como salientes.  
  
-   Limitar el número total de solicitudes pendientes en cualquier momento dado.  
  
-   Limitar la longitud de los encabezados HTTP y sus valores, así como proporcionar acceso a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] a los datos del encabezado.  
  
-   Detectar y contraatacar los ataques conocidos, como ataques SYN de TCP y de reproducción de mensajes.  
  
### <a name="values-are-not-further-encoded"></a>Los valores ya no se codifican  
 Los valores de propiedad enviados al servicio de datos ya no los codifica el tiempo de ejecución de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Por ejemplo, cuando una propiedad de cadena de una entidad contiene contenido HTML con formato, el servicio de datos no codifica las etiquetas en HTML. Además, el servicio de datos ya no codifica los valores de propiedad de la respuesta. Asimismo, la biblioteca cliente ya no efectúa ningún tipo de codificación adicional.  
  
### <a name="considerations-for-client-applications"></a>Consideraciones sobre aplicaciones cliente  
 Las consideraciones de seguridad siguientes se aplican a las aplicaciones que usan el cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para acceder a los servicios de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   La biblioteca cliente asume que los protocolos usados para acceder al servicio de datos proporcionan un nivel de seguridad adecuado.  
  
-   La biblioteca cliente usa todos los valores predeterminados para las opciones de tiempos de espera y de análisis de las pilas de transporte proporcionadas por la plataforma subyacente.  
  
-   La biblioteca cliente no lee la configuración a partir de los archivos de configuración de la aplicación.  
  
-   La biblioteca cliente no implementa los mecanismos de acceso entre dominios. En su lugar, confía en los mecanismos proporcionados por la pila HTTP subyacente.  
  
-   La biblioteca cliente no dispone de elementos de interfaz de usuario y nunca intenta mostrar o presentar los datos que recibe o envía.  
  
-   Se recomienda que las aplicaciones cliente siempre validen la entrada del usuario, así como los datos aceptados de servicios que no sean de confianza.  
  
## <a name="see-also"></a>Vea también  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
