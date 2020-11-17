---
title: Advertencia SYSLIB0010
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0010.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 824423d58802d4a286bfed98422341097985990f
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440613"
---
# <a name="syslib0010-unsupported-remoting-apis"></a><span data-ttu-id="35d74-103">SYSLIB0010: API de comunicación remota no compatibles</span><span class="sxs-lookup"><span data-stu-id="35d74-103">SYSLIB0010: Unsupported remoting APIs</span></span>

<span data-ttu-id="35d74-104">[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) es una tecnología heredada; la infraestructura solo existe en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35d74-104">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology, and the infrastructure exists only in .NET Framework.</span></span> <span data-ttu-id="35d74-105">Las siguientes API relacionadas con la comunicación remota se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="35d74-105">The following remoting-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="35d74-106">Su empleo en el código genera una advertencia `SYSLIB0010` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="35d74-106">Using them in code generates warning `SYSLIB0010` at compile time.</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="35d74-107">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="35d74-107">Workarounds</span></span>

<span data-ttu-id="35d74-108">Considere la posibilidad de usar servicios REST basados en WCF o HTTP para comunicarse con objetos de otras aplicaciones o entre máquinas.</span><span class="sxs-lookup"><span data-stu-id="35d74-108">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="35d74-109">Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="35d74-109">For more information, see [.NET Framework technologies unavailable on .NET Core](../porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="35d74-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d74-110">See also</span></span>

- <span data-ttu-id="35d74-111">[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span><span class="sxs-lookup"><span data-stu-id="35d74-111">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span></span>
