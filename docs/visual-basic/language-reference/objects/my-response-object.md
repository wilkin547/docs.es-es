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
ms.locfileid: "33597528"
---
# <a name="myresponse-object"></a><span data-ttu-id="02056-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="02056-102">My.Response Object</span></span>
<span data-ttu-id="02056-103">Obtiene el <xref:System.Web.HttpResponse> objeto asociado a la <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="02056-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="02056-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="02056-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02056-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02056-105">Remarks</span></span>  
 <span data-ttu-id="02056-106">El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="02056-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="02056-107">El `My.Response` objeto solo está disponible para [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="02056-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02056-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02056-108">Example</span></span>  
 <span data-ttu-id="02056-109">En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se utiliza la `My.Response` objeto que se va a escribir en la página ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="02056-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="02056-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="02056-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="02056-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="02056-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
