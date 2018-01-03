---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e157fb0e1fcdb3899440eed02a42b16f75541989
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a><span data-ttu-id="a5740-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="a5740-102">/optimize</span></span>
<span data-ttu-id="a5740-103">Habilita o deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="a5740-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5740-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5740-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5740-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a5740-105">Arguments</span></span>  
  
|<span data-ttu-id="a5740-106">Término</span><span class="sxs-lookup"><span data-stu-id="a5740-106">Term</span></span>|<span data-ttu-id="a5740-107">Definición</span><span class="sxs-lookup"><span data-stu-id="a5740-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="a5740-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a5740-108">`+` &#124; `-`</span></span>|<span data-ttu-id="a5740-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5740-109">Optional.</span></span> <span data-ttu-id="a5740-110">El `/optimize-` opción deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="a5740-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="a5740-111">El `/optimize+` opción habilita las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="a5740-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="a5740-112">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="a5740-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5740-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5740-113">Remarks</span></span>  
 <span data-ttu-id="a5740-114">Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="a5740-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="a5740-115">Sin embargo, dado que las optimizaciones causan la reestructuración del código en el archivo de salida, `/optimize+` puede dificultar la depuración.</span><span class="sxs-lookup"><span data-stu-id="a5740-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="a5740-116">Todos los módulos generados con `/target:module` para un ensamblado debe usar la misma `/optimize` configuración que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5740-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="a5740-117">Para obtener más información, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="a5740-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="a5740-118">Puede combinar la `/optimize` y `/debug` opciones.</span><span class="sxs-lookup"><span data-stu-id="a5740-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="a5740-119">Para establecer /optimize en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a5740-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a5740-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a5740-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a5740-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a5740-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="a5740-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="a5740-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a5740-123">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="a5740-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="a5740-124">4.  Modificar el **habilitar optimizaciones** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="a5740-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a5740-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5740-125">Example</span></span>  
 <span data-ttu-id="a5740-126">El siguiente código compila `T2.vb` y habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="a5740-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5740-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5740-127">See Also</span></span>  
 [<span data-ttu-id="a5740-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5740-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a5740-129">/Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5740-129">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="a5740-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5740-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="a5740-131">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5740-131">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
