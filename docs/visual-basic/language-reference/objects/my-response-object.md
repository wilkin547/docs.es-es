---
title: My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567451"
---
# <a name="myresponse-object"></a>My.Response (Objeto)
Obtiene el <xref:System.Web.HttpResponse> objeto asociado <xref:System.Web.UI.Page>a. Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `My.Response` objeto contiene el objeto <xref:System.Web.HttpResponse> actual asociado a la página.  
  
 El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de `My.Request` encabezados del objeto y `My.Response` se usa el objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpResponse>
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
