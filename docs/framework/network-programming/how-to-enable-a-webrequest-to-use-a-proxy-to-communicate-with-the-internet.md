---
title: "Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a42b9f947f4c3d59c3e17a892e4db405e2bc8b64
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet
En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet. En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias al espacio de nombres **System.Net**.  
  
## <a name="see-also"></a>Vea también  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

