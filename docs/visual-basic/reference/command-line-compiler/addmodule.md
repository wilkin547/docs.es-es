---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524479"
---
# <a name="-addmodule"></a><span data-ttu-id="059a2-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="059a2-102">-addmodule</span></span>
<span data-ttu-id="059a2-103">Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="059a2-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="059a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="059a2-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="059a2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="059a2-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="059a2-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="059a2-106">Required.</span></span> <span data-ttu-id="059a2-107">Lista delimitada por comas de archivos que contienen metadatos, pero que no contienen manifiestos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="059a2-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="059a2-108">Los nombres de archivo que contienen espacios deben ir entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="059a2-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="059a2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="059a2-109">Remarks</span></span>  
 <span data-ttu-id="059a2-110">Los archivos mostrados con el parámetro `fileList` se deben crear con la opción `-target:module` o con otro equivalente del compilador para `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="059a2-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="059a2-111">Todos los módulos agregados con `-addmodule` deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="059a2-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="059a2-112">Es decir, se puede especificar un módulo de cualquier directorio en el tiempo de compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="059a2-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="059a2-113">Si no es así, obtendrá un error <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="059a2-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="059a2-114">Si especifica (implícita o explícitamente) cualquier opción [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) que no sea `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` se convertirán en parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="059a2-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="059a2-115">Se requiere un ensamblado para ejecutar un archivo de salida que tenga uno o más archivos agregados con `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="059a2-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="059a2-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contenga un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="059a2-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="059a2-117">La opción `-addmodule` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="059a2-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="059a2-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="059a2-118">Example</span></span>  
 <span data-ttu-id="059a2-119">En el código siguiente se crea un módulo.</span><span class="sxs-lookup"><span data-stu-id="059a2-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="059a2-120">En el código siguiente se importan los tipos del módulo.</span><span class="sxs-lookup"><span data-stu-id="059a2-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="059a2-121">Al ejecutar `t1`, genera `802`.</span><span class="sxs-lookup"><span data-stu-id="059a2-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="059a2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="059a2-122">See also</span></span>

- [<span data-ttu-id="059a2-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="059a2-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="059a2-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="059a2-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="059a2-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="059a2-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="059a2-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="059a2-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
