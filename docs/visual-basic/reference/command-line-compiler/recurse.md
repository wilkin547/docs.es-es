---
description: Mas información sobre -recurse
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2c0f1788c3811e24e2d51ff30e4cb2842aa0bd7a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475882"
---
# <a name="-recurse"></a><span data-ttu-id="55dc4-103">-recurse</span><span class="sxs-lookup"><span data-stu-id="55dc4-103">-recurse</span></span>

<span data-ttu-id="55dc4-104">Compila archivos de código fuente de todos los directorios secundarios del directorio especificado o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55dc4-104">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55dc4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55dc4-105">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="55dc4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="55dc4-106">Arguments</span></span>  

 `dir`  
 <span data-ttu-id="55dc4-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="55dc4-107">Optional.</span></span> <span data-ttu-id="55dc4-108">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="55dc4-108">The directory in which you want the search to begin.</span></span> <span data-ttu-id="55dc4-109">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55dc4-109">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="55dc4-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="55dc4-110">Required.</span></span> <span data-ttu-id="55dc4-111">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="55dc4-111">The file(s) to search for.</span></span> <span data-ttu-id="55dc4-112">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="55dc4-112">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55dc4-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55dc4-113">Remarks</span></span>  

 <span data-ttu-id="55dc4-114">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="55dc4-114">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="55dc4-115">Si no se especifica ningún nombre de archivo de salida, el compilador basa el nombre del archivo de salida en el primer archivo de entrada procesado.</span><span class="sxs-lookup"><span data-stu-id="55dc4-115">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="55dc4-116">Normalmente es el primer archivo de la lista de archivos compilados cuando está ordenada alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="55dc4-116">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="55dc4-117">Por esta razón, es mejor especificar un archivo de salida mediante la opción `-out`.</span><span class="sxs-lookup"><span data-stu-id="55dc4-117">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55dc4-118">La opción `-recurse` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="55dc4-118">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55dc4-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55dc4-119">Example</span></span>  

 <span data-ttu-id="55dc4-120">El siguiente comando compilar todos los archivos de Visual Basic del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="55dc4-120">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="55dc4-121">El siguiente comando compila todos los archivos de Visual Basic en el directorio `Test\ABC` y los directorios que haya por debajo y luego genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="55dc4-121">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="55dc4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="55dc4-122">See also</span></span>

- [<span data-ttu-id="55dc4-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55dc4-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="55dc4-124">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55dc4-124">-out (Visual Basic)</span></span>](out.md)
- [<span data-ttu-id="55dc4-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="55dc4-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
