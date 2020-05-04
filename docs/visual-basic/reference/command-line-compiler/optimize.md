---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005370"
---
# <a name="-optimize"></a><span data-ttu-id="d4e04-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="d4e04-102">-optimize</span></span>
<span data-ttu-id="d4e04-103">Habilita o deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="d4e04-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e04-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4e04-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4e04-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d4e04-105">Arguments</span></span>  
  
|<span data-ttu-id="d4e04-106">Término</span><span class="sxs-lookup"><span data-stu-id="d4e04-106">Term</span></span>|<span data-ttu-id="d4e04-107">Definición</span><span class="sxs-lookup"><span data-stu-id="d4e04-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d4e04-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d4e04-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d4e04-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d4e04-109">Optional.</span></span> <span data-ttu-id="d4e04-110">La opción `-optimize-` deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="d4e04-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="d4e04-111">La opción `-optimize+` habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="d4e04-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="d4e04-112">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="d4e04-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4e04-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4e04-113">Remarks</span></span>  
 <span data-ttu-id="d4e04-114">Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="d4e04-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="d4e04-115">Pero como las optimizaciones causan la reestructuración del código en el archivo de salida, `-optimize+` puede dificultar la depuración.</span><span class="sxs-lookup"><span data-stu-id="d4e04-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="d4e04-116">Todos los módulos generados con `-target:module` para un ensamblado deben usar la misma configuración de `-optimize` que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d4e04-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="d4e04-117">Para obtener más información, vea [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="d4e04-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="d4e04-118">Puede combinar las opciones `-optimize` y `-debug`.</span><span class="sxs-lookup"><span data-stu-id="d4e04-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="d4e04-119">Para establecer -optimize en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d4e04-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d4e04-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="d4e04-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d4e04-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d4e04-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="d4e04-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d4e04-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d4e04-123">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="d4e04-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d4e04-124">4.  Modifique la casilla **Habilitar optimizaciones**.</span><span class="sxs-lookup"><span data-stu-id="d4e04-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4e04-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4e04-125">Example</span></span>  
 <span data-ttu-id="d4e04-126">El código siguiente compila `T2.vb` y habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="d4e04-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4e04-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4e04-127">See also</span></span>

- [<span data-ttu-id="d4e04-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4e04-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d4e04-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4e04-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="d4e04-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4e04-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d4e04-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4e04-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
