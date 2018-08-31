---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 479f9f639548eb81351d1df3f8f08b29b393cba1
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257254"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="655bd-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="655bd-102">-moduleassemblyname</span></span>
<span data-ttu-id="655bd-103">Especifica el nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="655bd-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="655bd-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="655bd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="655bd-105">Arguments</span></span>  
  
|<span data-ttu-id="655bd-106">Término</span><span class="sxs-lookup"><span data-stu-id="655bd-106">Term</span></span>|<span data-ttu-id="655bd-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="655bd-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="655bd-108">El nombre del ensamblado que formará parte de este módulo.</span><span class="sxs-lookup"><span data-stu-id="655bd-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="655bd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="655bd-109">Remarks</span></span>  
 <span data-ttu-id="655bd-110">El compilador procesa los el `-moduleassemblyname` opción únicamente en caso el `-target:module` se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="655bd-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="655bd-111">Esto hace que el compilador crear un módulo.</span><span class="sxs-lookup"><span data-stu-id="655bd-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="655bd-112">El módulo creado por el compilador solo es válido para el ensamblado especificado con el `-moduleassemblyname` opción.</span><span class="sxs-lookup"><span data-stu-id="655bd-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="655bd-113">Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="655bd-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="655bd-114">El `-moduleassemblyname` opción es necesaria sólo cuando se cumplan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="655bd-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="655bd-115">Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="655bd-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="655bd-116">El ensamblado de referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará el módulo.</span><span class="sxs-lookup"><span data-stu-id="655bd-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="655bd-117">Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="655bd-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="655bd-118">Para obtener más información acerca de los ensamblados de confianza, consulte [ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="655bd-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="655bd-119">El `-moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="655bd-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655bd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="655bd-120">See Also</span></span>  
 [<span data-ttu-id="655bd-121">Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="655bd-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="655bd-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="655bd-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="655bd-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="655bd-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="655bd-124">-main</span><span class="sxs-lookup"><span data-stu-id="655bd-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="655bd-125">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="655bd-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="655bd-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="655bd-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="655bd-127">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="655bd-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="655bd-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="655bd-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="655bd-129">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="655bd-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
