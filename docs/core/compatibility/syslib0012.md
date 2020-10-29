---
title: Advertencia SYSLIB0012
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333169"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="0fff2-103">SYSLIB0012: Assembly.CodeBase y Assembly.EscapedCodeBase están obsoletos</span><span class="sxs-lookup"><span data-stu-id="0fff2-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="0fff2-104">Las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="0fff2-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="0fff2-105">Su empleo en el código genera una advertencia `SYSLIB0012` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0fff2-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

<span data-ttu-id="0fff2-106">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="0fff2-106">Workaround</span></span>

<span data-ttu-id="0fff2-107">Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0fff2-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>
