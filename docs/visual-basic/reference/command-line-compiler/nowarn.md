---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653447"
---
# <a name="-nowarn"></a><span data-ttu-id="8cb72-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="8cb72-102">-nowarn</span></span>
<span data-ttu-id="8cb72-103">Suprime la capacidad del compilador para generar advertencias.</span><span class="sxs-lookup"><span data-stu-id="8cb72-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cb72-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8cb72-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8cb72-105">Arguments</span></span>  
  
|<span data-ttu-id="8cb72-106">Término</span><span class="sxs-lookup"><span data-stu-id="8cb72-106">Term</span></span>|<span data-ttu-id="8cb72-107">Definición</span><span class="sxs-lookup"><span data-stu-id="8cb72-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="8cb72-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8cb72-108">Optional.</span></span> <span data-ttu-id="8cb72-109">Lista delimitada por comas de los números de Id. de advertencia que el compilador debería suprimir.</span><span class="sxs-lookup"><span data-stu-id="8cb72-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="8cb72-110">Si no se especifican identificadores de advertencia, se suprimen todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="8cb72-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cb72-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8cb72-111">Remarks</span></span>  
 <span data-ttu-id="8cb72-112">El `-nowarn` opción hace que el compilador no genere advertencias.</span><span class="sxs-lookup"><span data-stu-id="8cb72-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="8cb72-113">Para suprimir una advertencia individual, proporcione el identificador de advertencia para el `-nowarn` opción después de los dos puntos.</span><span class="sxs-lookup"><span data-stu-id="8cb72-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="8cb72-114">Separe varios números de advertencia con comas.</span><span class="sxs-lookup"><span data-stu-id="8cb72-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="8cb72-115">Debe especificar solo la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="8cb72-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="8cb72-116">Por ejemplo, si desea suprimir BC42024, la advertencia para las variables locales no usadas, especifique `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="8cb72-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="8cb72-117">Para obtener más información sobre los números de Id. de advertencia, consulte [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8cb72-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="8cb72-118">Para establecer - nowarn en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8cb72-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8cb72-119">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="8cb72-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8cb72-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8cb72-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="8cb72-121">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="8cb72-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8cb72-122">3.  Seleccione el **deshabilitar todas las advertencias** casilla de verificación para deshabilitar todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="8cb72-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="8cb72-123">O bien</span><span class="sxs-lookup"><span data-stu-id="8cb72-123">- or -</span></span><br />     <span data-ttu-id="8cb72-124">Para deshabilitar una advertencia concreta, haga clic en **ninguno** desde la lista desplegable situada junto a la advertencia.</span><span class="sxs-lookup"><span data-stu-id="8cb72-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8cb72-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cb72-125">Example</span></span>  
 <span data-ttu-id="8cb72-126">El siguiente código compila `T2.vb` y no muestra las advertencias.</span><span class="sxs-lookup"><span data-stu-id="8cb72-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="8cb72-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cb72-127">Example</span></span>  
 <span data-ttu-id="8cb72-128">El siguiente código compila `T2.vb` y no muestra las advertencias para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="8cb72-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cb72-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cb72-129">See Also</span></span>  
 [<span data-ttu-id="8cb72-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cb72-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8cb72-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cb72-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="8cb72-132">Configurar advertencias en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cb72-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
