---
title: Procedimiento para convertir un elemento WebRequest a propiedades específicas del protocolo de acceso
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a9488e484aad7ba3df23c33b2cb5b79f234b758e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088371"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a>Procedimiento para convertir un elemento WebRequest a propiedades específicas del protocolo de acceso
En este ejemplo se muestra cómo convertir una WebRequest de manera que pueda tener acceso a las propiedades específicas del protocolo.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a>Vea también

- [Programming Pluggable Protocols (Programar protocolos acoplables)](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
