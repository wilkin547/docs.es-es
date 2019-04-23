---
title: Procedimiento para solicitar una página web y recuperar los resultados como una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 23c094f0a3f528750c9589dbc99a0ada86236967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097205"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="ab0f7-102">Procedimiento para solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="ab0f7-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="ab0f7-103">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ab0f7-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab0f7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab0f7-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab0f7-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ab0f7-105">Compiling the Code</span></span>  
 <span data-ttu-id="ab0f7-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ab0f7-106">This example requires:</span></span>  
  
-   <span data-ttu-id="ab0f7-107">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ab0f7-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab0f7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab0f7-108">See also</span></span>

- [<span data-ttu-id="ab0f7-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="ab0f7-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
