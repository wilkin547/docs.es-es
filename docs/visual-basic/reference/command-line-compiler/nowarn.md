---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828217"
---
# <a name="-nowarn"></a><span data-ttu-id="4bd11-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="4bd11-102">-nowarn</span></span>
<span data-ttu-id="4bd11-103">Suprime la capacidad del compilador para generar advertencias.</span><span class="sxs-lookup"><span data-stu-id="4bd11-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bd11-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4bd11-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4bd11-105">Arguments</span></span>  
  
|<span data-ttu-id="4bd11-106">Término</span><span class="sxs-lookup"><span data-stu-id="4bd11-106">Term</span></span>|<span data-ttu-id="4bd11-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="4bd11-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="4bd11-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4bd11-108">Optional.</span></span> <span data-ttu-id="4bd11-109">Lista delimitada por comas de los números de Id. de advertencia que el compilador debe suprimir.</span><span class="sxs-lookup"><span data-stu-id="4bd11-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="4bd11-110">Si no se especifican los identificadores de advertencia, se suprimen todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="4bd11-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bd11-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4bd11-111">Remarks</span></span>  
 <span data-ttu-id="4bd11-112">El `-nowarn` opción hace que el compilador no genere advertencias.</span><span class="sxs-lookup"><span data-stu-id="4bd11-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="4bd11-113">Para suprimir una advertencia individual, proporcione el identificador de advertencia para el `-nowarn` opción siguiendo los dos puntos.</span><span class="sxs-lookup"><span data-stu-id="4bd11-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="4bd11-114">Separe varios números de advertencia con comas.</span><span class="sxs-lookup"><span data-stu-id="4bd11-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="4bd11-115">Deberá especificar solo la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="4bd11-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="4bd11-116">Por ejemplo, especifique si desea suprimir BC42024, la advertencia para las variables locales no utilizadas, `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="4bd11-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="4bd11-117">Para obtener más información sobre los números de Id. de advertencia, consulte [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4bd11-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="4bd11-118">Para establecer - nowarn en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4bd11-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4bd11-119">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="4bd11-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4bd11-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4bd11-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4bd11-121">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="4bd11-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4bd11-122">3.  Seleccione el **deshabilitar todas las advertencias** casilla para deshabilitar todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="4bd11-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="4bd11-123">o bien</span><span class="sxs-lookup"><span data-stu-id="4bd11-123">- or -</span></span><br />     <span data-ttu-id="4bd11-124">Para deshabilitar una advertencia concreta, haga clic en **ninguno** en la lista desplegable junto a la advertencia.</span><span class="sxs-lookup"><span data-stu-id="4bd11-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4bd11-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bd11-125">Example</span></span>  
 <span data-ttu-id="4bd11-126">El siguiente código compila `T2.vb` y no muestra las advertencias.</span><span class="sxs-lookup"><span data-stu-id="4bd11-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="4bd11-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bd11-127">Example</span></span>  
 <span data-ttu-id="4bd11-128">El siguiente código compila `T2.vb` y no muestra las advertencias para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="4bd11-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bd11-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bd11-129">See also</span></span>

- [<span data-ttu-id="4bd11-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bd11-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4bd11-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bd11-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4bd11-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bd11-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
