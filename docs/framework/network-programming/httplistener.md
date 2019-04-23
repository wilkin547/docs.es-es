---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: d3fecb9fe78ca54f68d3c5a97dae5d5dd9fbb28d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075423"
---
# <a name="httplistener"></a>HttpListener
La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación. El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.  
  
## <a name="httpsys"></a>HTTP.SYS  
 La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows. HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web. Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL. Para obtener más información, vea la documentación en la herramienta [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Servidor](https://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.HttpWebResponse>
- [Servidor HTTP](https://go.microsoft.com/fwlink/?LinkID=178285)
- [Mejoras de seguridad de Internet Information](https://go.microsoft.com/fwlink/?LinkID=178286)
- [Ejemplo de la aplicación host HttpListener de ASPX](https://go.microsoft.com/fwlink/?LinkID=179560)
- [Ejemplo de tecnología HttpListener](https://go.microsoft.com/fwlink/?LinkID=179558)
- [Network Programming Samples (Ejemplos de programación de red)](../../../docs/framework/network-programming/network-programming-samples.md)
