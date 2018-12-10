---
title: 'Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 1b10d895478a88556cf1d716480de568c8e9c9ad
ms.sourcegitcommit: 2151690e10d91545e2c20d6b5ad222c162b6b83d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "50190448"
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
  
-   Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.  
  
## <a name="see-also"></a>Vea también  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
