---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962461"
---
# <a name="-addmodule"></a><span data-ttu-id="acf7a-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="acf7a-102">-addmodule</span></span>
<span data-ttu-id="acf7a-103">Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="acf7a-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acf7a-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="acf7a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="acf7a-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="acf7a-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="acf7a-106">Required.</span></span> <span data-ttu-id="acf7a-107">Lista delimitada por comas de archivos que contienen metadatos, pero que no contienen manifiestos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="acf7a-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="acf7a-108">Los nombres de archivo que contienen espacios deben ir entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="acf7a-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acf7a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acf7a-109">Remarks</span></span>  
 <span data-ttu-id="acf7a-110">Los archivos enumerados por `fileList` el parámetro se deben crear con `-target:module` la opción o con otro equivalente del compilador para `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="acf7a-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="acf7a-111">Todos los módulos agregados con `-addmodule` deben estar en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="acf7a-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="acf7a-112">Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="acf7a-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="acf7a-113">Si no es así, obtendrá un <xref:System.TypeLoadException> error.</span><span class="sxs-lookup"><span data-stu-id="acf7a-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="acf7a-114">Si especifica (implícita o explícitamente) la opción any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) que no `-target:module` sea `-addmodule`with, los archivos que pase `-addmodule` se convertirán en parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="acf7a-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="acf7a-115">Un ensamblado es necesario para ejecutar un archivo de salida que tiene uno o más archivos `-addmodule`agregados con.</span><span class="sxs-lookup"><span data-stu-id="acf7a-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="acf7a-116">Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contenga un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="acf7a-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acf7a-117">La `-addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="acf7a-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acf7a-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acf7a-118">Example</span></span>  
 <span data-ttu-id="acf7a-119">En el código siguiente se crea un módulo.</span><span class="sxs-lookup"><span data-stu-id="acf7a-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="acf7a-120">En el código siguiente se importan los tipos del módulo.</span><span class="sxs-lookup"><span data-stu-id="acf7a-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="acf7a-121">Al ejecutar `t1`, se genera `802`.</span><span class="sxs-lookup"><span data-stu-id="acf7a-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf7a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="acf7a-122">See also</span></span>

- [<span data-ttu-id="acf7a-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acf7a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="acf7a-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acf7a-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="acf7a-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acf7a-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="acf7a-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="acf7a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
