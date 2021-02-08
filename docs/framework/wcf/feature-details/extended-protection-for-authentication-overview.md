---
description: 'Más información sobre: información general sobre protección ampliada para la autenticación'
title: Información general sobre la protección extendida para la autenticación
ms.date: 03/30/2017
ms.assetid: 3d2ceffe-a7bf-4bd9-a5a2-9406423bd7f8
ms.openlocfilehash: 5f79092d71266176af3916e919be0018793959ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780276"
---
# <a name="extended-protection-for-authentication-overview"></a>Información general sobre la protección extendida para la autenticación

La protección extendida para la autenticación ayuda a protegerse de los ataques de tipo "man-in-the-middle" (MITM), en los que un atacante intercepta las credenciales de un cliente y las reenvía a un servidor.  
  
 Considere un escenario con tres participantes: un cliente, un servidor y un atacante. El servidor tiene la dirección URL `https://server`, mientras que el atacante tiene la dirección URL `https://attacker`. El atacante engaña al cliente para que este tenga acceso a él como si fuese el servidor. A continuación, el atacante envía una solicitud al servidor. Si el atacante intenta tener acceso a un recurso seguro, el servidor le responde con un encabezado WWW-Authenticate. El atacante no dispone de la información de autenticación, por lo que envía el encabezado WWW-Authenticate al cliente. El cliente envía el encabezado de autorización al atacante, y este lo envía a su vez al servidor, obteniendo así acceso a los recursos seguros mediante las credenciales del cliente.  
  
 Actualmente, cuando una aplicación cliente se autentica ante el servidor mediante Kerberos, Digest o NTLM usando HTTPS, se establece en primer lugar un canal de seguridad de nivel de transporte (TLS) y la autenticación se lleva a cabo usando dicho canal. Sin embargo, no hay ningún enlace entre la clave de sesión generada por la Capa de sockets seguros (SSL) y la clave de sesión generada durante la autenticación. Por lo tanto, en el escenario anterior, si la comunicación se lleva a cabo en un canal TLS (por ejemplo, un canal HTTPS), se crean dos canales SSL: uno entre el cliente y el atacante, y otro entre este y el servidor. Las credenciales del cliente se envían desde este al servidor primero sobre el canal SSL abierto entre el cliente y el atacante, y luego sobre el canal abierto entre este y el servidor. Cuando dichas credenciales alcanzan el servidor, este las comprueba sin detectar que el canal sobre el que se enviaron tiene su origen en el atacante, no en el cliente.  
  
 La solución consiste en usar un canal externo seguro para TLS y un canal interno autenticado con el cliente, así como en pasar un token de enlace de canal (CBT) al servidor. El CBT es una propiedad del canal externo seguro para TLS, y se usa para enlazar el canal externo a una conversación sobre el canal interno autenticado con el cliente.  
  
 En el escenario anterior, el CBT del canal TLS cliente-atacante se combina con la información de autorización que se envía al servidor. Un servidor compatible con CBT compara el CBT incluido en la información de autenticación del cliente, que corresponde al canal cliente-atacante, con el CBT adjuntado al canal atacante-servidor. El CBT es específico del destino de un canal, por lo que el CBT cliente-atacante no coincide con el CBT atacante-servidor. Esto permite al servidor detectar el ataque MITM y rechazar la solicitud de autenticación.  
  
 El lado de cliente no requiere ningún valor de configuración. Una vez que el cliente se ha actualizado para pasar el CBT al servidor, lo hará siempre. Si el servidor también se ha actualizado, es posible configurarlo para que use el CBT o lo ignore. Si no se ha actualizado, lo ignorará.  
  
 El servidor puede tener los niveles de protección siguientes:  
  
- Ninguno. No se realiza ninguna validación de enlace de canal. Este es el comportamiento de todos los servidores que no se han actualizado.  
  
- Parcial. Todos los clientes que se han actualizado deben proporcionar información de enlace de canal al servidor. No es obligatorio para los clientes que no se han actualizado. Esta es una opción intermedia que permite la compatibilidad entre aplicaciones.  
  
- Completo. Todos los clientes deben proporcionar información de enlace de canal. El servidor rechazará las solicitudes de autenticación de los clientes que no lo hagan.  
  
 Para obtener más información, vea el ejemplo de protección extendida/CBT para Windows 7.  
  
## <a name="see-also"></a>Vea también

- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
