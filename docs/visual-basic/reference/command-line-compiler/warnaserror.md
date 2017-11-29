---
title: /warnaserror (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04b79b3d14a9c4a9f9721860cd1ed44032dfa5d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="3a432-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a432-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="3a432-103">Hace que el compilador trate la primera aparición de una advertencia como un error.</span><span class="sxs-lookup"><span data-stu-id="3a432-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a432-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a432-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a432-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3a432-105">Arguments</span></span>  
  
|<span data-ttu-id="3a432-106">Término</span><span class="sxs-lookup"><span data-stu-id="3a432-106">Term</span></span>|<span data-ttu-id="3a432-107">Definición</span><span class="sxs-lookup"><span data-stu-id="3a432-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="3a432-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="3a432-108">+ &#124; -</span></span>|<span data-ttu-id="3a432-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3a432-109">Optional.</span></span> <span data-ttu-id="3a432-110">De forma predeterminada, `/warnaserror-` está en vigor; las advertencias no impiden que el compilador produce un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="3a432-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="3a432-111">El `/warnaserror` opción, que es el mismo como `/warnaserror+`, hace que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="3a432-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="3a432-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3a432-112">Optional.</span></span> <span data-ttu-id="3a432-113">Lista delimitada por comas de Id. de la advertencia números a la que el `/warnaserror` opción se aplica.</span><span class="sxs-lookup"><span data-stu-id="3a432-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="3a432-114">Si se especifica ningún identificador de advertencia, el `/warnaserror` opción se aplica a todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="3a432-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a432-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a432-115">Remarks</span></span>  
 <span data-ttu-id="3a432-116">El `/warnaserror` opción trata todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="3a432-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="3a432-117">Los mensajes que normalmente se mostrarían como advertencias en su lugar se notifican como errores.</span><span class="sxs-lookup"><span data-stu-id="3a432-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="3a432-118">El compilador informa de las siguientes apariciones de la misma advertencia como advertencias.</span><span class="sxs-lookup"><span data-stu-id="3a432-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="3a432-119">De forma predeterminada, `/warnaserror-` está en vigor, lo que hace que las advertencias es sólo informativo.</span><span class="sxs-lookup"><span data-stu-id="3a432-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="3a432-120">El `/warnaserror` opción, que es el mismo como `/warnaserror+`, hace que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="3a432-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="3a432-121">Si desea que sólo se traten como errores algunas advertencias concretas, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.</span><span class="sxs-lookup"><span data-stu-id="3a432-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a432-122">El `/warnaserror` opción no controla cómo se muestran las advertencias.</span><span class="sxs-lookup"><span data-stu-id="3a432-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="3a432-123">Use la [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opción para deshabilitar las advertencias.</span><span class="sxs-lookup"><span data-stu-id="3a432-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="3a432-124">Para establecer /warnaserror para tratar todas las advertencias como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a432-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3a432-125">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3a432-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3a432-126">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3a432-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3a432-127">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="3a432-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="3a432-128">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3a432-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="3a432-129">3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.</span><span class="sxs-lookup"><span data-stu-id="3a432-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="3a432-130">4.  Compruebe el **tratar todas las advertencias como errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="3a432-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="3a432-131">Para establecer /warnaserror para tratar advertencias específicas como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a432-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3a432-132">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3a432-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3a432-133">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3a432-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="3a432-134">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3a432-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="3a432-135">3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.</span><span class="sxs-lookup"><span data-stu-id="3a432-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="3a432-136">4.  Asegúrese de que el **tratar todas las advertencias como errores** casilla de verificación está desactivada.</span><span class="sxs-lookup"><span data-stu-id="3a432-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="3a432-137">5.  Seleccione **Error** desde el **notificación** columna adyacente a la advertencia que se debe tratar como un error.</span><span class="sxs-lookup"><span data-stu-id="3a432-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3a432-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a432-138">Example</span></span>  
 <span data-ttu-id="3a432-139">El siguiente código compila `In.vb` e indica al compilador que muestre un error para la primera aparición de cada advertencia.</span><span class="sxs-lookup"><span data-stu-id="3a432-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="3a432-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a432-140">Example</span></span>  
 <span data-ttu-id="3a432-141">El siguiente código compila `T2.vb` y trata sólo la advertencia para las variables locales no utilizadas (42024) como un error.</span><span class="sxs-lookup"><span data-stu-id="3a432-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a432-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a432-142">See Also</span></span>  
 [<span data-ttu-id="3a432-143">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a432-143">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3a432-144">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a432-144">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="3a432-145">Configurar advertencias en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a432-145">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
