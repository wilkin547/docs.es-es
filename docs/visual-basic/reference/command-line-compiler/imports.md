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
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="a69c6-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a69c6-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="a69c6-103">Importa los espacios de nombres desde un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="a69c6-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a69c6-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a69c6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a69c6-105">Arguments</span></span>  
  
|<span data-ttu-id="a69c6-106">Término</span><span class="sxs-lookup"><span data-stu-id="a69c6-106">Term</span></span>|<span data-ttu-id="a69c6-107">Definición</span><span class="sxs-lookup"><span data-stu-id="a69c6-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="a69c6-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a69c6-108">Required.</span></span> <span data-ttu-id="a69c6-109">Lista delimitada por comas de espacios de nombres que desea importar.</span><span class="sxs-lookup"><span data-stu-id="a69c6-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a69c6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a69c6-110">Remarks</span></span>  
 <span data-ttu-id="a69c6-111">El `/imports` opción importa cualquier espacio de nombres definido dentro del conjunto actual de archivos de origen o de cualquier ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a69c6-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="a69c6-112">Los miembros de un espacio de nombres especificado con `/imports` están disponibles para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a69c6-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="a69c6-113">Utilice la [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar un espacio de nombres en un archivo de código fuente individual.</span><span class="sxs-lookup"><span data-stu-id="a69c6-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="a69c6-114">Para establecer/importa en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a69c6-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a69c6-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a69c6-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a69c6-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a69c6-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a69c6-117">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="a69c6-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="a69c6-118">3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="a69c6-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="a69c6-119">4.  Haga clic en el **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="a69c6-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a69c6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a69c6-120">Example</span></span>  
 <span data-ttu-id="a69c6-121">El siguiente código compila cuando `/imports:system` se especifica.</span><span class="sxs-lookup"><span data-stu-id="a69c6-121">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a69c6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a69c6-122">See Also</span></span>  
 [<span data-ttu-id="a69c6-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a69c6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a69c6-124">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="a69c6-124">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="a69c6-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a69c6-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
