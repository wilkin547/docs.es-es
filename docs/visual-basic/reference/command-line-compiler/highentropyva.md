---
description: Más información sobre -highentropyva (Visual Basic)
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 90fc3713ae4f9a073a63a57c5b35114548e26cbb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470270"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="c2a49-103">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2a49-103">-highentropyva (Visual Basic)</span></span>

<span data-ttu-id="c2a49-104">Indica si un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [-platform:anycpu](platform.md) admite la selección aleatoria del diseño del espacio de direcciones de alta entropía (ASLR).</span><span class="sxs-lookup"><span data-stu-id="c2a49-104">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a49-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2a49-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c2a49-106">Arguments</span></span>  

 <span data-ttu-id="c2a49-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c2a49-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c2a49-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c2a49-108">Optional.</span></span> <span data-ttu-id="c2a49-109">La opción está desactivada de forma predeterminada o si se especifica `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="c2a49-109">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="c2a49-110">La opción está activada si se especifica `-highentropyva` o `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="c2a49-110">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a49-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2a49-111">Remarks</span></span>  

 <span data-ttu-id="c2a49-112">Si se especifica esta opción, las versiones compatibles del kernel de Windows pueden usar niveles superiores de entropía cuando el kernel seleccione de forma aleatoria el diseño del espacio de direcciones de un proceso como parte de ASLR.</span><span class="sxs-lookup"><span data-stu-id="c2a49-112">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="c2a49-113">Si el kernel usa niveles superiores de entropía, se puede asignar un mayor número de direcciones a las regiones de memoria como pilas y montones.</span><span class="sxs-lookup"><span data-stu-id="c2a49-113">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="c2a49-114">Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.</span><span class="sxs-lookup"><span data-stu-id="c2a49-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="c2a49-115">Si la opción está activada, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigas (GB), cuando dichos módulos se ejecutan como un proceso de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c2a49-115">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a49-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a49-116">See also</span></span>

- [<span data-ttu-id="c2a49-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2a49-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c2a49-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2a49-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
