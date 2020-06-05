---
title: My.Request (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 38f510e2a3958761b902f37760069aa8d595ea8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372432"
---
# <a name="myrequest-object"></a><span data-ttu-id="bf09d-102">My.Request (Objeto)</span><span class="sxs-lookup"><span data-stu-id="bf09d-102">My.Request Object</span></span>
<span data-ttu-id="bf09d-103">Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.</span><span class="sxs-lookup"><span data-stu-id="bf09d-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf09d-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf09d-104">Remarks</span></span>  
 <span data-ttu-id="bf09d-105">Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.</span><span class="sxs-lookup"><span data-stu-id="bf09d-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="bf09d-106">El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bf09d-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf09d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf09d-107">Example</span></span>  
 <span data-ttu-id="bf09d-108">En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="bf09d-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bf09d-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf09d-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="bf09d-110">My.Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="bf09d-110">My.Response Object</span></span>](my-response-object.md)
