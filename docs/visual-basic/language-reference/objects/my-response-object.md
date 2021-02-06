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
# <a name="myresponse-object"></a><span data-ttu-id="8c03c-103">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="8c03c-103">My.Response Object</span></span>

<span data-ttu-id="8c03c-104">Obtiene el <xref:System.Web.HttpResponse> objeto asociado a <xref:System.Web.UI.Page> .</span><span class="sxs-lookup"><span data-stu-id="8c03c-104">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="8c03c-105">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="8c03c-105">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c03c-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c03c-106">Remarks</span></span>  

 <span data-ttu-id="8c03c-107">El `My.Response` objeto contiene el <xref:System.Web.HttpResponse> objeto actual asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="8c03c-107">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="8c03c-108">El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="8c03c-108">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c03c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c03c-109">Example</span></span>  

 <span data-ttu-id="8c03c-110">En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="8c03c-110">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8c03c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c03c-111">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="8c03c-112">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="8c03c-112">My.Request Object</span></span>](my-request-object.md)
