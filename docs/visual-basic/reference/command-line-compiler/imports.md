---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: ce59cbc834d84d19ec7f8d6d3d32b545c537173c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364676"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="95353-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95353-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="95353-103">Importa los espacios de nombres desde un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="95353-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95353-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95353-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="95353-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95353-105">Arguments</span></span>  
  
|<span data-ttu-id="95353-106">Término</span><span class="sxs-lookup"><span data-stu-id="95353-106">Term</span></span>|<span data-ttu-id="95353-107">Definición</span><span class="sxs-lookup"><span data-stu-id="95353-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="95353-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="95353-108">Required.</span></span> <span data-ttu-id="95353-109">Lista delimitada por comas de los espacios de nombres que desea importar.</span><span class="sxs-lookup"><span data-stu-id="95353-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95353-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95353-110">Remarks</span></span>  
 <span data-ttu-id="95353-111">El `-imports` opción importa cualquier espacio de nombres definido dentro del conjunto actual de archivos de origen o de cualquier ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="95353-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="95353-112">Los miembros de un espacio de nombres especificado con `-imports` están disponibles para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="95353-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="95353-113">Utilice la [instrucción Imports (tipo y Namespace. NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para usar un espacio de nombres en un archivo de código fuente único.</span><span class="sxs-lookup"><span data-stu-id="95353-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="95353-114">Para establecer/importa en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95353-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="95353-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="95353-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="95353-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="95353-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="95353-117">2.  Haga clic en la pestaña **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="95353-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="95353-118">3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="95353-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="95353-119">4.  Haga clic en el **Agregar importación del usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="95353-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95353-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95353-120">Example</span></span>  
 <span data-ttu-id="95353-121">El siguiente código compila cuando `/imports:system.globalization` se especifica.</span><span class="sxs-lookup"><span data-stu-id="95353-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="95353-122">Sin él, la compilación correcta requiere que un `Imports System.Globalization` incluirse instrucción al principio del archivo de código fuente, o la propiedad totalmente calificarse como `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="95353-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="95353-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="95353-123">See also</span></span>
- [<span data-ttu-id="95353-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95353-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="95353-125">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="95353-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="95353-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="95353-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
