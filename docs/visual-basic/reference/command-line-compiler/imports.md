---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 380e71e462f736d4564a37b83567007fa9461b05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332964"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="ac8c5-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac8c5-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="ac8c5-103">Imports namespaces from a specified assembly.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac8c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac8c5-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac8c5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ac8c5-105">Arguments</span></span>  
  
|<span data-ttu-id="ac8c5-106">Término</span><span class="sxs-lookup"><span data-stu-id="ac8c5-106">Term</span></span>|<span data-ttu-id="ac8c5-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="ac8c5-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="ac8c5-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-108">Required.</span></span> <span data-ttu-id="ac8c5-109">Comma-delimited list of namespaces to be imported.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac8c5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac8c5-110">Remarks</span></span>  
 <span data-ttu-id="ac8c5-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="ac8c5-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="ac8c5-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="ac8c5-114">To set /imports in the Visual Studio integrated development environment</span><span class="sxs-lookup"><span data-stu-id="ac8c5-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ac8c5-115">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ac8c5-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ac8c5-117">2.  Click the **References** tab.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="ac8c5-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="ac8c5-119">4.  Click the **Add User Import** button.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac8c5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8c5-120">Example</span></span>  
 <span data-ttu-id="ac8c5-121">The following code compiles when `/imports:system.globalization` is specified.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="ac8c5-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="ac8c5-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="ac8c5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac8c5-123">See also</span></span>

- [<span data-ttu-id="ac8c5-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac8c5-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ac8c5-125">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="ac8c5-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="ac8c5-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac8c5-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
