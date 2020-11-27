---
title: Introducción a la autenticación HTTP
description: Revise esta introducción a la autenticación HTTP en WCF, incluidos los esquemas de autenticación HTTP y la elección de un esquema de autenticación.
ms.date: 03/30/2017
ms.assetid: 9376309a-39e3-4819-b47b-a73982b57620
ms.openlocfilehash: 65ccde358f4eb8727e59ca32fb9782b87e29c5c1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293525"
---
# <a name="understanding-http-authentication"></a>Introducción a la autenticación HTTP

La autenticación es el proceso de identificar si un cliente es elegible para tener acceso a un recurso. El protocolo HTTP soporta la autenticación como un medio de negociar el acceso a un recurso seguro.  
  
 La solicitud inicial de un cliente es normalmente una solicitud anónima, que no contiene ninguna información de autenticación. Las aplicaciones de servidor HTTP pueden denegar la solicitud anónima indicando que se requiere la autenticación. La aplicación de servidor envía encabezados de la autenticación de WWW para indicar los esquemas de autenticación soportados. En este documento se describen varios esquemas de autenticación para HTTP y se describe su compatibilidad en Windows Communication Foundation (WCF).  
  
## <a name="http-authentication-schemes"></a>Esquemas de autenticación HTTP  

 El servidor puede especificar múltiples esquemas de autenticación para que el cliente elija uno de ellos. En la tabla siguiente se describen algunos de los esquemas de autenticación que pueden encontrarse habitualmente en las aplicaciones de Windows.  
  
|Esquema de autenticación|Descripción|  
|---------------------------|-----------------|  
|Anónimas|Una solicitud anónima no contiene ninguna información de autenticación. Esto equivale a conceder acceso al recurso a todo el mundo.|  
|Básico|La autenticación básica envía una cadena codificada por Base64 que contiene un nombre de usuario y contraseña para el cliente. Base64 no es una forma de cifrado y debe considerarse igual que enviar el nombre de usuario y contraseña en texto no cifrado. Si un recurso necesita ser protegido, considere fervientemente utilizar un esquema de autenticación distinto de la autenticación básica.|  
|Digest|La autenticación implícita es un esquema de desafío-respuesta destinado a reemplazar a la autenticación básica. El servidor envía una cadena de datos aleatorios denominada un valor de seguridad ( *nonce* ) al cliente como un desafío. El cliente responde con un hash que incluye el nombre de usuario, contraseña y valor de seguridad, entre otra información adicional. La complejidad que introduce este intercambio y el hash de datos hacen que sea más difícil robar y reutilizar las credenciales del usuario con este esquema de autenticación.<br /><br /> La autenticación implícita requiere el uso de cuentas de dominio de Windows. El dominio *de síntesis es* el nombre de dominio de Windows. Por consiguiente, no puede utilizar un servidor que se ejecute en un sistema operativo que no admita los dominios de Windows, como Windows XP Home Edition, con autenticación implícita. A la inversa, cuando el cliente se ejecuta en un sistema operativo que no admite los dominios de Windows, una cuenta de dominio se debe especificar explícitamente durante la autenticación.|  
|NTLM|La autenticación de NT LAN Manager (NTLM) es un esquema de desafío-respuesta que es una variación más segura de la autenticación implícita. NTLM utiliza las credenciales de Windows para transformar los datos del desafío en lugar del nombre de usuario descodificado y contraseña. La autenticación NTLM requiere varios intercambios entre el cliente y servidor. El servidor y cualquier proxy que intervenga deben admitir las conexiones persistentes para completar correctamente la autenticación.|  
|Negotiate|Negociar la autenticación automáticamente selecciona entre el protocolo Kerberos y la autenticación NTLM, dependiendo de la disponibilidad. Se utiliza el protocolo Kerberos si está disponible; de lo contrario, se prueba NTLM. La autenticación Kerberos mejora significativamente en NTLM. La autenticación Kerberos es más rápido que NTLM y además permite el uso de autenticación mutua y delegación de credenciales a los equipos remotos.|  
|Windows Live ID|El servicio HTTP de Windows subyacente incluye autenticación mediante los protocolos federados. Sin embargo, los transportes HTTP estándar en WCF no admiten el uso de esquemas de autenticación federados, como Microsoft Windows Live ID. La compatibilidad para esta característica está actualmente disponible a través del uso de la seguridad de mensajes. Para obtener más información, vea [Federación y tokens emitidos](federation-and-issued-tokens.md).|  
  
## <a name="choosing-an-authentication-scheme"></a>Elegir un esquema de autenticación  

 Al seleccionar los esquemas de autenticación potenciales para un servidor HTTP, deben considerarse algunos elementos, como los siguientes:  
  
- Considere si el recurso necesita ser protegido. La utilización de la autenticación de HTTP requiere transmitir más datos y puede limitar la interoperabilidad con los clientes. Permita el acceso anónimo a los recursos que no necesitan ser protegidos.  
  
- Si el recurso necesita ser protegido, considere qué esquemas de autenticación proporcionan el nivel necesario de seguridad. El esquema de autenticación estándar más débil aquí descrito es la autenticación básica. La autenticación básica no protege las credenciales del usuario. El esquema de autenticación estándar más fuerte es Negociar la autenticación, que resulta en el protocolo Kerberos.  
  
- Un servidor no debería presentar (en los encabezados de la autenticación de WWW) ningún esquema que no esté preparado para aceptar o que no proteja adecuadamente el recurso protegido. Los clientes son libres de elegir entre cualquiera de los esquemas de autenticación que el servidor presenta. Algunos clientes tienen como valor predeterminado un esquema de autenticación débil o el primer esquema de autenticación en la lista del servidor.  
  
## <a name="see-also"></a>Vea también

- [Información general de la seguridad del transporte](transport-security-overview.md)
- [Utilización de la suplantación con la seguridad de transporte](using-impersonation-with-transport-security.md)
- [Delegación y suplantación](delegation-and-impersonation-with-wcf.md)
