---
title: My.Response (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 2f72f493d99c1e0b0469150c041649486e5ed124
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819000"
---
# <a name="myresponse-object"></a>My.Response (Objeto)
Obtiene el <xref:System.Web.HttpResponse> objeto asociado con el <xref:System.Web.UI.Page>. Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  
 El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.  
  
 El `My.Response` solo está disponible para el objeto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplicaciones.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se usa el `My.Response` objeto escribirlo en la página ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpResponse>
- [My.Request (objeto)](../../../visual-basic/language-reference/objects/my-request-object.md)
