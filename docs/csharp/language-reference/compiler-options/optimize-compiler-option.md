---
description: -optimize (Opciones del compilador de C#)
title: -optimize (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 1862794e4d823e38ce19780300a0b04f4e57dc44
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193990"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="3654f-103">-optimize (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="3654f-103">-optimize (C# Compiler Options)</span></span>

<span data-ttu-id="3654f-104">La opción **-optimize** habilita o deshabilita las optimizaciones realizadas por el compilador para que el archivo de salida sea menor, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="3654f-104">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3654f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3654f-105">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="3654f-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3654f-106">Remarks</span></span>  

 <span data-ttu-id="3654f-107">**-optimize** también indica a Common Language Runtime que optimice el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3654f-107">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="3654f-108">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="3654f-108">By default, optimizations are disabled.</span></span> <span data-ttu-id="3654f-109">Especifique **-optimize+** para habilitar las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="3654f-109">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="3654f-110">Al compilar un módulo para que lo use un ensamblado, use la misma configuración de **-optimize** que la del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3654f-110">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="3654f-111">**-o** es la forma abreviada de **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="3654f-111">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="3654f-112">Es posible combinar las opciones **-optimize** y [-debug](./debug-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3654f-112">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3654f-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3654f-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="3654f-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3654f-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="3654f-115">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3654f-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="3654f-116">Modifique la propiedad **Optimizar código**.</span><span class="sxs-lookup"><span data-stu-id="3654f-116">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="3654f-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="3654f-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3654f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3654f-118">Example</span></span>  

 <span data-ttu-id="3654f-119">Compile `t2.cs` y habilite las optimizaciones del compilador:</span><span class="sxs-lookup"><span data-stu-id="3654f-119">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="3654f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3654f-120">See also</span></span>

- [<span data-ttu-id="3654f-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="3654f-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3654f-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="3654f-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
