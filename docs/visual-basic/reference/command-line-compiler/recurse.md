---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a><span data-ttu-id="b8fa8-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="b8fa8-102">/recurse</span></span>
<span data-ttu-id="b8fa8-103">Compila archivos de código fuente de todos los subdirectorios del directorio especificado o el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8fa8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8fa8-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8fa8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8fa8-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="b8fa8-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-106">Optional.</span></span> <span data-ttu-id="b8fa8-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="b8fa8-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="b8fa8-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-109">Required.</span></span> <span data-ttu-id="b8fa8-110">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-110">The file(s) to search for.</span></span> <span data-ttu-id="b8fa8-111">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fa8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8fa8-112">Remarks</span></span>  
 <span data-ttu-id="b8fa8-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `/recurse`.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="b8fa8-114">Si no se especifica ningún nombre de archivo de salida, el compilador utilizará el nombre de archivo de salida en el primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="b8fa8-115">Por lo general, suele ser el primer archivo en la lista de archivos compilados ordenada alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="b8fa8-116">Por esta razón, es mejor especificar un archivo de salida mediante la `/out` opción.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8fa8-117">El `/recurse` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8fa8-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8fa8-118">Example</span></span>  
 <span data-ttu-id="b8fa8-119">El siguiente código compila todos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-119">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="b8fa8-120">El siguiente código compila todos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el `Test\ABC` directory y los directorios por debajo de él y, a continuación, genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="b8fa8-120">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8fa8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8fa8-121">See Also</span></span>  
 [<span data-ttu-id="b8fa8-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8fa8-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b8fa8-123">entrada/salida (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8fa8-123">/out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="b8fa8-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8fa8-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
