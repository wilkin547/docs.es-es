---
title: Advertencia SYSLIB0008
description: Obtenga información sobre la obsolescencia que genera la advertencia en tiempo de compilación SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440600"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="1b203-103">SYSLIB0008: CreatePdbGenerator no es compatible</span><span class="sxs-lookup"><span data-stu-id="1b203-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="1b203-104">La API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> se ha marcado como obsoleta a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="1b203-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="1b203-105">El empleo de esta API genera una advertencia `SYSLIB0008` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1b203-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="1b203-106">Supresión de la advertencia</span><span class="sxs-lookup"><span data-stu-id="1b203-106">Suppress the warning</span></span>

<span data-ttu-id="1b203-107">Si no puede cambiar el código, puede suprimir la advertencia por medio de una directiva `#pragma` o la opción de configuración del proyecto `<NoWarn>`.</span><span class="sxs-lookup"><span data-stu-id="1b203-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="1b203-108">Para obtener ejemplos, vea [Supresión de advertencias](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="1b203-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
