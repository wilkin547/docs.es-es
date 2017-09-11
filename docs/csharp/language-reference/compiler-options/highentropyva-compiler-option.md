---
title: -highentropyva (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /highentropyva
dev_langs:
- CSharp
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4cb21c109fc33a30da016fd6a42285a3a3da02e2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="highentropyva-c-compiler-options"></a><span data-ttu-id="6b2b2-102">/highentropyva (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6b2b2-102">/highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="6b2b2-103">La opción del compilador **/highentropyva** indica al kernel de Windows si un archivo ejecutable determinado admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-103">The **/highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b2b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b2b2-104">Syntax</span></span>  
  
```console  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b2b2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b2b2-105">Arguments</span></span>  
 <span data-ttu-id="6b2b2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6b2b2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="6b2b2-107">Esta opción especifica que un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) admite un espacio de direcciones virtuales de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-107">This option specifies that a 64-bit executable or an executable that is marked by the [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="6b2b2-108">La opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-108">The option is disabled by default.</span></span> <span data-ttu-id="6b2b2-109">Para habilitarla, use **/highentropyva+** o **/highentropyva**.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-109">Use **/highentropyva+** or **/highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b2b2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b2b2-110">Remarks</span></span>  
 <span data-ttu-id="6b2b2-111">La opción **/highentropyva** habilita las versiones compatibles del kernel de Windows para usar niveles superiores de entropía al aleatorizar el diseño del espacio de direcciones de un proceso como parte de ASLR.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-111">The **/highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="6b2b2-112">El uso de niveles superiores de entropía significa que un mayor número de direcciones se puede asignar a las regiones de memoria como pilas y montones.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-112">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="6b2b2-113">Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="6b2b2-114">Cuando se especifica la opción del compilador **/highentropyva**, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigabytes (GB), cuando se ejecutan como un proceso de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-114">When the **/highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>

