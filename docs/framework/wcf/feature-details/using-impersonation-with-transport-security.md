---
title: Utilización de la suplantación con la seguridad de transporte
ms.date: 03/30/2017
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
ms.openlocfilehash: 14914bc65d5033c54640e06b79713ea1871daf18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289508"
---
# <a name="using-impersonation-with-transport-security"></a>Utilización de la suplantación con la seguridad de transporte

La *suplantación* es la capacidad de una aplicación de servidor de asumir la identidad del cliente. Es común que los servicios utilicen la suplantación al validar el acceso a los recursos. La aplicación de servidor se ejecuta utilizando una cuenta de servicio, pero cuando el servidor acepta una conexión de cliente, suplanta al cliente para que se realicen comprobaciones de acceso utilizando las credenciales del cliente. La seguridad de transporte es un mecanismo para pasar credenciales y proteger la comunicación mediante esas credenciales. En este tema se describe el uso de la seguridad de transporte en Windows Communication Foundation (WCF) con la característica de suplantación. Para obtener más información sobre la suplantación mediante la seguridad de mensajes, vea [delegación y suplantación](delegation-and-impersonation-with-wcf.md).  
  
## <a name="five-impersonation-levels"></a>Cinco niveles de suplantación  

 La seguridad de transporte utiliza cinco niveles de suplantación, como se describe en la siguiente tabla.  
  
|Nivel de suplantación|Descripción|  
|-------------------------|-----------------|  
|None|La aplicación de servidor no intenta suplantar al cliente.|  
|Anónimas|La aplicación de servidor puede realizar comprobaciones de acceso frente a las credenciales de cliente, pero no recibe ninguna información sobre la identidad del cliente. Este nivel de suplantación solo es significativo para la comunicación en equipo, como, por ejemplo, en canalizaciones con nombre. Al utilizar `Anonymous` con una conexión remota, se promueve el nivel de suplantación a identificar.|  
|Identificar|La aplicación de servidor conoce la identidad del cliente y puede realizar validación de acceso frente a las credenciales del cliente, pero no puede suplantar al cliente. Identificar es el nivel de suplantación predeterminado que se usa con las credenciales de SSPI en WCF a menos que el proveedor de tokens proporcione un nivel de suplantación diferente.|  
|Impersonate|La aplicación de servidor puede obtener acceso a recursos en el equipo del servidor como el cliente además de realizar las comprobaciones de acceso. La aplicación de servidor no puede tener acceso a los recursos en los equipos remotos utilizando la identidad del cliente porque el token suplantado no tiene credenciales de red.|  
|Delegado|Además de tener las mismas funciones que `Impersonate`, el nivel de suplantación de Delegar también permite a la aplicación de servidor obtener acceso a los recursos en los equipos remotos utilizando la identidad del cliente y pasar la identidad a otras aplicaciones.<br /><br /> **Importante** La cuenta de dominio del servidor debe estar marcada como de confianza para la delegación en el controlador de dominio para usar estas características adicionales. Este nivel de suplantación no se puede utilizar con cuentas de dominio de cliente marcadas como sensibles.|  
  
 Los niveles que se usan con mayor frecuencia con la seguridad de transporte son `Identify` y `Impersonate` . Los niveles `None` y `Anonymous` no se recomiendan para el uso general y muchos transportes no permiten el uso de esos niveles con autenticación. El nivel `Delegate` es una característica eficaz que se debe utilizar con cuidado. Solo se debe proporcionar el permiso de delegación de credenciales a las aplicaciones de servidor de confianza.  
  
 El uso de la suplantación en los niveles `Impersonate` o `Delegate` exige que la aplicación de servidor tenga el privilegio `SeImpersonatePrivilege`. Una aplicación tiene de forma predeterminada este privilegio si se está ejecutando en una cuenta del grupo Administradores o en una cuenta con un SID de Servicio (servicio de red, servicio local o sistema local). La suplantación no requiere autenticación mutua del cliente y el servidor. Algunos esquemas de autenticación que admiten la suplantación, como NTLM, no se pueden utilizar con autenticación mutua.  
  
## <a name="transport-specific-issues-with-impersonation"></a>Problemas específicos del transporte con suplantación  

 La elección de un transporte en WCF afecta a las posibles opciones de suplantación. En esta sección se describen los problemas que afectan a los transportes HTTP y de canalización con nombre estándar en WCF. Los transportes personalizados tienen sus propias restricciones sobre la compatibilidad con la suplantación.  
  
### <a name="named-pipe-transport"></a>Transporte de canalización con nombre  

 Los elementos siguientes se utilizan con el transporte de canalización con nombre:  
  
- El transporte de canalización con nombre solo está pensado para su uso en el equipo local. El transporte de canalización con nombre de WCF no permite explícitamente las conexiones entre equipos.  
  
- Las canalizaciones con nombre no se pueden utilizar con `Impersonate` o el nivel de suplantación `Delegate`. La canalización con nombre no puede exigir la garantía en equipo en estos niveles de suplantación.  
  
 Para obtener más información acerca de las canalizaciones con nombre, vea [elegir un transporte](choosing-a-transport.md).  
  
### <a name="http-transport"></a>Transporte HTTP  

 Los enlaces que utilizan el transporte HTTP ( <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.BasicHttpBinding> ) admiten varios esquemas de autenticación, como se explica en [Understanding http Authentication](understanding-http-authentication.md). El nivel de suplantación admitido depende del esquema de autenticación. Los elementos siguientes se utilizan con el transporte HTTP:  
  
- El esquema de autenticación `Anonymous` omite la suplantación.  
  
- El `Basic` esquema de autenticación solo admite el `Delegate` nivel. Todos los niveles de suplantación inferiores se actualizan.  
  
- El esquema de autenticación `Digest` solo admite los niveles `Impersonate` y `Delegate`.  
  
- El esquema de autenticación `NTLM`, que se puede seleccionar directamente o mediante negociación, solo admite el nivel `Delegate` en el equipo local.  
  
- El esquema de autenticación Kerberos, que solo se puede seleccionar mediante negociación, puede utilizarse con cualquier nivel de suplantación admitido.  
  
 Para obtener más información acerca del transporte HTTP, consulte [elección de un transporte](choosing-a-transport.md).  
  
## <a name="see-also"></a>Vea también

- [Delegación y suplantación](delegation-and-impersonation-with-wcf.md)
- [Autorización](authorization-in-wcf.md)
- [Procedimiento para suplantar a un cliente en un servicio](../how-to-impersonate-a-client-on-a-service.md)
- [Introducción a la autenticación HTTP](understanding-http-authentication.md)
