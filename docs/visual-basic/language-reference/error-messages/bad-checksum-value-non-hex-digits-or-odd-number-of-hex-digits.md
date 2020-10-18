---
title: Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: e380033f9353781ee7dc86696e93c8d0f18a1a73
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162978"
---
# <a name="bc42033-bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="7ceef-102">BC42033: valor de suma de comprobación incorrecto, dígitos no hexadecimales o número impar de dígitos hexadecimales</span><span class="sxs-lookup"><span data-stu-id="7ceef-102">BC42033: Bad checksum value, non hex digits or odd number of hex digits</span></span>

<span data-ttu-id="7ceef-103">Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.</span><span class="sxs-lookup"><span data-stu-id="7ceef-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>

 <span data-ttu-id="7ceef-104">Cuando ASP.NET genera un archivo de origen de Visual Basic (extensión .vb), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="7ceef-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="7ceef-105">Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.</span><span class="sxs-lookup"><span data-stu-id="7ceef-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>

 <span data-ttu-id="7ceef-106">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="7ceef-106">By default, this message is a warning.</span></span> <span data-ttu-id="7ceef-107">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7ceef-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="7ceef-108">**Identificador de error:** BC42033</span><span class="sxs-lookup"><span data-stu-id="7ceef-108">**Error ID:** BC42033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7ceef-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7ceef-109">To correct this error</span></span>

1. <span data-ttu-id="7ceef-110">Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ceef-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>

2. <span data-ttu-id="7ceef-111">Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="7ceef-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>

3. <span data-ttu-id="7ceef-112">Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ceef-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ceef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ceef-113">See also</span></span>

- <span data-ttu-id="7ceef-114">[ASP.NET Overview](/aspnet/overview) (Información general de ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="7ceef-114">[ASP.NET Overview](/aspnet/overview)</span></span>
- [<span data-ttu-id="7ceef-115">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="7ceef-115">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
