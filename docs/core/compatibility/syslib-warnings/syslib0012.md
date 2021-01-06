---
title: Advertencia SYSLIB0012
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9b3fa94029efb2343e6dbbeb3ae36195f0956523
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596396"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="02585-103">SYSLIB0012: Assembly.CodeBase y Assembly.EscapedCodeBase están obsoletos</span><span class="sxs-lookup"><span data-stu-id="02585-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="02585-104">Las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="02585-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="02585-105">Su empleo en el código genera una advertencia `SYSLIB0012` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="02585-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="02585-106">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="02585-106">Workarounds</span></span>

<span data-ttu-id="02585-107">Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="02585-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]
