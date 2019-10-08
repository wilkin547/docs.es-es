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
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005229"
---
# <a name="-removeintchecks"></a><span data-ttu-id="770d9-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="770d9-102">-removeintchecks</span></span>
<span data-ttu-id="770d9-103">Activa o desactiva la comprobación de errores de desbordamiento para operaciones de enteros.</span><span class="sxs-lookup"><span data-stu-id="770d9-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="770d9-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="770d9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="770d9-105">Arguments</span></span>  
  
|<span data-ttu-id="770d9-106">Término</span><span class="sxs-lookup"><span data-stu-id="770d9-106">Term</span></span>|<span data-ttu-id="770d9-107">Definición</span><span class="sxs-lookup"><span data-stu-id="770d9-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="770d9-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="770d9-108">`+` &#124; `-`</span></span>|<span data-ttu-id="770d9-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="770d9-109">Optional.</span></span> <span data-ttu-id="770d9-110">La opción `-removeintchecks-` hace que el compilador Compruebe todos los cálculos de enteros en busca de errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="770d9-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="770d9-111">De manera predeterminada, es `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="770d9-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="770d9-112">Si se especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y se pueden realizar cálculos de enteros con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="770d9-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="770d9-113">Sin embargo, sin la comprobación de errores y si las capacidades del tipo de datos se desbordan, los resultados incorrectos pueden almacenarse sin producir un error.</span><span class="sxs-lookup"><span data-stu-id="770d9-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="770d9-114">Para Set-removeintchecks (en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="770d9-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="770d9-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="770d9-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="770d9-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="770d9-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="770d9-117">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="770d9-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="770d9-118">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="770d9-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="770d9-119">4.  Modifique el valor de la casilla **quitar comprobaciones de desbordamiento de enteros** .</span><span class="sxs-lookup"><span data-stu-id="770d9-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="770d9-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="770d9-120">Example</span></span>  
 <span data-ttu-id="770d9-121">En el código siguiente se compila `Test.vb` y se desactiva la comprobación de errores de desbordamiento de enteros.</span><span class="sxs-lookup"><span data-stu-id="770d9-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="770d9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="770d9-122">See also</span></span>

- [<span data-ttu-id="770d9-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="770d9-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="770d9-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="770d9-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
