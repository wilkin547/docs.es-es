---
title: Utilización de la suplantación con la seguridad de transporte
ms.date: 03/30/2017
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
ms.openlocfilehash: 6209007b60effe5403caf3db8855f029d0c47a0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050680"
---
# <a name="using-impersonation-with-transport-security"></a>Utilización de la suplantación con la seguridad de transporte
*Suplantación* es la capacidad de una aplicación de servidor para asumir la identidad del cliente. Es común que los servicios utilicen la suplantación al validar el acceso a los recursos. La aplicación de servidor se ejecuta utilizando una cuenta de servicio, pero cuando el servidor acepta una conexión de cliente, suplanta al cliente para que se realicen comprobaciones de acceso utilizando las credenciales del cliente. La seguridad de transporte es un mecanismo para pasar credenciales y proteger la comunicación mediante esas credenciales. En este tema describe cómo utilizar la seguridad de transporte en Windows Communication Foundation (WCF) con la característica de suplantación. Para obtener más información sobre la suplantación con seguridad de mensajes, vea [delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="five-impersonation-levels"></a>Cinco niveles de suplantación  
 La seguridad de transporte utiliza cinco niveles de suplantación, como se describe en la siguiente tabla.  
  
|Nivel de suplantación|Descripción|  
|-------------------------|-----------------|  
|Ninguna|La aplicación de servidor no intenta suplantar al cliente.|  
|Anónimo|La aplicación de servidor puede realizar comprobaciones de acceso frente a las credenciales de cliente, pero no recibe ninguna información sobre la identidad del cliente. Este nivel de suplantación solo es significativo para la comunicación en equipo, como, por ejemplo, en canalizaciones con nombre. Al utilizar `Anonymous` con una conexión remota, se promueve el nivel de suplantación a identificar.|  
|Identificar|La aplicación de servidor conoce la identidad del cliente y puede realizar validación de acceso frente a las credenciales del cliente, pero no puede suplantar al cliente. Identificar es el nivel de suplantación predeterminado utilizado con credenciales SSPI en WCF, a menos que el proveedor de tokens proporciona un nivel de suplantación.|  
|Suplantar|La aplicación de servidor puede obtener acceso a recursos en el equipo del servidor como el cliente además de realizar las comprobaciones de acceso. La aplicación de servidor no puede tener acceso a los recursos en los equipos remotos utilizando la identidad del cliente porque el token suplantado no tiene credenciales de red.|  
|delegado|Además de tener las mismas funciones que `Impersonate`, el nivel de suplantación de Delegar también permite a la aplicación de servidor obtener acceso a los recursos en los equipos remotos utilizando la identidad del cliente y pasar la identidad a otras aplicaciones.<br /><br /> **Importante** la cuenta de dominio del servidor debe marcarse como de confianza para delegación en el controlador de dominio para usar estas características adicionales. Este nivel de suplantación no se puede utilizar con cuentas de dominio de cliente marcadas como sensibles.|  
  
 Los niveles más utilizados con la seguridad de transporte son `Identify` y `Impersonate`. Los niveles `None` y `Anonymous` no se recomiendan para el uso general y muchos transportes no permiten el uso de esos niveles con autenticación. El nivel `Delegate` es una característica eficaz que se debe utilizar con cuidado. Solo se debe proporcionar el permiso de delegación de credenciales a las aplicaciones de servidor de confianza.  
  
 El uso de la suplantación en los niveles `Impersonate` o `Delegate` exige que la aplicación de servidor tenga el privilegio `SeImpersonatePrivilege`. Una aplicación tiene de forma predeterminada este privilegio si se está ejecutando en una cuenta del grupo Administradores o en una cuenta con un SID de Servicio (servicio de red, servicio local o sistema local). La suplantación no requiere autenticación mutua del cliente y el servidor. Algunos esquemas de autenticación que admiten la suplantación, como NTLM, no se pueden utilizar con autenticación mutua.  
  
## <a name="transport-specific-issues-with-impersonation"></a>Problemas específicos del transporte con suplantación  
 La elección de un transporte de WCF afecta a las posibles opciones de suplantación. En esta sección se describe los problemas que afectan al HTTP estándar y transportes de canalización con en WCF. Los transportes personalizados tienen sus propias restricciones sobre la compatibilidad con la suplantación.  
  
### <a name="named-pipe-transport"></a>Transporte de canalización con nombre  
 Los elementos siguientes se utilizan con el transporte de canalización con nombre:  
  
- El transporte de canalización con nombre solo está pensado para su uso en el equipo local. El transporte de canalización con nombre en WCF impide explícitamente las conexiones entre equipos.  
  
- Las canalizaciones con nombre no se pueden utilizar con `Impersonate` o el nivel de suplantación `Delegate`. La canalización con nombre no puede exigir la garantía en equipo en estos niveles de suplantación.  
  
 Para obtener más información acerca de las canalizaciones con nombre, vea [elección del transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).  
  
### <a name="http-transport"></a>Transporte HTTP  
 Los enlaces que utilizan el transporte HTTP (<xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.BasicHttpBinding>) admiten varios esquemas de autenticación, como se explica en [descripción de la autenticación HTTP](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md). El nivel de suplantación admitido depende del esquema de autenticación. Los elementos siguientes se utilizan con el transporte HTTP:  
  
- El esquema de autenticación `Anonymous` omite la suplantación.  
  
- El `Basic` esquema de autenticación solo admite la `Delegate` nivel. Todos los niveles de suplantación inferiores se actualizan.  
  
- El esquema de autenticación `Digest` solo admite los niveles `Impersonate` y `Delegate`.  
  
- El esquema de autenticación `NTLM`, que se puede seleccionar directamente o mediante negociación, solo admite el nivel `Delegate` en el equipo local.  
  
- El esquema de autenticación Kerberos, que solo se puede seleccionar mediante negociación, puede utilizarse con cualquier nivel de suplantación admitido.  
  
 Para obtener más información sobre el transporte HTTP, consulte [elección del transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).  
  
## <a name="see-also"></a>Vea también

- [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
- [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [Cómo: Suplantar a un cliente en un servicio](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md)
- [Introducción a la autenticación HTTP](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)
