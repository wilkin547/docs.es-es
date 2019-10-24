---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775635"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="c46c3-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="c46c3-102">-moduleassemblyname</span></span>
<span data-ttu-id="c46c3-103">Especifica el nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="c46c3-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c46c3-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="c46c3-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c46c3-105">Arguments</span></span>  
  
|<span data-ttu-id="c46c3-106">Término</span><span class="sxs-lookup"><span data-stu-id="c46c3-106">Term</span></span>|<span data-ttu-id="c46c3-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="c46c3-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="c46c3-108">Nombre del ensamblado del que formará parte este módulo.</span><span class="sxs-lookup"><span data-stu-id="c46c3-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c46c3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c46c3-109">Remarks</span></span>  
 <span data-ttu-id="c46c3-110">El compilador procesa la opción `-moduleassemblyname` solo si se ha especificado la opción `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="c46c3-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="c46c3-111">Esto hace que el compilador cree un módulo.</span><span class="sxs-lookup"><span data-stu-id="c46c3-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="c46c3-112">El módulo creado por el compilador solo es válido para el ensamblado especificado con la opción `-moduleassemblyname`.</span><span class="sxs-lookup"><span data-stu-id="c46c3-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="c46c3-113">Si coloca el módulo en otro ensamblado, se producirán errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c46c3-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="c46c3-114">La opción `-moduleassemblyname` solo es necesaria cuando se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c46c3-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="c46c3-115">Un tipo de datos del módulo necesita acceso a un `Friend` tipo de un ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="c46c3-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="c46c3-116">El ensamblado al que se hace referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se va a compilar el módulo.</span><span class="sxs-lookup"><span data-stu-id="c46c3-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="c46c3-117">Para obtener más información sobre cómo crear un módulo, vea [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="c46c3-117">For more information about creating a module, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="c46c3-118">Para obtener más información sobre los ensamblados de confianza, vea [ensamblados de confianza](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="c46c3-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c46c3-119">La opción `-moduleassemblyname` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c46c3-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46c3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c46c3-120">See also</span></span>

- [<span data-ttu-id="c46c3-121">Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="c46c3-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="c46c3-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c46c3-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c46c3-123">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c46c3-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="c46c3-124">-main</span><span class="sxs-lookup"><span data-stu-id="c46c3-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="c46c3-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c46c3-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="c46c3-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="c46c3-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="c46c3-127">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="c46c3-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="c46c3-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c46c3-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="c46c3-129">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="c46c3-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
