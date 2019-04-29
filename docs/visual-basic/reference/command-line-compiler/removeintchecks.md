---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788770"
---
# <a name="-removeintchecks"></a><span data-ttu-id="cf457-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="cf457-102">-removeintchecks</span></span>
<span data-ttu-id="cf457-103">Activa el error de desbordamiento para operaciones con enteros o desactivar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="cf457-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf457-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf457-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf457-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cf457-105">Arguments</span></span>  
  
|<span data-ttu-id="cf457-106">Término</span><span class="sxs-lookup"><span data-stu-id="cf457-106">Term</span></span>|<span data-ttu-id="cf457-107">Definición</span><span class="sxs-lookup"><span data-stu-id="cf457-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="cf457-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="cf457-108">`+` &#124; `-`</span></span>|<span data-ttu-id="cf457-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf457-109">Optional.</span></span> <span data-ttu-id="cf457-110">El `-removeintchecks-` opción hace que el compilador compruebe todos los cálculos de enteros para los errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="cf457-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="cf457-111">De manera predeterminada, es `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="cf457-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="cf457-112">Especificar `-removeintchecks` o `-removeintchecks+` evita la comprobación de errores y realizar los cálculos de enteros más rápidos.</span><span class="sxs-lookup"><span data-stu-id="cf457-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="cf457-113">Sin embargo, sin comprobación de errores, y si se sobrepasan las capacidades de tipo de datos, se podrán almacenar resultados incorrectos sin provocar un error.</span><span class="sxs-lookup"><span data-stu-id="cf457-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="cf457-114">Para establecer - removeintchecks en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cf457-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="cf457-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="cf457-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cf457-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf457-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="cf457-117">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="cf457-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="cf457-118">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="cf457-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="cf457-119">4.  Modificar el valor de la **Quitar comprobaciones de desbordamiento con enteros** cuadro.</span><span class="sxs-lookup"><span data-stu-id="cf457-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cf457-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf457-120">Example</span></span>  
 <span data-ttu-id="cf457-121">El siguiente código compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.</span><span class="sxs-lookup"><span data-stu-id="cf457-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf457-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf457-122">See also</span></span>

- [<span data-ttu-id="cf457-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf457-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cf457-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf457-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
