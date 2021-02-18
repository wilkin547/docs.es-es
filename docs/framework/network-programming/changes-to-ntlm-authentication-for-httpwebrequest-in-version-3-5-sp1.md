---
description: 'Más información acerca de: Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1'
title: Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1
ms.date: 03/30/2017
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
ms.openlocfilehash: 24787894d89f65024f7022a44b507c689bb0beb5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434854"
---
# <a name="changes-to-ntlm-authentication-for-httpwebrequest-in-version-35-sp1"></a>Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1

Se han realizado cambios de seguridad en .NET Framework versión 3.5 SP1 que afectan al modo en que las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream> y relacionadas del espacio de nombres System.Net controlan la autenticación integrada de Windows. Estos cambios pueden afectar a las aplicaciones que usan estas clases para realizar solicitudes web y recibir respuestas donde se emplea la autenticación integrada de Windows basada en NTLM. Este cambio puede afectar a los servidores web y a las aplicaciones cliente configurados para usar autenticación integrada de Windows.

## <a name="overview"></a>Información general

El diseño de la autenticación integrada de Windows permite que algunas respuestas de credenciales sean universales, lo que significa que se pueden volver a usar o reenviar. Si no se necesita esta característica de diseño concreta, los protocolos de autenticación deben incluir información específica de destino, así como información específica de canal. Entonces los servicios pueden proporcionar protección extendida para asegurarse de que las respuestas de credenciales contengan información específica de servicio, como un nombre de entidad de seguridad de servicio (SPN). Con esta información en los intercambios de credenciales, los servicios pueden mejorar la protección contra el uso malintencionado de respuestas de credenciales que podrían haberse obtenido de forma inapropiada.

Varios componentes de los espacios de nombres <xref:System.Net> y <xref:System.Net.Security> realizan la autenticación integrada de Windows en nombre de una aplicación que llama. En esta sección se describen los cambios en los componentes de System.Net para agregar protección ampliada al uso de la autenticación integrada de Windows.

## <a name="changes"></a>Cambios

El proceso de autenticación NTLM usado con la autenticación integrada de Windows incluye un desafío emitido por el equipo de destino y enviado de vuelta al equipo cliente. Cuando un equipo recibe un desafío que ha generado él mismo, se produce un error en la autenticación, a menos que la conexión sea una conexión de bucle invertido (dirección IPv4 127.0.0.1, por ejemplo).

Al tener acceso a un servicio que se ejecuta en un servidor web interno, es habitual hacerlo por medio de una dirección URL similar a `http://contoso/service` o `https://contoso/service`. El nombre "contoso" no suele ser el nombre del equipo en el que se implementa el servicio. Los espacios de nombres <xref:System.Net> y relacionados admiten el uso de Active Directory, DNS, NetBIOS, el archivo de hosts del equipo local (normalmente WINDOWS\system32\drivers\etc\hosts, por ejemplo) o el archivo Imhosts del equipo local (normalmente WINDOWS\system32\drivers\etc\lmhosts, por ejemplo) para resolver nombres en direcciones. El nombre "contoso" se resuelve de modo que las solicitudes enviadas a "contoso" se envíen al equipo de servidor adecuado.

Cuando se ha configurado para implementaciones grandes, también es común que se asigne un nombre único de servidor virtual a la implementación con los nombres de equipos subyacentes no usados nunca por aplicaciones cliente y usuarios finales. Por ejemplo, se podría asignar el nombre `www.contoso.com` al servidor, pero en una red interna, usar simplemente "contoso". Este nombre se denomina encabezado de host en la solicitud de web cliente. Como especifica el protocolo HTTP, el campo de encabezado o solicitud de host especifica el número de puerto y el host de Internet del recurso que se solicita. Esta información se obtiene del URI original proporcionado por el usuario o el recurso que hace referencia (normalmente una dirección URL HTTP). En .NET Framework versión 4, esta información también puede establecerla el cliente con la nueva propiedad <xref:System.Net.HttpWebRequest.Host%2A>.

La clase <xref:System.Net.AuthenticationManager> controla los componentes de autenticación administrados ("módulos") usados por las clases derivadas <xref:System.Net.WebRequest> y la clase <xref:System.Net.WebClient>. La clase <xref:System.Net.AuthenticationManager> proporciona una propiedad que expone un objeto <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>, indexado por cadena URI, para que las aplicaciones proporcionen una cadena SPN personalizada que se use durante la autenticación.

Ahora el comportamiento predeterminado de SP1 versión 3.5 es especificar el nombre de host usado en la dirección URL de solicitud del SPN en el intercambio de autenticación NTLM (NT LAN Manager) cuando la propiedad <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> no está establecida. El nombre de host usado en la dirección URL de solicitud puede ser diferente al encabezado de host especificado en <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType> en la solicitud de cliente. El nombre de host usado en la dirección URL de solicitud puede ser diferente al nombre de host real del servidor, el nombre de equipo del servidor, la dirección IP del equipo o la dirección de bucle invertido. En estos casos se produce un error en la solicitud de autenticación de Windows. Para solucionar el problema, es necesario notificar a Windows que el nombre de host usado en la dirección URL de solicitud en la solicitud de cliente (por ejemplo, "contoso") es realmente un nombre alternativo para el equipo local.

Existen varios métodos posibles para que una aplicación de servidor solucione este cambio. El enfoque recomendado consiste en asignar el nombre de host usado en la dirección URL de solicitud a la clave `BackConnectionHostNames` del Registro en el servidor. La clave `BackConnectionHostNames` del Registro normalmente se usa para asignar un nombre de host a una dirección de bucle invertido. Los pasos se indican a continuación.

Para especificar los nombres de host que se asignan a la dirección de bucle invertido y pueden conectar con sitios web en un equipo local, siga estos pasos:

1. Haga clic en Inicio, en Ejecutar, escriba regedit y luego haga clic en Aceptar.

2. En el editor del Registro, busque y luego haga clic en la siguiente clave del Registro:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`

3. Haga clic con el botón derecho en MSV1_0, apunte a Nuevo y luego haga clic en Valor de cadena múltiple.

4. Escriba `BackConnectionHostNames` y presione ENTRAR.

5. Haga clic con el botón derecho en `BackConnectionHostNames` y luego haga clic en Modificar.

6. En el cuadro de datos Valor, escriba el nombre de host o los nombres de host de los sitios (el nombre de host usado en la dirección URL de solicitud) que se encuentran en el equipo local y luego haga clic en Aceptar.

7. Salga del editor del Registro y luego reinicie el servicio IISAdmin y ejecute IISReset.

Una solución menos segura consiste en deshabilitar la comprobación de bucle inverso. Esto deshabilita la protección contra ataques de reflejo. Por eso es mejor restringir el conjunto de nombres alternativos a solo aquellos que espera que use el equipo en realidad.

## <a name="see-also"></a>Vea también

- <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>
- <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=nameWithType>
