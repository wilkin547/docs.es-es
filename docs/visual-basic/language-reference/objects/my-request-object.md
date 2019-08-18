---
title: My. Request (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: da17872acb839cdcdfa7f80c3f58f26dc25d0ab5
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567462"
---
# <a name="myrequest-object"></a>My.Request (Objeto)
Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.  
  
## <a name="remarks"></a>Comentarios  
 Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.  
  
 El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de `My.Request` encabezados del objeto y `My.Response` se usa el objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpRequest>
- [My.Response (objeto)](../../../visual-basic/language-reference/objects/my-response-object.md)
