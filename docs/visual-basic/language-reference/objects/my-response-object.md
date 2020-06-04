---
title: My.Response (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 962108264563c5e0b2894c5c856a5f23a3c1a8b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372470"
---
# <a name="myresponse-object"></a><span data-ttu-id="dbd44-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="dbd44-102">My.Response Object</span></span>
<span data-ttu-id="dbd44-103">Obtiene el <xref:System.Web.HttpResponse> objeto asociado a <xref:System.Web.UI.Page> .</span><span class="sxs-lookup"><span data-stu-id="dbd44-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="dbd44-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="dbd44-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbd44-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbd44-105">Remarks</span></span>  
 <span data-ttu-id="dbd44-106">El `My.Response` objeto contiene el <xref:System.Web.HttpResponse> objeto actual asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="dbd44-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="dbd44-107">El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="dbd44-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbd44-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbd44-108">Example</span></span>  
 <span data-ttu-id="dbd44-109">En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="dbd44-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="dbd44-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbd44-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="dbd44-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="dbd44-111">My.Request Object</span></span>](my-request-object.md)
