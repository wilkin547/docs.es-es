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
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400479"
---
# <a name="-removeintchecks"></a><span data-ttu-id="73196-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="73196-102">-removeintchecks</span></span>
<span data-ttu-id="73196-103">Activa o desactiva la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="73196-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73196-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73196-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="73196-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73196-105">Arguments</span></span>  
  
|<span data-ttu-id="73196-106">Término</span><span class="sxs-lookup"><span data-stu-id="73196-106">Term</span></span>|<span data-ttu-id="73196-107">Definición</span><span class="sxs-lookup"><span data-stu-id="73196-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="73196-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="73196-108">`+` &#124; `-`</span></span>|<span data-ttu-id="73196-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73196-109">Optional.</span></span> <span data-ttu-id="73196-110">La opción `-removeintchecks-` hace que el compilador compruebe todos los cálculos de enteros en busca de errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="73196-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="73196-111">De manera predeterminada, es `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="73196-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="73196-112">Si especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y puede realizar cálculos de enteros más rápido.</span><span class="sxs-lookup"><span data-stu-id="73196-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="73196-113">Pero si se cancela la comprobación de errores y si se desbordan las capacidades de tipo de datos, es posible que se almacenen resultados incorrectos sin que se genere ningún error.</span><span class="sxs-lookup"><span data-stu-id="73196-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="73196-114">Para definir -removeintchecks en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73196-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="73196-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="73196-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73196-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="73196-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="73196-117">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="73196-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="73196-118">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="73196-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="73196-119">4.  Modifique el valor del cuadro **Quitar comprobaciones de desbordamiento con enteros**.</span><span class="sxs-lookup"><span data-stu-id="73196-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73196-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73196-120">Example</span></span>  
 <span data-ttu-id="73196-121">El código siguiente compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.</span><span class="sxs-lookup"><span data-stu-id="73196-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="73196-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="73196-122">See also</span></span>

- [<span data-ttu-id="73196-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73196-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="73196-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="73196-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
