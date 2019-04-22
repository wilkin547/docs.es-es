---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2fe1834c3e92c3eff016ffd7857a0473eb2e8b3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816426"
---
# <a name="-recurse"></a><span data-ttu-id="3d0e1-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="3d0e1-102">-recurse</span></span>
<span data-ttu-id="3d0e1-103">Compila los archivos de código fuente de todos los subdirectorios del directorio especificado o el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d0e1-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d0e1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3d0e1-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="3d0e1-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-106">Optional.</span></span> <span data-ttu-id="3d0e1-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="3d0e1-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="3d0e1-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-109">Required.</span></span> <span data-ttu-id="3d0e1-110">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-110">The file(s) to search for.</span></span> <span data-ttu-id="3d0e1-111">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d0e1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d0e1-112">Remarks</span></span>  
 <span data-ttu-id="3d0e1-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="3d0e1-114">Si no se especifica ningún nombre de archivo de salida, el compilador utilizará el nombre de archivo de salida en el primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="3d0e1-115">Esto suele ser el primer archivo en la lista de archivos compilados ordenada alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="3d0e1-116">Por este motivo, es mejor especificar un archivo de salida mediante la `-out` opción.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d0e1-117">El `-recurse` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d0e1-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d0e1-118">Example</span></span>  
 <span data-ttu-id="3d0e1-119">El comando siguiente compila todos los archivos de Visual Basic en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="3d0e1-120">El comando siguiente compila todos los archivos de Visual Basic en el `Test\ABC` directory y los directorios por debajo de él y, a continuación, genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="3d0e1-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d0e1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d0e1-121">See also</span></span>

- [<span data-ttu-id="3d0e1-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d0e1-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3d0e1-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d0e1-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="3d0e1-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d0e1-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
