---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095428"
---
# <a name="-recurse"></a><span data-ttu-id="b8fd2-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="b8fd2-102">-recurse</span></span>

<span data-ttu-id="b8fd2-103">Compila archivos de código fuente de todos los directorios secundarios del directorio especificado o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8fd2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8fd2-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8fd2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8fd2-105">Arguments</span></span>  

 `dir`  
 <span data-ttu-id="b8fd2-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-106">Optional.</span></span> <span data-ttu-id="b8fd2-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="b8fd2-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="b8fd2-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-109">Required.</span></span> <span data-ttu-id="b8fd2-110">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-110">The file(s) to search for.</span></span> <span data-ttu-id="b8fd2-111">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fd2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8fd2-112">Remarks</span></span>  

 <span data-ttu-id="b8fd2-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="b8fd2-114">Si no se especifica ningún nombre de archivo de salida, el compilador basa el nombre del archivo de salida en el primer archivo de entrada procesado.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="b8fd2-115">Normalmente es el primer archivo de la lista de archivos compilados cuando está ordenada alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="b8fd2-116">Por esta razón, es mejor especificar un archivo de salida mediante la opción `-out`.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8fd2-117">La opción `-recurse` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8fd2-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8fd2-118">Example</span></span>  

 <span data-ttu-id="b8fd2-119">El siguiente comando compilar todos los archivos de Visual Basic del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="b8fd2-120">El siguiente comando compila todos los archivos de Visual Basic en el directorio `Test\ABC` y los directorios que haya por debajo y luego genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="b8fd2-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8fd2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8fd2-121">See also</span></span>

- [<span data-ttu-id="b8fd2-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8fd2-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b8fd2-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8fd2-123">-out (Visual Basic)</span></span>](out.md)
- [<span data-ttu-id="b8fd2-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8fd2-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
