---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8e9cd761263b3b61a4e6d3e33c5f7f875be7a1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="bf182-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf182-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="bf182-103">Importa los espacios de nombres desde un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="bf182-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf182-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf182-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf182-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bf182-105">Arguments</span></span>  
  
|<span data-ttu-id="bf182-106">Término</span><span class="sxs-lookup"><span data-stu-id="bf182-106">Term</span></span>|<span data-ttu-id="bf182-107">Definición</span><span class="sxs-lookup"><span data-stu-id="bf182-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="bf182-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="bf182-108">Required.</span></span> <span data-ttu-id="bf182-109">Lista delimitada por comas de espacios de nombres que desea importar.</span><span class="sxs-lookup"><span data-stu-id="bf182-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf182-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf182-110">Remarks</span></span>  
 <span data-ttu-id="bf182-111">El `/imports` opción importa cualquier espacio de nombres definido dentro del conjunto actual de archivos de origen o de cualquier ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bf182-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="bf182-112">Los miembros de un espacio de nombres especificado con `/imports` están disponibles para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="bf182-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="bf182-113">Utilice la [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar un espacio de nombres en un archivo de código fuente individual.</span><span class="sxs-lookup"><span data-stu-id="bf182-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="bf182-114">Para establecer/importa en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf182-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="bf182-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="bf182-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bf182-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf182-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="bf182-117">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="bf182-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="bf182-118">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="bf182-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="bf182-119">3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="bf182-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="bf182-120">4.  Haga clic en el **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="bf182-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf182-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf182-121">Example</span></span>  
 <span data-ttu-id="bf182-122">El siguiente código compila cuando `/imports:system` se especifica.</span><span class="sxs-lookup"><span data-stu-id="bf182-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bf182-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf182-123">See Also</span></span>  
 [<span data-ttu-id="bf182-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf182-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bf182-125">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="bf182-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="bf182-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf182-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
