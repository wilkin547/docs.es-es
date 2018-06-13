---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2fefdf81ab25d2e109f265f0c895a3415ad5673d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656011"
---
# <a name="-addmodule"></a><span data-ttu-id="c647d-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="c647d-102">-addmodule</span></span>
<span data-ttu-id="c647d-103">Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="c647d-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c647d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c647d-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="c647d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c647d-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="c647d-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="c647d-106">Required.</span></span> <span data-ttu-id="c647d-107">Lista delimitada por comas de los archivos que contienen metadatos pero no contienen manifiestos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c647d-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="c647d-108">Nombres de archivo que contienen espacios deben ir entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="c647d-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c647d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c647d-109">Remarks</span></span>  
 <span data-ttu-id="c647d-110">Los archivos mostrados por la `fileList` parámetro debe crearse con el `-target:module` opción, o con el equivalente de otro compilador a `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="c647d-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="c647d-111">Todos los módulos agregados con `-addmodule` debe estar en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c647d-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="c647d-112">Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c647d-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="c647d-113">Si no es así, obtendrá una <xref:System.TypeLoadException> error.</span><span class="sxs-lookup"><span data-stu-id="c647d-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="c647d-114">Si especifica (implícita o explícitamente) cualquier[-destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opción distinto de `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` pasan a formar parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c647d-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="c647d-115">Se requiere un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados mediante `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="c647d-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="c647d-116">Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c647d-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c647d-117">El `-addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c647d-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c647d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c647d-118">Example</span></span>  
 <span data-ttu-id="c647d-119">El siguiente código crea un módulo.</span><span class="sxs-lookup"><span data-stu-id="c647d-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 <span data-ttu-id="c647d-120">El siguiente código importa los tipos del módulo.</span><span class="sxs-lookup"><span data-stu-id="c647d-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 <span data-ttu-id="c647d-121">Al ejecutar `t1`, genera `802`.</span><span class="sxs-lookup"><span data-stu-id="c647d-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c647d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c647d-122">See Also</span></span>  
 [<span data-ttu-id="c647d-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c647d-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c647d-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c647d-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c647d-125">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c647d-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="c647d-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c647d-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
