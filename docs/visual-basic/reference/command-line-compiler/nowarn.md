---
title: -nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2f3f15ef12b24b8baedc9db59e772aa9eb073bc
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-nowarn"></a><span data-ttu-id="6d7da-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6d7da-102">-nowarn</span></span>
<span data-ttu-id="6d7da-103">Suprime la capacidad del compilador para generar advertencias.</span><span class="sxs-lookup"><span data-stu-id="6d7da-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d7da-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d7da-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6d7da-105">Arguments</span></span>  
  
|<span data-ttu-id="6d7da-106">Término</span><span class="sxs-lookup"><span data-stu-id="6d7da-106">Term</span></span>|<span data-ttu-id="6d7da-107">Definición</span><span class="sxs-lookup"><span data-stu-id="6d7da-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="6d7da-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6d7da-108">Optional.</span></span> <span data-ttu-id="6d7da-109">Lista delimitada por comas de los números de Id. de advertencia que el compilador debería suprimir.</span><span class="sxs-lookup"><span data-stu-id="6d7da-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="6d7da-110">Si no se especifican identificadores de advertencia, se suprimen todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="6d7da-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d7da-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d7da-111">Remarks</span></span>  
 <span data-ttu-id="6d7da-112">El `-nowarn` opción hace que el compilador no genere advertencias.</span><span class="sxs-lookup"><span data-stu-id="6d7da-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="6d7da-113">Para suprimir una advertencia individual, proporcione el identificador de advertencia para el `-nowarn` opción después de los dos puntos.</span><span class="sxs-lookup"><span data-stu-id="6d7da-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="6d7da-114">Separe varios números de advertencia con comas.</span><span class="sxs-lookup"><span data-stu-id="6d7da-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="6d7da-115">Debe especificar solo la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="6d7da-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="6d7da-116">Por ejemplo, si desea suprimir BC42024, la advertencia para las variables locales no usadas, especifique `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="6d7da-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="6d7da-117">Para obtener más información sobre los números de Id. de advertencia, consulte [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6d7da-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="6d7da-118">Para establecer - nowarn en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6d7da-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6d7da-119">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="6d7da-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6d7da-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6d7da-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6d7da-121">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="6d7da-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6d7da-122">3.  Seleccione el **deshabilitar todas las advertencias** casilla de verificación para deshabilitar todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="6d7da-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="6d7da-123">O bien</span><span class="sxs-lookup"><span data-stu-id="6d7da-123">- or -</span></span><br />     <span data-ttu-id="6d7da-124">Para deshabilitar una advertencia concreta, haga clic en **ninguno** desde la lista desplegable situada junto a la advertencia.</span><span class="sxs-lookup"><span data-stu-id="6d7da-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6d7da-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d7da-125">Example</span></span>  
 <span data-ttu-id="6d7da-126">El siguiente código compila `T2.vb` y no muestra las advertencias.</span><span class="sxs-lookup"><span data-stu-id="6d7da-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="6d7da-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d7da-127">Example</span></span>  
 <span data-ttu-id="6d7da-128">El siguiente código compila `T2.vb` y no muestra las advertencias para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="6d7da-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d7da-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d7da-129">See Also</span></span>  
 [<span data-ttu-id="6d7da-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d7da-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6d7da-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d7da-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6d7da-132">Configurar advertencias en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d7da-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
