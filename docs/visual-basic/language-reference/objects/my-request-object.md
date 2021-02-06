---
description: 'Más información acerca de: My. Request (objeto)'
title: My.Request (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 0b72252e261cd033bfc35c546de5c53a4f3cfe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640659"
---
# <a name="myrequest-object"></a><span data-ttu-id="8e476-103">My.Request (Objeto)</span><span class="sxs-lookup"><span data-stu-id="8e476-103">My.Request Object</span></span>

<span data-ttu-id="8e476-104">Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.</span><span class="sxs-lookup"><span data-stu-id="8e476-104">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e476-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8e476-105">Remarks</span></span>  

 <span data-ttu-id="8e476-106">Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.</span><span class="sxs-lookup"><span data-stu-id="8e476-106">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="8e476-107">El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8e476-107">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e476-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e476-108">Example</span></span>  

 <span data-ttu-id="8e476-109">En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="8e476-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8e476-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e476-110">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="8e476-111">My.Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="8e476-111">My.Response Object</span></span>](my-response-object.md)
