---
title: My.Response (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0a907d74112586e7b88c5a0a6f40080455454d7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="myresponse-object"></a>My.Response (Objeto)
Obtiene el <xref:System.Web.HttpResponse> objeto asociado a la <xref:System.Web.UI.Page>. Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.  
  
 El `My.Response` objeto solo está disponible para [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] las aplicaciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se utiliza la `My.Response` objeto que se va a escribir en la página ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Web.HttpResponse>  
 [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
