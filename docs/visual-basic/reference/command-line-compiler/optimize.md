---
description: Más información sobre -optimize
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 812eaa544dd874fd3871e58f366a34ee8176273a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426704"
---
# <a name="-optimize"></a><span data-ttu-id="162af-103">-optimize</span><span class="sxs-lookup"><span data-stu-id="162af-103">-optimize</span></span>

<span data-ttu-id="162af-104">Habilita o deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="162af-104">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="162af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="162af-105">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="162af-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="162af-106">Arguments</span></span>  
  
|<span data-ttu-id="162af-107">Término</span><span class="sxs-lookup"><span data-stu-id="162af-107">Term</span></span>|<span data-ttu-id="162af-108">Definición</span><span class="sxs-lookup"><span data-stu-id="162af-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="162af-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="162af-109">`+` &#124; `-`</span></span>|<span data-ttu-id="162af-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="162af-110">Optional.</span></span> <span data-ttu-id="162af-111">La opción `-optimize-` deshabilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="162af-111">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="162af-112">La opción `-optimize+` habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="162af-112">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="162af-113">De forma predeterminada, las optimizaciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="162af-113">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="162af-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="162af-114">Remarks</span></span>  

 <span data-ttu-id="162af-115">Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz.</span><span class="sxs-lookup"><span data-stu-id="162af-115">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="162af-116">Pero como las optimizaciones causan la reestructuración del código en el archivo de salida, `-optimize+` puede dificultar la depuración.</span><span class="sxs-lookup"><span data-stu-id="162af-116">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="162af-117">Todos los módulos generados con `-target:module` para un ensamblado deben usar la misma configuración de `-optimize` que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="162af-117">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="162af-118">Para obtener más información, vea [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="162af-118">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="162af-119">Puede combinar las opciones `-optimize` y `-debug`.</span><span class="sxs-lookup"><span data-stu-id="162af-119">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="162af-120">Para establecer -optimize en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="162af-120">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="162af-121">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="162af-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="162af-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="162af-122">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="162af-123">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="162af-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="162af-124">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="162af-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="162af-125">4.  Modifique la casilla **Habilitar optimizaciones**.</span><span class="sxs-lookup"><span data-stu-id="162af-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="162af-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="162af-126">Example</span></span>  

 <span data-ttu-id="162af-127">El código siguiente compila `T2.vb` y habilita las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="162af-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="162af-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="162af-128">See also</span></span>

- [<span data-ttu-id="162af-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="162af-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="162af-130">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="162af-130">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="162af-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="162af-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="162af-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="162af-132">-target (Visual Basic)</span></span>](target.md)
