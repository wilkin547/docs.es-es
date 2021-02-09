---
description: 'Más información acerca de: Derivar de WebResponse'
title: Derivar de WebResponse
ms.date: 03/30/2017
helpviewer_keywords:
- Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
ms.openlocfilehash: 5e941ce055091c6034640733465020ff62ce3721
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747483"
---
# <a name="deriving-from-webresponse"></a>Derivar de WebResponse

La clase <xref:System.Net.WebResponse> es una clase base abstracta que proporciona las propiedades y métodos básicos para crear una respuesta específica del protocolo adecuada al modelo de protocolo acoplable de .NET Framework. Las aplicaciones que usan la clase <xref:System.Net.WebRequest> para solicitar datos de recursos reciben las respuestas en una **WebResponse**. Los descendientes de **WebResponse** específicos del protocolo deben implementar los miembros abstractos de la clase **WebResponse**.  
  
 La clase **WebRequest** asociada debe crear descendientes de **WebResponse**. Por ejemplo, las instancias de <xref:System.Net.HttpWebResponse> se crean solo como el resultado de llamar a <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> o <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType>. Cada **WebResponse** contiene el resultado de una solicitud a un recurso y no está diseñada para volver a usarse.  
  
## <a name="contentlength-property"></a>Propiedad ContentLength  

 La propiedad <xref:System.Net.WebResponse.ContentLength%2A> indica el número de bytes de datos que están disponibles de la secuencia que ha devuelto el método <xref:System.Net.WebResponse.GetResponseStream%2A>. La propiedad **ContentLength** no indica el número de bytes de la información de metadatos o encabezado que ha devuelto el servidor; indica solo el número de bytes de datos en el propio recurso solicitado.  
  
## <a name="contenttype-property"></a>Propiedad ContentType  

 La propiedad <xref:System.Net.WebResponse.ContentType%2A> proporciona toda la información especial que el protocolo necesita que envíe al cliente para identificar el tipo de contenido que está enviando el servidor. Suele ser el tipo de contenido MIME de los datos devueltos.  
  
## <a name="headers-property"></a>Propiedad Headers  

 La propiedad <xref:System.Net.WebResponse.Headers%2A> contiene una colección arbitraria de pares nombre-valor de metadatos asociados a la respuesta. Los metadatos que necesita el protocolo y que se pueden expresar como un par nombre-valor se pueden incluir en la propiedad **Headers**.  
  
 No es necesario usar la propiedad **Headers** para usar los metadatos de encabezado. Los metadatos específicos del protocolo pueden exponerse como propiedades; por ejemplo, la propiedad <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType> expone el encabezado HTTP **Última modificación**. Cuando se exponen metadatos de encabezado como una propiedad, no se debe permitir que se establezca la misma propiedad mediante la propiedad **Headers**.  
  
## <a name="responseuri-property"></a>Propiedad ResponseUri  

 La propiedad <xref:System.Net.WebResponse.ResponseUri%2A> contiene el URI del recurso que ha proporcionado realmente la respuesta. Para los protocolos que no admiten el redireccionamiento, **ResponseUri** será igual que la propiedad <xref:System.Net.WebRequest.RequestUri%2A> de la **WebRequest** que ha creado la respuesta. Si el protocolo admite el redireccionamiento de la solicitud, **ResponseUri** contendrá el URI de la respuesta.  
  
## <a name="close-method"></a>Close (Método)  

 El método <xref:System.Net.WebResponse.Close%2A> cierra cualquier conexión realizada por la solicitud y respuesta, y borra los recursos que ha usado la respuesta. El método **Close** cierra cualquier instancia de secuencia que haya usado la respuesta, pero no genera una excepción si la secuencia de respuesta se ha cerrado anteriormente mediante una llamada al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.  
  
## <a name="getresponsestream-method"></a>Método GetResponseStream  

 El método <xref:System.Net.WebResponse.GetResponseStream%2A> devuelve una secuencia que contiene la respuesta del recurso solicitado. La secuencia de respuesta contiene solo los datos devueltos por el recurso; cualquier encabezado o metadatos incluidos en la respuesta deben quitarse de esta y exponerse en la aplicación mediante propiedades específicas del protocolo o mediante la propiedad **Headers**.  
  
 La instancia de secuencia que ha devuelto el método **GetResponseStream** pertenece a la aplicación y puede cerrarse sin cerrar la **WebResponse**. Por convención, al llamar al método **WebResponse.Close** también se cierra la secuencia devuelta por **GetResponse**.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebResponse>
- <xref:System.Net.HttpWebResponse>
- <xref:System.Net.FileWebResponse>
- [Programming Pluggable Protocols (Programar protocolos acoplables)](programming-pluggable-protocols.md)
- [Derivar de WebRequest](deriving-from-webrequest.md)
