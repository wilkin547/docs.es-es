---
title: 'Cómo: solicitar una página web y recuperar los resultados como una secuencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71393110"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="c4608-102">Cómo: solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="c4608-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="c4608-103">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c4608-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="c4608-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4608-104">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="c4608-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c4608-105">Compiling the Code</span></span>

 <span data-ttu-id="c4608-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c4608-106">This example requires:</span></span>

- <span data-ttu-id="c4608-107">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c4608-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4608-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4608-108">See also</span></span>

- [<span data-ttu-id="c4608-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="c4608-109">Requesting Data</span></span>](requesting-data.md)
