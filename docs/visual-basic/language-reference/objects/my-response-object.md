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
# <a name="myresponse-object"></a><span data-ttu-id="ac7e7-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="ac7e7-102">My.Response Object</span></span>
<span data-ttu-id="ac7e7-103">Obtiene el <xref:System.Web.HttpResponse> objeto asociado <xref:System.Web.UI.Page>a.</span><span class="sxs-lookup"><span data-stu-id="ac7e7-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="ac7e7-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac7e7-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac7e7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac7e7-105">Remarks</span></span>  
 <span data-ttu-id="ac7e7-106">El `My.Response` objeto contiene el objeto <xref:System.Web.HttpResponse> actual asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="ac7e7-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="ac7e7-107">El `My.Response` objeto solo está disponible para las aplicaciones de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="ac7e7-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac7e7-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac7e7-108">Example</span></span>  
 <span data-ttu-id="ac7e7-109">En el ejemplo siguiente se obtiene la colección de `My.Request` encabezados del objeto y `My.Response` se usa el objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="ac7e7-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ac7e7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac7e7-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="ac7e7-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="ac7e7-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
