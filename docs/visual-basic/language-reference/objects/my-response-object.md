---
title: My.Response (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: c133e46b1adff0c100d49c4bfe5e17db4314a0bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738818"
---
# <a name="myresponse-object"></a><span data-ttu-id="125d8-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="125d8-102">My.Response Object</span></span>
<span data-ttu-id="125d8-103">Obtiene el <xref:System.Web.HttpResponse> objeto asociado con el <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="125d8-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="125d8-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="125d8-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="125d8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="125d8-105">Remarks</span></span>  
 <span data-ttu-id="125d8-106">El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="125d8-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="125d8-107">El `My.Response` solo está disponible para el objeto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="125d8-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="125d8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="125d8-108">Example</span></span>  
 <span data-ttu-id="125d8-109">En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se usa el `My.Response` objeto escribirlo en la página ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="125d8-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="125d8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="125d8-110">See also</span></span>
- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="125d8-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="125d8-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
