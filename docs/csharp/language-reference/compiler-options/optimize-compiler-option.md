---
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
ms.openlocfilehash: 25a9ee1b27836dfb00dcbc72712ed068639fa2fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320037"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="80dd0-102">-optimize (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="80dd0-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="80dd0-103">La opción **-optimize** habilita o deshabilita las optimizaciones realizadas por el compilador para que el archivo de salida sea menor, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="80dd0-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80dd0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80dd0-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="80dd0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80dd0-105">Remarks</span></span>  
 <span data-ttu-id="80dd0-106">**-optimize** también indica a Common Language Runtime que optimice el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80dd0-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="80dd0-107">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="80dd0-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="80dd0-108">Especifique **-optimize+** para habilitar las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="80dd0-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="80dd0-109">Al compilar un módulo para que lo use un ensamblado, use la misma configuración de **-optimize** que la del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="80dd0-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="80dd0-110">**-o** es la forma abreviada de **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="80dd0-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="80dd0-111">Es posible combinar las opciones **-optimize** y [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="80dd0-111">It is possible to combine the **-optimize** and [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="80dd0-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80dd0-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="80dd0-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="80dd0-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="80dd0-114">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="80dd0-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="80dd0-115">Modifique la propiedad **Optimizar código**.</span><span class="sxs-lookup"><span data-stu-id="80dd0-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="80dd0-116">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="80dd0-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80dd0-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80dd0-117">Example</span></span>  
 <span data-ttu-id="80dd0-118">Compile `t2.cs` y habilite las optimizaciones del compilador:</span><span class="sxs-lookup"><span data-stu-id="80dd0-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="80dd0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="80dd0-119">See also</span></span>

- [<span data-ttu-id="80dd0-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="80dd0-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="80dd0-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="80dd0-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
