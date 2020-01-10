---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 2a1dd19189ff65413255b9bc137e1a7f0227bbe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716646"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="56b97-102">-Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56b97-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="56b97-103">Importa los espacios de nombres de un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="56b97-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56b97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56b97-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="56b97-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="56b97-105">Arguments</span></span>  
  
|<span data-ttu-id="56b97-106">Término</span><span class="sxs-lookup"><span data-stu-id="56b97-106">Term</span></span>|<span data-ttu-id="56b97-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="56b97-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="56b97-108">Obligatoria.</span><span class="sxs-lookup"><span data-stu-id="56b97-108">Required.</span></span> <span data-ttu-id="56b97-109">Lista delimitada por comas de los espacios de nombres que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="56b97-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56b97-110">Notas</span><span class="sxs-lookup"><span data-stu-id="56b97-110">Remarks</span></span>  
 <span data-ttu-id="56b97-111">La opción `-imports` importa cualquier espacio de nombres definido en el conjunto actual de archivos de código fuente o desde cualquier ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="56b97-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="56b97-112">Los miembros de un espacio de nombres especificado con `-imports` están disponibles para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="56b97-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="56b97-113">Use la [instrucción Imports (espacio de nombres y tipo de .net)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para usar un espacio de nombres en un solo archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="56b97-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="56b97-114">Para establecer las importaciones en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="56b97-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="56b97-115">1. tener un proyecto seleccionado en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="56b97-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="56b97-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="56b97-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="56b97-117">2. Haga clic en la pestaña **referencias** .</span><span class="sxs-lookup"><span data-stu-id="56b97-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="56b97-118">3. Escriba el nombre del espacio de nombres en el cuadro situado junto al botón **Agregar importación de usuario** .</span><span class="sxs-lookup"><span data-stu-id="56b97-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="56b97-119">4. Haga clic en el botón **Agregar importación de usuario** .</span><span class="sxs-lookup"><span data-stu-id="56b97-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56b97-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56b97-120">Example</span></span>  
 <span data-ttu-id="56b97-121">El siguiente código se compila cuando se especifica `-imports:system.globalization`.</span><span class="sxs-lookup"><span data-stu-id="56b97-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="56b97-122">Sin él, la compilación correcta requiere que una instrucción `Imports System.Globalization` esté incluida al principio del archivo de código fuente, o que la propiedad esté completa como `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="56b97-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="56b97-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="56b97-123">See also</span></span>

- [<span data-ttu-id="56b97-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56b97-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="56b97-125">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="56b97-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="56b97-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="56b97-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
