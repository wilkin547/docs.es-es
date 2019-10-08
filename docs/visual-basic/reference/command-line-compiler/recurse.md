---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 71613af0f1c319801296180d49dbacfedf0ceca4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005250"
---
# <a name="-recurse"></a><span data-ttu-id="176d7-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="176d7-102">-recurse</span></span>
<span data-ttu-id="176d7-103">Compila los archivos de código fuente en todos los directorios secundarios del directorio especificado o del directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="176d7-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="176d7-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="176d7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="176d7-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="176d7-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="176d7-106">Optional.</span></span> <span data-ttu-id="176d7-107">El directorio en el que quiere que comience la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="176d7-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="176d7-108">Si no se especifica, la búsqueda comienza en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="176d7-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="176d7-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="176d7-109">Required.</span></span> <span data-ttu-id="176d7-110">Los archivos que buscará.</span><span class="sxs-lookup"><span data-stu-id="176d7-110">The file(s) to search for.</span></span> <span data-ttu-id="176d7-111">Se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="176d7-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="176d7-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="176d7-112">Remarks</span></span>  
 <span data-ttu-id="176d7-113">Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="176d7-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="176d7-114">Si no se especifica ningún nombre de archivo de salida, el compilador basa el nombre del archivo de salida en el primer archivo de entrada procesado.</span><span class="sxs-lookup"><span data-stu-id="176d7-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="176d7-115">Normalmente es el primer archivo de la lista de archivos compilados cuando se ve en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="176d7-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="176d7-116">Por esta razón, es mejor especificar un archivo de salida mediante la opción `-out`.</span><span class="sxs-lookup"><span data-stu-id="176d7-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="176d7-117">La opción `-recurse` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="176d7-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="176d7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="176d7-118">Example</span></span>  
 <span data-ttu-id="176d7-119">El comando siguiente compila todos los archivos de Visual Basic en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="176d7-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="176d7-120">El comando siguiente compila todos los archivos de Visual Basic en el directorio `Test\ABC` y en los directorios situados por debajo de él y, a continuación, genera `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="176d7-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="176d7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="176d7-121">See also</span></span>

- [<span data-ttu-id="176d7-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="176d7-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="176d7-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="176d7-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="176d7-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="176d7-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
