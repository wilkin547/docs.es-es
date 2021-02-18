---
description: Más información sobre -warnaserror (Visual Basic)
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 38fc2d70f95228c715ef5ac4bfc9b4fdb6f67c0e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470102"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="68344-103">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68344-103">-warnaserror (Visual Basic)</span></span>

<span data-ttu-id="68344-104">Causa que el compilador trate como un error la primera ocurrencia de una advertencia.</span><span class="sxs-lookup"><span data-stu-id="68344-104">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68344-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68344-105">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="68344-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68344-106">Arguments</span></span>  
  
|<span data-ttu-id="68344-107">Término</span><span class="sxs-lookup"><span data-stu-id="68344-107">Term</span></span>|<span data-ttu-id="68344-108">Definición</span><span class="sxs-lookup"><span data-stu-id="68344-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="68344-109">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="68344-109">+ &#124; -</span></span>|<span data-ttu-id="68344-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="68344-110">Optional.</span></span> <span data-ttu-id="68344-111">De forma predeterminada, se aplica `-warnaserror-`; las advertencias no impiden que el compilador genere un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="68344-111">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="68344-112">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="68344-112">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="68344-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="68344-113">Optional.</span></span> <span data-ttu-id="68344-114">Lista delimitada por comas de los números de identificadores de advertencia a los que se aplica la opción `-warnaserror`.</span><span class="sxs-lookup"><span data-stu-id="68344-114">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="68344-115">Si no se especifica ningún identificador de advertencia, la opción `-warnaserror` se aplica a todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="68344-115">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68344-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68344-116">Remarks</span></span>  

 <span data-ttu-id="68344-117">La opción `-warnaserror` trata todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="68344-117">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="68344-118">Todos los mensajes que, por norma general, deberían notificarse como advertencias, en su lugar se registran como errores.</span><span class="sxs-lookup"><span data-stu-id="68344-118">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="68344-119">El compilador notifica como advertencias las ocurrencias posteriores de la misma advertencia.</span><span class="sxs-lookup"><span data-stu-id="68344-119">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="68344-120">De forma predeterminada, se aplica `-warnaserror-`, que da lugar a que las advertencias tengan solo carácter informativo.</span><span class="sxs-lookup"><span data-stu-id="68344-120">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="68344-121">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="68344-121">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="68344-122">Si desea que solo algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencias que se deben tratar como errores.</span><span class="sxs-lookup"><span data-stu-id="68344-122">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68344-123">La opción `-warnaserror` no controla cómo se muestran las advertencias.</span><span class="sxs-lookup"><span data-stu-id="68344-123">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="68344-124">Use la opción [-nowarn](nowarn.md) para deshabilitar las advertencias.</span><span class="sxs-lookup"><span data-stu-id="68344-124">Use the [-nowarn](nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="68344-125">Para establecer -warnaserror a fin de tratar todas las advertencias como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68344-125">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="68344-126">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="68344-126">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="68344-127">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="68344-127">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="68344-128">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="68344-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="68344-129">3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="68344-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="68344-130">4.  Active la casilla **Tratar todas las advertencias como errores**.</span><span class="sxs-lookup"><span data-stu-id="68344-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="68344-131">Para establecer - warnaserror a fin de tratar advertencias específicas como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68344-131">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="68344-132">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="68344-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="68344-133">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="68344-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="68344-134">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="68344-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="68344-135">3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="68344-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="68344-136">4.  Asegúrese de que la casilla **Tratar todas las advertencias como errores** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="68344-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="68344-137">5.  Seleccione **Error** en la columna **Notificación** adyacente a la advertencia que se debe tratar como un error.</span><span class="sxs-lookup"><span data-stu-id="68344-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="68344-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68344-138">Example</span></span>  

 <span data-ttu-id="68344-139">El siguiente código compila `In.vb` y ordena al compilador que muestre un error para la primera ocurrencia de cada advertencia que encuentra.</span><span class="sxs-lookup"><span data-stu-id="68344-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="68344-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68344-140">Example</span></span>  

 <span data-ttu-id="68344-141">El siguiente código compila `T2.vb` y trata como un error solo la advertencia para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="68344-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="68344-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="68344-142">See also</span></span>

- [<span data-ttu-id="68344-143">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68344-143">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="68344-144">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="68344-144">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="68344-145">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68344-145">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
