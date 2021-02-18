---
description: Más información sobre -moduleassemblyname
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 1b5daac8fea264e86b7200f3cead4cb657641000
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434321"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="e2794-103">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="e2794-103">-moduleassemblyname</span></span>

<span data-ttu-id="e2794-104">Especifica el nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="e2794-104">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2794-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2794-105">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2794-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e2794-106">Arguments</span></span>  
  
|<span data-ttu-id="e2794-107">Término</span><span class="sxs-lookup"><span data-stu-id="e2794-107">Term</span></span>|<span data-ttu-id="e2794-108">Definición</span><span class="sxs-lookup"><span data-stu-id="e2794-108">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="e2794-109">Nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="e2794-109">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2794-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2794-110">Remarks</span></span>  

 <span data-ttu-id="e2794-111">El compilador procesa la opción `-moduleassemblyname` solo si se ha especificado la opción `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="e2794-111">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="e2794-112">Esto hace que el compilador cree un módulo.</span><span class="sxs-lookup"><span data-stu-id="e2794-112">This causes the compiler to create a module.</span></span> <span data-ttu-id="e2794-113">El módulo creado por el compilador es válido únicamente en el ensamblado especificado con la opción `-moduleassemblyname`.</span><span class="sxs-lookup"><span data-stu-id="e2794-113">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="e2794-114">Si el módulo se coloca en otro ensamblado, se producirán errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e2794-114">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="e2794-115">La opción `-moduleassemblyname` solo es necesaria cuando se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e2794-115">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="e2794-116">Un tipo de datos del módulo necesita acceso a un tipo `Friend` en un ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e2794-116">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="e2794-117">El ensamblado al que se hace referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que el módulo se compilará.</span><span class="sxs-lookup"><span data-stu-id="e2794-117">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="e2794-118">Para más información sobre cómo crear un módulo, vea [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="e2794-118">For more information about creating a module, see [-target (Visual Basic)](target.md).</span></span> <span data-ttu-id="e2794-119">Para más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="e2794-119">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2794-120">La opción `-moduleassemblyname` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e2794-120">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2794-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2794-121">See also</span></span>

- [<span data-ttu-id="e2794-122">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="e2794-122">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="e2794-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2794-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e2794-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2794-124">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="e2794-125">-main</span><span class="sxs-lookup"><span data-stu-id="e2794-125">-main</span></span>](main.md)
- [<span data-ttu-id="e2794-126">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2794-126">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="e2794-127">-addmodule</span><span class="sxs-lookup"><span data-stu-id="e2794-127">-addmodule</span></span>](addmodule.md)
- [<span data-ttu-id="e2794-128">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="e2794-128">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e2794-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2794-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="e2794-130">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="e2794-130">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
