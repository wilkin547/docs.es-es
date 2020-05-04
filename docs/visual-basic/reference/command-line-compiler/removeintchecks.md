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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005229"
---
# <a name="-removeintchecks"></a><span data-ttu-id="2b63f-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="2b63f-102">-removeintchecks</span></span>
<span data-ttu-id="2b63f-103">Activa o desactiva la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="2b63f-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b63f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b63f-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b63f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2b63f-105">Arguments</span></span>  
  
|<span data-ttu-id="2b63f-106">Término</span><span class="sxs-lookup"><span data-stu-id="2b63f-106">Term</span></span>|<span data-ttu-id="2b63f-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2b63f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2b63f-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2b63f-108">`+` &#124; `-`</span></span>|<span data-ttu-id="2b63f-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b63f-109">Optional.</span></span> <span data-ttu-id="2b63f-110">La opción `-removeintchecks-` hace que el compilador compruebe todos los cálculos de enteros en busca de errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="2b63f-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="2b63f-111">De manera predeterminada, es `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="2b63f-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="2b63f-112">Si especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y puede realizar cálculos de enteros más rápido.</span><span class="sxs-lookup"><span data-stu-id="2b63f-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="2b63f-113">Pero si se cancela la comprobación de errores y si se desbordan las capacidades de tipo de datos, es posible que se almacenen resultados incorrectos sin que se genere ningún error.</span><span class="sxs-lookup"><span data-stu-id="2b63f-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="2b63f-114">Para definir -removeintchecks en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2b63f-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2b63f-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2b63f-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2b63f-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2b63f-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2b63f-117">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="2b63f-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2b63f-118">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="2b63f-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="2b63f-119">4.  Modifique el valor del cuadro **Quitar comprobaciones de desbordamiento con enteros**.</span><span class="sxs-lookup"><span data-stu-id="2b63f-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b63f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b63f-120">Example</span></span>  
 <span data-ttu-id="2b63f-121">El código siguiente compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.</span><span class="sxs-lookup"><span data-stu-id="2b63f-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b63f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b63f-122">See also</span></span>

- [<span data-ttu-id="2b63f-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b63f-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2b63f-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b63f-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
