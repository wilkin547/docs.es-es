---
title: My.Response (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0e49a3b5732ee1a3626666ce06e366c4940eca05
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881961"
---
# <a name="myresponse-object"></a><span data-ttu-id="cc334-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="cc334-102">My.Response Object</span></span>
<span data-ttu-id="cc334-103">Obtiene el <xref:System.Web.HttpResponse> objeto asociado con el <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="cc334-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="cc334-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="cc334-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc334-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc334-105">Remarks</span></span>  
 <span data-ttu-id="cc334-106">El `My.Response` objeto contiene actual <xref:System.Web.HttpResponse> objeto asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="cc334-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="cc334-107">La `My.Response` objeto sólo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc334-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc334-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc334-108">Example</span></span>  
 <span data-ttu-id="cc334-109">En el ejemplo siguiente se obtiene la colección de encabezados de la `My.Request` objeto y se usa el `My.Response` objeto escribirlo en la página ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc334-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cc334-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc334-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="cc334-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="cc334-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
