---
description: Más información sobre -addmodule
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: ca08aa599003897e680240af21c4a0eb568e31d8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468296"
---
# <a name="-addmodule"></a><span data-ttu-id="a1adc-103">-addmodule</span><span class="sxs-lookup"><span data-stu-id="a1adc-103">-addmodule</span></span>

<span data-ttu-id="a1adc-104">Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="a1adc-104">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1adc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1adc-105">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a1adc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a1adc-106">Arguments</span></span>  

 `fileList`  
 <span data-ttu-id="a1adc-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a1adc-107">Required.</span></span> <span data-ttu-id="a1adc-108">Lista delimitada por comas de archivos que contienen metadatos, pero que no contienen manifiestos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1adc-108">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="a1adc-109">Los nombres de archivo que contienen espacios deben ir entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="a1adc-109">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1adc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1adc-110">Remarks</span></span>  

 <span data-ttu-id="a1adc-111">Los archivos mostrados con el parámetro `fileList` se deben crear con la opción `-target:module` o con otro equivalente del compilador para `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="a1adc-111">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="a1adc-112">Todos los módulos agregados con `-addmodule` deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1adc-112">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="a1adc-113">Es decir, se puede especificar un módulo de cualquier directorio en el tiempo de compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1adc-113">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="a1adc-114">Si no es así, obtendrá un error <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="a1adc-114">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="a1adc-115">Si especifica (implícita o explícitamente) cualquier opción [-target (Visual Basic)](target.md) que no sea `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` se convertirán en parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a1adc-115">If you specify (implicitly or explicitly) any[-target (Visual Basic)](target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="a1adc-116">Se requiere un ensamblado para ejecutar un archivo de salida que tenga uno o más archivos agregados con `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="a1adc-116">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="a1adc-117">Use [-reference (Visual Basic)](reference.md) para importar metadatos de un archivo que contenga un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1adc-117">Use [-reference (Visual Basic)](reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1adc-118">La opción `-addmodule` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a1adc-118">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1adc-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1adc-119">Example</span></span>  

 <span data-ttu-id="a1adc-120">En el código siguiente se crea un módulo.</span><span class="sxs-lookup"><span data-stu-id="a1adc-120">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="a1adc-121">En el código siguiente se importan los tipos del módulo.</span><span class="sxs-lookup"><span data-stu-id="a1adc-121">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="a1adc-122">Al ejecutar `t1`, genera `802`.</span><span class="sxs-lookup"><span data-stu-id="a1adc-122">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1adc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1adc-123">See also</span></span>

- [<span data-ttu-id="a1adc-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a1adc-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a1adc-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1adc-125">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="a1adc-126">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1adc-126">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="a1adc-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1adc-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
