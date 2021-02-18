---
description: Más información sobre -removeintchecks
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
ms.openlocfilehash: 1dc484e1538718b68fe9f0cc450fa2480dc52412
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474101"
---
# <a name="-removeintchecks"></a><span data-ttu-id="5d596-103">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="5d596-103">-removeintchecks</span></span>

<span data-ttu-id="5d596-104">Activa o desactiva la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="5d596-104">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d596-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d596-105">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d596-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5d596-106">Arguments</span></span>  
  
|<span data-ttu-id="5d596-107">Término</span><span class="sxs-lookup"><span data-stu-id="5d596-107">Term</span></span>|<span data-ttu-id="5d596-108">Definición</span><span class="sxs-lookup"><span data-stu-id="5d596-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="5d596-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5d596-109">`+` &#124; `-`</span></span>|<span data-ttu-id="5d596-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5d596-110">Optional.</span></span> <span data-ttu-id="5d596-111">La opción `-removeintchecks-` hace que el compilador compruebe todos los cálculos de enteros en busca de errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="5d596-111">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="5d596-112">De manera predeterminada, es `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="5d596-112">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="5d596-113">Si especifica `-removeintchecks` o `-removeintchecks+`, se impide la comprobación de errores y puede realizar cálculos de enteros más rápido.</span><span class="sxs-lookup"><span data-stu-id="5d596-113">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="5d596-114">Pero si se cancela la comprobación de errores y si se desbordan las capacidades de tipo de datos, es posible que se almacenen resultados incorrectos sin que se genere ningún error.</span><span class="sxs-lookup"><span data-stu-id="5d596-114">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="5d596-115">Para definir -removeintchecks en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d596-115">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5d596-116">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="5d596-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5d596-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5d596-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5d596-118">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="5d596-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5d596-119">3.  Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="5d596-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="5d596-120">4.  Modifique el valor del cuadro **Quitar comprobaciones de desbordamiento con enteros**.</span><span class="sxs-lookup"><span data-stu-id="5d596-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5d596-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d596-121">Example</span></span>  

 <span data-ttu-id="5d596-122">El código siguiente compila `Test.vb` y desactiva la comprobación de errores de desbordamiento con enteros.</span><span class="sxs-lookup"><span data-stu-id="5d596-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d596-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d596-123">See also</span></span>

- [<span data-ttu-id="5d596-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d596-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="5d596-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d596-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
