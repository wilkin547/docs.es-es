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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716646"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="2ff8b-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ff8b-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="2ff8b-103">Importa espacios de nombres desde un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ff8b-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ff8b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2ff8b-105">Arguments</span></span>  
  
|<span data-ttu-id="2ff8b-106">Término</span><span class="sxs-lookup"><span data-stu-id="2ff8b-106">Term</span></span>|<span data-ttu-id="2ff8b-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2ff8b-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="2ff8b-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-108">Required.</span></span> <span data-ttu-id="2ff8b-109">Lista delimitada por comas de los espacios de nombres que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ff8b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ff8b-110">Remarks</span></span>  
 <span data-ttu-id="2ff8b-111">La opción `-imports` importa cualquier espacio de nombres definido en el conjunto actual de archivos de código fuente o desde cualquier ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="2ff8b-112">Los miembros de un espacio de nombres especificado con `-imports` están disponibles para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="2ff8b-113">Utilice la [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para usar un espacio de nombres en un solo archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="2ff8b-114">Para establecer -imports en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ff8b-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2ff8b-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2ff8b-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2ff8b-117">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="2ff8b-118">3.  Escriba el nombre del espacio de nombres en el cuadro situado junto al botón **Agregar importación del usuario**.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="2ff8b-119">4.  Haga clic en el botón **Agregar importación del usuario**.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ff8b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ff8b-120">Example</span></span>  
 <span data-ttu-id="2ff8b-121">El código siguiente se compila cuando se especifica `-imports:system.globalization`.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="2ff8b-122">Si no se especifica, la compilación correcta requiere que se incluya una instrucción `Imports System.Globalization` al principio del archivo de código fuente, o bien que la propiedad se complete como `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="2ff8b-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="2ff8b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ff8b-123">See also</span></span>

- [<span data-ttu-id="2ff8b-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ff8b-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2ff8b-125">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="2ff8b-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="2ff8b-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ff8b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
