---
title: My.Request (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: d0459506994fb69ebfaa4186ba137044b6fe9464
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870078"
---
# <a name="myrequest-object"></a>My.Request (Objeto)

Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.  
  
## <a name="remarks"></a>Comentarios  

 Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.  
  
 El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Web.HttpRequest>
- [My.Response (objeto)](my-response-object.md)
