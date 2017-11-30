---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a><span data-ttu-id="ff525-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="ff525-102">/removeintchecks</span></span>
<span data-ttu-id="ff525-103">Activa el error de desbordamiento para operaciones con enteros o desactivar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="ff525-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff525-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff525-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff525-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ff525-105">Arguments</span></span>  
  
|<span data-ttu-id="ff525-106">Término</span><span class="sxs-lookup"><span data-stu-id="ff525-106">Term</span></span>|<span data-ttu-id="ff525-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ff525-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ff525-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ff525-108">`+` &#124; `-`</span></span>|<span data-ttu-id="ff525-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ff525-109">Optional.</span></span> <span data-ttu-id="ff525-110">El `/removeintchecks-` opción hace que el compilador compruebe todos los cálculos de enteros para los errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="ff525-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="ff525-111">De manera predeterminada, es `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="ff525-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="ff525-112">Especificar `/removeintchecks` o `/removeintchecks+` evita la comprobación de errores y realizar cálculos de enteros más rápidos.</span><span class="sxs-lookup"><span data-stu-id="ff525-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="ff525-113">Sin embargo, sin comprobación de errores, y si se sobrepasan las capacidades de tipo de datos, se pueden almacenar resultados incorrectos cuando se genera un error.</span><span class="sxs-lookup"><span data-stu-id="ff525-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="ff525-114">Para establecer /removeintchecks en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="ff525-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ff525-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ff525-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ff525-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff525-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ff525-117">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="ff525-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="ff525-118">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ff525-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ff525-119">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="ff525-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="ff525-120">4.  Modificar el valor de la **Quitar comprobaciones de desbordamiento con enteros** cuadro.</span><span class="sxs-lookup"><span data-stu-id="ff525-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff525-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff525-121">Example</span></span>  
 <span data-ttu-id="ff525-122">El siguiente código compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.</span><span class="sxs-lookup"><span data-stu-id="ff525-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff525-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff525-123">See Also</span></span>  
 [<span data-ttu-id="ff525-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff525-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ff525-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff525-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
