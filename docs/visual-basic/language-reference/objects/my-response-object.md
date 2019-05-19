---
title: My.Response (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0e49a3b5732ee1a3626666ce06e366c4940eca05
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881961"
---
# <a name="myresponse-object"></a>My.Response (Objeto)
Obtiene el <xref:System.Web.HttpResponse> objeto asociado con el <xref:System.Web.UI.Page>. Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.  
  
 La `My.Response` objeto sólo está disponible para las aplicaciones ASP.NET.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se usa el `My.Response` objeto escribirlo en la página ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpResponse>
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
