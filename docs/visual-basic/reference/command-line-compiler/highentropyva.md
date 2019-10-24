---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775654"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="77be9-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77be9-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="77be9-103">Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [-Platform: AnyCPU](../../../visual-basic/reference/command-line-compiler/platform.md) admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="77be9-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77be9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77be9-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="77be9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="77be9-105">Arguments</span></span>  
 <span data-ttu-id="77be9-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="77be9-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="77be9-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="77be9-107">Optional.</span></span> <span data-ttu-id="77be9-108">La opción está desactivada de forma predeterminada o si se especifica `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="77be9-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="77be9-109">La opción está activada si se especifica `-highentropyva` o `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="77be9-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77be9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77be9-110">Remarks</span></span>  
 <span data-ttu-id="77be9-111">Si especifica esta opción, las versiones compatibles del kernel de Windows pueden usar los mayores grados de entropía cuando el kernel Aleatoriza el diseño del espacio de direcciones de un proceso como parte de ASLR.</span><span class="sxs-lookup"><span data-stu-id="77be9-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="77be9-112">Si el kernel usa mayores grados de entropía, se puede asignar un número mayor de direcciones a las regiones de memoria, como pilas y montones.</span><span class="sxs-lookup"><span data-stu-id="77be9-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="77be9-113">Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.</span><span class="sxs-lookup"><span data-stu-id="77be9-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="77be9-114">Cuando la opción está activada, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigabytes (GB) cuando dichos módulos se ejecutan como procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="77be9-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77be9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="77be9-115">See also</span></span>

- [<span data-ttu-id="77be9-116">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77be9-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="77be9-117">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="77be9-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
