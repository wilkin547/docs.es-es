---
description: 'Más información acerca de: BC42033: valor de suma de comprobación incorrecto, dígitos no hexadecimales o número impar de dígitos hexadecimales'
title: Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 8af1ca5e3f733278054300c2a79134817c56cf5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797112"
---
# <a name="bc42033-bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="6a0c4-103">BC42033: valor de suma de comprobación incorrecto, dígitos no hexadecimales o número impar de dígitos hexadecimales</span><span class="sxs-lookup"><span data-stu-id="6a0c4-103">BC42033: Bad checksum value, non hex digits or odd number of hex digits</span></span>

<span data-ttu-id="6a0c4-104">Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-104">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>

 <span data-ttu-id="6a0c4-105">Cuando ASP.NET genera un archivo de origen de Visual Basic (extensión .vb), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-105">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="6a0c4-106">Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-106">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>

 <span data-ttu-id="6a0c4-107">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-107">By default, this message is a warning.</span></span> <span data-ttu-id="6a0c4-108">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6a0c4-108">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="6a0c4-109">**Identificador de error:** BC42033</span><span class="sxs-lookup"><span data-stu-id="6a0c4-109">**Error ID:** BC42033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6a0c4-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6a0c4-110">To correct this error</span></span>

1. <span data-ttu-id="6a0c4-111">Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-111">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>

2. <span data-ttu-id="6a0c4-112">Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-112">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>

3. <span data-ttu-id="6a0c4-113">Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a0c4-113">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a0c4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a0c4-114">See also</span></span>

- <span data-ttu-id="6a0c4-115">[ASP.NET Overview](/aspnet/overview) (Información general de ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="6a0c4-115">[ASP.NET Overview](/aspnet/overview)</span></span>
- [<span data-ttu-id="6a0c4-116">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="6a0c4-116">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
