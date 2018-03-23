---
title: -moduleassemblyname
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpett
ms.openlocfilehash: 0a097ea8a7e30f25a0abb877dc496fb81d1c139f
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="74d70-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="74d70-102">-moduleassemblyname</span></span>
<span data-ttu-id="74d70-103">Especifica el nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="74d70-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74d70-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="74d70-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="74d70-105">Arguments</span></span>  
  
|<span data-ttu-id="74d70-106">Término</span><span class="sxs-lookup"><span data-stu-id="74d70-106">Term</span></span>|<span data-ttu-id="74d70-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="74d70-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="74d70-108">El nombre del ensamblado que formará parte de este módulo.</span><span class="sxs-lookup"><span data-stu-id="74d70-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74d70-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74d70-109">Remarks</span></span>  
 <span data-ttu-id="74d70-110">Los procesos de compilador la `-moduleassemblyname` opción únicamente en caso el `-target:module` se ha especificado la opción.</span><span class="sxs-lookup"><span data-stu-id="74d70-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="74d70-111">Esto hace que el compilador crear un módulo.</span><span class="sxs-lookup"><span data-stu-id="74d70-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="74d70-112">El módulo creado por el compilador solo es válido para el ensamblado especificado con el `-moduleassemblyname` opción.</span><span class="sxs-lookup"><span data-stu-id="74d70-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="74d70-113">Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="74d70-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="74d70-114">El `-moduleassemblyname` opción es necesaria sólo cuando se cumple la siguiente:</span><span class="sxs-lookup"><span data-stu-id="74d70-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="74d70-115">Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="74d70-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="74d70-116">El ensamblado que se hace referencia ha concedido acceso de ensamblado de confianza para el ensamblado en el que se generará el módulo.</span><span class="sxs-lookup"><span data-stu-id="74d70-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="74d70-117">Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="74d70-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="74d70-118">Para obtener más información acerca de ensamblados de confianza, consulte [Friend (ensamblados)](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="74d70-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74d70-119">El `-moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible solo cuando se compila desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="74d70-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d70-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="74d70-120">See Also</span></span>  
 [<span data-ttu-id="74d70-121">Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="74d70-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="74d70-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74d70-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="74d70-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74d70-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="74d70-124">-main</span><span class="sxs-lookup"><span data-stu-id="74d70-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="74d70-125">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74d70-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="74d70-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="74d70-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="74d70-127">Ensamblados y Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="74d70-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="74d70-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="74d70-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="74d70-129">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="74d70-129">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
