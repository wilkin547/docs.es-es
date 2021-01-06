---
title: Advertencia SYSLIB0009
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0009.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 922fcc30b2b1577976e4e88e3f7631e19d4b2cce
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596408"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a><span data-ttu-id="40a15-103">SYSLIB0009: no se admiten los métodos AuthenticationManager Authenticate y PreAuthenticate</span><span class="sxs-lookup"><span data-stu-id="40a15-103">SYSLIB0009: The AuthenticationManager Authenticate and PreAuthenticate methods are not supported</span></span>

<span data-ttu-id="40a15-104">Las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="40a15-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="40a15-105">El uso de estas API genera una advertencia `SYSLIB0009` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="40a15-105">Use of these APIs generates warning `SYSLIB0009` at compile time.</span></span>

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a><span data-ttu-id="40a15-106">Supresión de la advertencia</span><span class="sxs-lookup"><span data-stu-id="40a15-106">Suppress the warning</span></span>

<span data-ttu-id="40a15-107">Si no puede cambiar el código, puede suprimir la advertencia por medio de una directiva `#pragma` o la opción de configuración del proyecto `<NoWarn>`.</span><span class="sxs-lookup"><span data-stu-id="40a15-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="40a15-108">Para obtener ejemplos, vea [Supresión de advertencias](../syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="40a15-108">For examples, see [Suppress warnings](../syslib-obsoletions.md#suppress-warnings).</span></span>
