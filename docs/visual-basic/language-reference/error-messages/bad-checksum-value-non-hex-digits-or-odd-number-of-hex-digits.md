---
title: "Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="55df8-102">Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar</span><span class="sxs-lookup"><span data-stu-id="55df8-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="55df8-103">Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.</span><span class="sxs-lookup"><span data-stu-id="55df8-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="55df8-104">Cuando ASP.NET genera un archivo de origen de Visual Basic (extensión .vb), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="55df8-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="55df8-105">Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.</span><span class="sxs-lookup"><span data-stu-id="55df8-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="55df8-106">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="55df8-106">By default, this message is a warning.</span></span> <span data-ttu-id="55df8-107">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="55df8-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="55df8-108">**Id. de error:** BC42033</span><span class="sxs-lookup"><span data-stu-id="55df8-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="55df8-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="55df8-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="55df8-110">Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55df8-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="55df8-111">Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="55df8-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="55df8-112">Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55df8-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55df8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="55df8-113">See Also</span></span>  
 <span data-ttu-id="55df8-114">[ASP.NET Overview](https://msdn.microsoft.com/library/4w3ex9c2.aspx) (Información general de ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="55df8-114">[ASP.NET Overview](https://msdn.microsoft.com/library/4w3ex9c2.aspx)</span></span>  
 [<span data-ttu-id="55df8-115">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="55df8-115">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
