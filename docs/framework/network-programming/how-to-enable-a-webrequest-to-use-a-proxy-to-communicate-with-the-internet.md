---
title: Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet
description: Obtenga información sobre cómo crear una instancia de proxy global con el fin de permitir que cualquier WebRequest use un proxy para comunicarse con Internet en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502540"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="f34a8-103">Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet</span><span class="sxs-lookup"><span data-stu-id="f34a8-103">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="f34a8-104">En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet.</span><span class="sxs-lookup"><span data-stu-id="f34a8-104">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="f34a8-105">En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="f34a8-105">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="f34a8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f34a8-106">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="f34a8-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f34a8-107">Compiling the Code</span></span>

<span data-ttu-id="f34a8-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f34a8-108">This example requires:</span></span>

- <span data-ttu-id="f34a8-109">Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) de C# para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="f34a8-109">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="f34a8-110">Una [instrucción `Imports`](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)de Visual Basic para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="f34a8-110">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="f34a8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f34a8-111">See also</span></span>

- [<span data-ttu-id="f34a8-112">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f34a8-112">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="f34a8-113">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="f34a8-113">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
