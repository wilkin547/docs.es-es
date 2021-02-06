---
description: 'Más información acerca de: My. Response (objeto)'
title: My.Response (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 551528356040539994251cb66a905d0249f482da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640620"
---
# <a name="myresponse-object"></a>My.Response (Objeto)

Obtiene el <xref:System.Web.HttpResponse> objeto asociado a <xref:System.Web.UI.Page> . Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.  
  
## <a name="remarks"></a>Observaciones  

 El `My.Response` objeto contiene el <xref:System.Web.HttpResponse> objeto actual asociado a la página.  
  
 El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Web.HttpResponse>
- [My.Request (objeto)](my-request-object.md)
