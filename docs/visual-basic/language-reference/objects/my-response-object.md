---
title: My.Response (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 53e8012e762c46e6efbd8e9d2191aa62d58aa42b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870041"
---
# <a name="myresponse-object"></a>My.Response (Objeto)

Obtiene el <xref:System.Web.HttpResponse> objeto asociado a <xref:System.Web.UI.Page> . Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Comentarios  

 El `My.Response` objeto contiene el <xref:System.Web.HttpResponse> objeto actual asociado a la página.  
  
 El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Web.HttpResponse>
- [My.Request (objeto)](my-request-object.md)
