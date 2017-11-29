---
title: "Cómo: solicitar una página web y recuperar los resultados como una secuencia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 30006e43899cb146f02dbed3e8e72ed1b5416f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="530dc-102">Cómo: solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="530dc-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="530dc-103">En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="530dc-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="530dc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="530dc-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="530dc-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="530dc-105">Compiling the Code</span></span>  
 <span data-ttu-id="530dc-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="530dc-106">This example requires:</span></span>  
  
-   <span data-ttu-id="530dc-107">Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="530dc-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530dc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="530dc-108">See Also</span></span>  
 [<span data-ttu-id="530dc-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="530dc-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
