---
title: Procedimiento para solicitar una página web y recuperar los resultados como una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: b3d24a958ec93084d03d2ad2e0eb6d9d2507e155
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048174"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="c41c2-102">Procedimiento para solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="c41c2-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="c41c2-103">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c41c2-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c41c2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c41c2-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c41c2-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c41c2-105">Compiling the Code</span></span>  
 <span data-ttu-id="c41c2-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c41c2-106">This example requires:</span></span>  
  
- <span data-ttu-id="c41c2-107">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c41c2-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41c2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c41c2-108">See also</span></span>

- [<span data-ttu-id="c41c2-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="c41c2-109">Requesting Data</span></span>](requesting-data.md)
