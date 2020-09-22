---
title: My.Request (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: d0459506994fb69ebfaa4186ba137044b6fe9464
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870078"
---
# <a name="myrequest-object"></a><span data-ttu-id="8bf66-102">My.Request (Objeto)</span><span class="sxs-lookup"><span data-stu-id="8bf66-102">My.Request Object</span></span>

<span data-ttu-id="8bf66-103">Obtiene el objeto <xref:System.Web.HttpRequest> para la página solicitada.</span><span class="sxs-lookup"><span data-stu-id="8bf66-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bf66-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bf66-104">Remarks</span></span>  

 <span data-ttu-id="8bf66-105">Objeto `My.Request` que contiene información sobre la solicitud HTTP actual.</span><span class="sxs-lookup"><span data-stu-id="8bf66-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="8bf66-106">El objeto `My.Request` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8bf66-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bf66-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bf66-107">Example</span></span>  

 <span data-ttu-id="8bf66-108">En el ejemplo siguiente se obtiene la colección de encabezados del `My.Request` objeto y se usa el `My.Response` objeto para escribirla en la página ASP.net.</span><span class="sxs-lookup"><span data-stu-id="8bf66-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8bf66-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bf66-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="8bf66-110">My.Response (objeto)</span><span class="sxs-lookup"><span data-stu-id="8bf66-110">My.Response Object</span></span>](my-response-object.md)
