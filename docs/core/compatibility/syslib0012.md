---
title: Advertencia SYSLIB0012
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dc139d5c5cb6d6a34d161147b350b3324d15117e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440587"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="1b35e-103">SYSLIB0012: Assembly.CodeBase y Assembly.EscapedCodeBase están obsoletos</span><span class="sxs-lookup"><span data-stu-id="1b35e-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="1b35e-104">Las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="1b35e-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="1b35e-105">Su empleo en el código genera una advertencia `SYSLIB0012` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1b35e-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="1b35e-106">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="1b35e-106">Workarounds</span></span>

<span data-ttu-id="1b35e-107">Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1b35e-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]
