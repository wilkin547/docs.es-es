---
title: Procedimiento para solicitar una página web y recuperar los resultados como una secuencia
description: En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502488"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="690dc-103">Procedimiento para solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="690dc-103">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="690dc-104">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="690dc-104">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="690dc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="690dc-105">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="690dc-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="690dc-106">Compiling the Code</span></span>

 <span data-ttu-id="690dc-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="690dc-107">This example requires:</span></span>

- <span data-ttu-id="690dc-108">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="690dc-108">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="690dc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="690dc-109">See also</span></span>

- [<span data-ttu-id="690dc-110">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="690dc-110">Requesting Data</span></span>](requesting-data.md)
