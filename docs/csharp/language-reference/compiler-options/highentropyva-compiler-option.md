---
description: -highentropyva (Opciones del compilador de C#)
title: -highentropyva (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: f3cdeb5e63d632fecbbd94501558cc53c28a918a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173209"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="eba9f-103">-highentropyva (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="eba9f-103">-highentropyva (C# Compiler Options)</span></span>

<span data-ttu-id="eba9f-104">La opción del compilador **-highentropyva** indica al kernel de Windows si un archivo ejecutable determinado admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="eba9f-104">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eba9f-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="eba9f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eba9f-106">Arguments</span></span>  

 <span data-ttu-id="eba9f-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="eba9f-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="eba9f-108">Esta opción especifica que un archivo ejecutable de 64 bits o un archivo ejecutable que está marcado con la opción del compilador [-platform:anycpu](./platform-compiler-option.md) admite un espacio de direcciones virtuales de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="eba9f-108">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="eba9f-109">La opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eba9f-109">The option is disabled by default.</span></span> <span data-ttu-id="eba9f-110">Para habilitarla, use **-highentropyva+** o **-highentropyva**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-110">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eba9f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eba9f-111">Remarks</span></span>  

 <span data-ttu-id="eba9f-112">La opción **-highentropyva** habilita las versiones compatibles del kernel de Windows para usar niveles superiores de entropía al aleatorizar el diseño del espacio de direcciones de un proceso como parte de ASLR.</span><span class="sxs-lookup"><span data-stu-id="eba9f-112">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="eba9f-113">El uso de niveles superiores de entropía significa que un mayor número de direcciones se puede asignar a las regiones de memoria como pilas y montones.</span><span class="sxs-lookup"><span data-stu-id="eba9f-113">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="eba9f-114">Como resultado, la ubicación de un área de memoria específica es más difícil de adivinar.</span><span class="sxs-lookup"><span data-stu-id="eba9f-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="eba9f-115">Cuando se especifica la opción del compilador **-highentropyva**, el archivo ejecutable de destino y todos los módulos de los que depende deben ser capaces de controlar los valores de puntero que son superiores a 4 gigas (GB), cuando se ejecutan como un proceso de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="eba9f-115">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
