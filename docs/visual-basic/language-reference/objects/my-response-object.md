---
title: My.Response (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: d5f49529a2593093a234babc22f64b591ea3cc61
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46526550"
---
# <a name="myresponse-object"></a>My.Response (Objeto)
Obtiene el <xref:System.Web.HttpResponse> objeto asociado con el <xref:System.Web.UI.Page>. Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.  
  
 El `My.Response` solo está disponible para el objeto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplicaciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se usa el `My.Response` objeto escribirlo en la página ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Web.HttpResponse>  
 [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
