---
description: 'Más información acerca de: My. Request (objeto)'
title: My.Request (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 0b72252e261cd033bfc35c546de5c53a4f3cfe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640659"
---
# <a name="myrequest-object"></a>My.Request (Objeto)

Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.  
  
## <a name="remarks"></a>Observaciones  

 Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.  
  
 El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpRequest>
- [My.Response (objeto)](my-response-object.md)
