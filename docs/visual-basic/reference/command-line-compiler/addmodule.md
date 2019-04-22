---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816439"
---
# <a name="-addmodule"></a><span data-ttu-id="02956-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="02956-102">-addmodule</span></span>
<span data-ttu-id="02956-103">Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="02956-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02956-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02956-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="02956-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="02956-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="02956-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="02956-106">Required.</span></span> <span data-ttu-id="02956-107">Lista delimitada por comas de los archivos que contienen metadatos pero no contienen manifiestos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02956-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="02956-108">Los nombres de archivo que contienen espacios deben ir entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="02956-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02956-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02956-109">Remarks</span></span>  
 <span data-ttu-id="02956-110">Los archivos mostrados por la `fileList` parámetro debe crearse con el `-target:module` opción, o con el equivalente de otro compilador a `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="02956-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="02956-111">Todos los módulos agregados mediante `-addmodule` debe estar en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02956-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="02956-112">Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02956-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="02956-113">Si no es así, obtendrá un <xref:System.TypeLoadException> error.</span><span class="sxs-lookup"><span data-stu-id="02956-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="02956-114">Si especifica (implícita o explícitamente) cualquier[-destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opción distinto `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` pasan formar parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="02956-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="02956-115">Se requiere un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados con `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="02956-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="02956-116">Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02956-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02956-117">El `-addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="02956-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02956-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02956-118">Example</span></span>  
 <span data-ttu-id="02956-119">El código siguiente crea un módulo.</span><span class="sxs-lookup"><span data-stu-id="02956-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="02956-120">El código siguiente importa los tipos del módulo.</span><span class="sxs-lookup"><span data-stu-id="02956-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="02956-121">Al ejecutar `t1`, lo que da como resultado `802`.</span><span class="sxs-lookup"><span data-stu-id="02956-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02956-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="02956-122">See also</span></span>

- [<span data-ttu-id="02956-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02956-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="02956-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02956-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="02956-125">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02956-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="02956-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="02956-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
