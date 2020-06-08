---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 94a8b43a891df9837925869e17fac4536a995264
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414277"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="ccfbc-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccfbc-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="ccfbc-103">Causa que el compilador trate como un error la primera ocurrencia de una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfbc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccfbc-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ccfbc-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ccfbc-105">Arguments</span></span>  
  
|<span data-ttu-id="ccfbc-106">Término</span><span class="sxs-lookup"><span data-stu-id="ccfbc-106">Term</span></span>|<span data-ttu-id="ccfbc-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ccfbc-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ccfbc-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="ccfbc-108">+ &#124; -</span></span>|<span data-ttu-id="ccfbc-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-109">Optional.</span></span> <span data-ttu-id="ccfbc-110">De forma predeterminada, se aplica `-warnaserror-`; las advertencias no impiden que el compilador genere un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="ccfbc-111">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="ccfbc-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-112">Optional.</span></span> <span data-ttu-id="ccfbc-113">Lista delimitada por comas de los números de identificadores de advertencia a los que se aplica la opción `-warnaserror`.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="ccfbc-114">Si no se especifica ningún identificador de advertencia, la opción `-warnaserror` se aplica a todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccfbc-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccfbc-115">Remarks</span></span>  
 <span data-ttu-id="ccfbc-116">La opción `-warnaserror` trata todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="ccfbc-117">Todos los mensajes que, por norma general, deberían notificarse como advertencias, en su lugar se registran como errores.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="ccfbc-118">El compilador notifica como advertencias las ocurrencias posteriores de la misma advertencia.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="ccfbc-119">De forma predeterminada, se aplica `-warnaserror-`, que da lugar a que las advertencias tengan solo carácter informativo.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="ccfbc-120">La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="ccfbc-121">Si desea que solo algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencias que se deben tratar como errores.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccfbc-122">La opción `-warnaserror` no controla cómo se muestran las advertencias.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="ccfbc-123">Use la opción [-nowarn](nowarn.md) para deshabilitar las advertencias.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-123">Use the [-nowarn](nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="ccfbc-124">Para establecer -warnaserror a fin de tratar todas las advertencias como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ccfbc-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ccfbc-125">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ccfbc-126">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ccfbc-127">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ccfbc-128">3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ccfbc-129">4.  Active la casilla **Tratar todas las advertencias como errores**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="ccfbc-130">Para establecer - warnaserror a fin de tratar advertencias específicas como errores en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ccfbc-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ccfbc-131">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ccfbc-132">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="ccfbc-133">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ccfbc-134">3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ccfbc-135">4.  Asegúrese de que la casilla **Tratar todas las advertencias como errores** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="ccfbc-136">5.  Seleccione **Error** en la columna **Notificación** adyacente a la advertencia que se debe tratar como un error.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ccfbc-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccfbc-137">Example</span></span>  
 <span data-ttu-id="ccfbc-138">El siguiente código compila `In.vb` y ordena al compilador que muestre un error para la primera ocurrencia de cada advertencia que encuentra.</span><span class="sxs-lookup"><span data-stu-id="ccfbc-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="ccfbc-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccfbc-139">Example</span></span>  
 <span data-ttu-id="ccfbc-140">El siguiente código compila `T2.vb` y trata como un error solo la advertencia para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="ccfbc-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccfbc-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccfbc-141">See also</span></span>

- [<span data-ttu-id="ccfbc-142">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccfbc-142">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ccfbc-143">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccfbc-143">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="ccfbc-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccfbc-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
