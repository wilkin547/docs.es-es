---
title: -optimizar
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 2f066835c5f864538f281d4c58772e0e60c132f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649950"
---
# <a name="-optimize"></a><span data-ttu-id="6188f-102">-optimizar</span><span class="sxs-lookup"><span data-stu-id="6188f-102">-optimize</span></span>
<span data-ttu-id="6188f-103">Habilita o deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="6188f-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6188f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6188f-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6188f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6188f-105">Arguments</span></span>  
  
|<span data-ttu-id="6188f-106">Término</span><span class="sxs-lookup"><span data-stu-id="6188f-106">Term</span></span>|<span data-ttu-id="6188f-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="6188f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="6188f-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6188f-108">`+` &#124; `-`</span></span>|<span data-ttu-id="6188f-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6188f-109">Optional.</span></span> <span data-ttu-id="6188f-110">El `-optimize-` opción deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="6188f-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="6188f-111">El `-optimize+` opción habilita las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="6188f-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="6188f-112">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6188f-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6188f-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6188f-113">Remarks</span></span>  
 <span data-ttu-id="6188f-114">Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="6188f-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="6188f-115">Sin embargo, dado que las optimizaciones causan la reestructuración del código en el archivo de salida, `-optimize+` puede dificultar la depuración.</span><span class="sxs-lookup"><span data-stu-id="6188f-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="6188f-116">Todos los módulos generados con `-target:module` para un ensamblado debe usar la misma `-optimize` configuración que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6188f-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="6188f-117">Para obtener más información, consulte [-destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="6188f-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="6188f-118">Puede combinar la `-optimize` y `-debug` opciones.</span><span class="sxs-lookup"><span data-stu-id="6188f-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="6188f-119">Para establecer - optimizar en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6188f-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6188f-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="6188f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6188f-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6188f-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="6188f-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="6188f-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6188f-123">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="6188f-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="6188f-124">4.  Modificar el **habilitar optimizaciones** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="6188f-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6188f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6188f-125">Example</span></span>  
 <span data-ttu-id="6188f-126">El siguiente código compila `T2.vb` y habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="6188f-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="6188f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6188f-127">See Also</span></span>  
 [<span data-ttu-id="6188f-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6188f-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6188f-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6188f-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="6188f-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6188f-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6188f-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6188f-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
