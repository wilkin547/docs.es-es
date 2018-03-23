---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d40e5acda73786ee88d16bacd9bc5f69400be8
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="bfe73-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfe73-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="bfe73-103">Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con el [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) opción del compilador admite selección aleatoria de diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="bfe73-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfe73-104">Syntax</span></span>  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bfe73-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bfe73-105">Arguments</span></span>  
 <span data-ttu-id="bfe73-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bfe73-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="bfe73-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bfe73-107">Optional.</span></span> <span data-ttu-id="bfe73-108">La opción está desactivada de forma predeterminada o si especifica `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="bfe73-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="bfe73-109">La opción está activada si especifica `-highentropyva` o `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="bfe73-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe73-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfe73-110">Remarks</span></span>  
 <span data-ttu-id="bfe73-111">Si especifica esta opción, las versiones compatibles del núcleo de Windows pueden usar niveles superiores de entropía cuando el kernel Aleatoriza el diseño del espacio de direcciones de un proceso como parte de ASLR.</span><span class="sxs-lookup"><span data-stu-id="bfe73-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="bfe73-112">Si el núcleo utiliza grados de entropía más altos, se puede asignar un mayor número de direcciones a las regiones de memoria como pilas y montones.</span><span class="sxs-lookup"><span data-stu-id="bfe73-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="bfe73-113">Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.</span><span class="sxs-lookup"><span data-stu-id="bfe73-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="bfe73-114">Cuando la opción está activada, el archivo ejecutable de destino y los módulos en que, en función de debe ser capaz de controlar los valores de puntero que son mayores de 4 gigabytes (GB) cuando dichos módulos se ejecutan como procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="bfe73-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe73-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfe73-115">See Also</span></span>  
 [<span data-ttu-id="bfe73-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfe73-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bfe73-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfe73-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
