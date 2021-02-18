---
description: Mas información sobre -nowarn
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 4fb7d39aef48ff1443c342367f9e20bb37f9c5e0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434867"
---
# <a name="-nowarn"></a><span data-ttu-id="a01ba-103">-nowarn</span><span class="sxs-lookup"><span data-stu-id="a01ba-103">-nowarn</span></span>

<span data-ttu-id="a01ba-104">Suprime la capacidad del compilador para generar advertencias.</span><span class="sxs-lookup"><span data-stu-id="a01ba-104">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a01ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a01ba-105">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a01ba-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a01ba-106">Arguments</span></span>  
  
|<span data-ttu-id="a01ba-107">Término</span><span class="sxs-lookup"><span data-stu-id="a01ba-107">Term</span></span>|<span data-ttu-id="a01ba-108">Definición</span><span class="sxs-lookup"><span data-stu-id="a01ba-108">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="a01ba-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a01ba-109">Optional.</span></span> <span data-ttu-id="a01ba-110">Lista delimitada por comas de los números de id. de advertencia que el compilador debe suprimir.</span><span class="sxs-lookup"><span data-stu-id="a01ba-110">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="a01ba-111">Si no se especifican los id. de advertencia, se suprimen todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="a01ba-111">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a01ba-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a01ba-112">Remarks</span></span>  

 <span data-ttu-id="a01ba-113">La opción `-nowarn` hace que el compilador no genere advertencias.</span><span class="sxs-lookup"><span data-stu-id="a01ba-113">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="a01ba-114">Para suprimir una advertencia individual, proporcione el id. de advertencia a la opción `-nowarn` que aparece después de los dos puntos.</span><span class="sxs-lookup"><span data-stu-id="a01ba-114">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="a01ba-115">Separe varios números de advertencia mediante comas.</span><span class="sxs-lookup"><span data-stu-id="a01ba-115">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="a01ba-116">Solo tendrá que especificar la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="a01ba-116">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="a01ba-117">Por ejemplo, si quiere suprimir BC42024, la advertencia para las variables locales no utilizadas, especifique `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="a01ba-117">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="a01ba-118">Para obtener más información sobre los números de id. de advertencia, vea [Configuración de advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a01ba-118">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="a01ba-119">Para establecer -nowarn en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a01ba-119">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a01ba-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a01ba-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a01ba-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a01ba-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a01ba-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="a01ba-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a01ba-123">3.  Active la casilla **Deshabilitar todas las advertencias** para deshabilitar todas las advertencias.</span><span class="sxs-lookup"><span data-stu-id="a01ba-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="a01ba-124">o bien</span><span class="sxs-lookup"><span data-stu-id="a01ba-124">- or -</span></span><br />     <span data-ttu-id="a01ba-125">Para deshabilitar una advertencia concreta, haga clic en **Ninguno** en la lista desplegable situada junto a la advertencia.</span><span class="sxs-lookup"><span data-stu-id="a01ba-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a01ba-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a01ba-126">Example</span></span>  

 <span data-ttu-id="a01ba-127">El código siguiente compila `T2.vb` y no muestra ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="a01ba-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="a01ba-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a01ba-128">Example</span></span>  

 <span data-ttu-id="a01ba-129">El código compila `T2.vb` siguiente y no muestra las advertencias para las variables locales no utilizadas (42024).</span><span class="sxs-lookup"><span data-stu-id="a01ba-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a01ba-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a01ba-130">See also</span></span>

- [<span data-ttu-id="a01ba-131">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a01ba-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a01ba-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a01ba-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="a01ba-133">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a01ba-133">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
