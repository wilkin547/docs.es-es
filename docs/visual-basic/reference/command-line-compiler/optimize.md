---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097597"
---
# <a name="-optimize"></a><span data-ttu-id="276d1-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="276d1-102">-optimize</span></span>

<span data-ttu-id="276d1-103">Habilita o deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="276d1-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="276d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="276d1-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="276d1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="276d1-105">Arguments</span></span>  
  
|<span data-ttu-id="276d1-106">Término</span><span class="sxs-lookup"><span data-stu-id="276d1-106">Term</span></span>|<span data-ttu-id="276d1-107">Definición</span><span class="sxs-lookup"><span data-stu-id="276d1-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="276d1-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="276d1-108">`+` &#124; `-`</span></span>|<span data-ttu-id="276d1-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="276d1-109">Optional.</span></span> <span data-ttu-id="276d1-110">La opción `-optimize-` deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="276d1-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="276d1-111">La opción `-optimize+` habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="276d1-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="276d1-112">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="276d1-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="276d1-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="276d1-113">Remarks</span></span>  

 <span data-ttu-id="276d1-114">Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="276d1-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="276d1-115">Pero como las optimizaciones causan la reestructuración del código en el archivo de salida, `-optimize+` puede dificultar la depuración.</span><span class="sxs-lookup"><span data-stu-id="276d1-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="276d1-116">Todos los módulos generados con `-target:module` para un ensamblado deben usar la misma configuración de `-optimize` que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="276d1-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="276d1-117">Para obtener más información, vea [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="276d1-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="276d1-118">Puede combinar las opciones `-optimize` y `-debug`.</span><span class="sxs-lookup"><span data-stu-id="276d1-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="276d1-119">Para establecer -optimize en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="276d1-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="276d1-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="276d1-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="276d1-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="276d1-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="276d1-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="276d1-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="276d1-123">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="276d1-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="276d1-124">4.  Modifique la casilla **Habilitar optimizaciones**.</span><span class="sxs-lookup"><span data-stu-id="276d1-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="276d1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="276d1-125">Example</span></span>  

 <span data-ttu-id="276d1-126">El código siguiente compila `T2.vb` y habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="276d1-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="276d1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="276d1-127">See also</span></span>

- [<span data-ttu-id="276d1-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="276d1-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="276d1-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="276d1-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="276d1-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="276d1-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="276d1-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="276d1-131">-target (Visual Basic)</span></span>](target.md)
