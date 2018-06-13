---
title: 'Cómo: solicitar una página web y recuperar los resultados como una secuencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 31856e7fc7136b3bdb8fab9fdf8185de32a3007a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395218"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="e9cc3-102">Cómo: solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="e9cc3-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="e9cc3-103">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9cc3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9cc3-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9cc3-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e9cc3-105">Compiling the Code</span></span>  
 <span data-ttu-id="e9cc3-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e9cc3-107">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cc3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9cc3-108">See Also</span></span>  
 [<span data-ttu-id="e9cc3-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="e9cc3-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
