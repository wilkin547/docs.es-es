---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082062"
---
# <a name="-doc"></a><span data-ttu-id="c9234-102">-doc</span><span class="sxs-lookup"><span data-stu-id="c9234-102">-doc</span></span>
<span data-ttu-id="c9234-103">Procesa los comentarios de documentación generando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c9234-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9234-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9234-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9234-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c9234-105">Arguments</span></span>  
  
|<span data-ttu-id="c9234-106">Término</span><span class="sxs-lookup"><span data-stu-id="c9234-106">Term</span></span>|<span data-ttu-id="c9234-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="c9234-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c9234-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c9234-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c9234-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c9234-109">Optional.</span></span> <span data-ttu-id="c9234-110">Especificar +, o simplemente `-doc`, hace que el compilador genere información de documentación y colocarla en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c9234-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="c9234-111">Especificar `-` equivale a no especificar `-doc`, lo que provoca ninguna información de documentación se puede crear.</span><span class="sxs-lookup"><span data-stu-id="c9234-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="c9234-112">Es necesario si se usa `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="c9234-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="c9234-113">Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c9234-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="c9234-114">Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="c9234-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9234-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9234-115">Remarks</span></span>  
 <span data-ttu-id="c9234-116">El `-doc` opción controla si el compilador genera un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="c9234-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="c9234-117">Si usas el `-doc:file` sintaxis, el `file` parámetro especifica el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c9234-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="c9234-118">Si usas `-doc` o `-doc+`, el compilador toma el nombre del archivo XML desde el archivo ejecutable o biblioteca que está creando el compilador.</span><span class="sxs-lookup"><span data-stu-id="c9234-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="c9234-119">Si usas `-doc-` o no especifique el `-doc` opción, el compilador no crea un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c9234-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="c9234-120">En los archivos de código fuente, los comentarios de documentación pueden preceder a las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="c9234-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="c9234-121">Definido por el usuario tipos, como un [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaz](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c9234-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="c9234-122">Los miembros, como un campo, [eventos](../../../visual-basic/language-reference/statements/event-statement.md), [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), [función](../../../visual-basic/language-reference/statements/function-statement.md), o [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c9234-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="c9234-123">Para usar el archivo XML generado con Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) de características, deje que el nombre de archivo del archivo XML a ser el mismo que el ensamblado que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="c9234-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="c9234-124">Asegúrese de que el archivo XML está en el mismo directorio que el ensamblado para que cuando se hace referencia al ensamblado en el proyecto de Visual Studio, también se encuentra el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="c9234-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="c9234-125">Archivos de documentación XML no son necesarios para que IntelliSense funcione para el código dentro de un proyecto o dentro de los proyectos que se hace referencia un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c9234-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="c9234-126">A menos que compile con `/target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="c9234-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="c9234-127">Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c9234-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="c9234-128">Consulte [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/index.md) para formas de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="c9234-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="c9234-129">Para establecer - doc en Visual Studio el entorno de desarrollo integrado</span><span class="sxs-lookup"><span data-stu-id="c9234-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c9234-130">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c9234-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c9234-131">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c9234-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c9234-132">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="c9234-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c9234-133">3.  Establezca el valor el **generar archivo de documentación** cuadro.</span><span class="sxs-lookup"><span data-stu-id="c9234-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c9234-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9234-134">Example</span></span>  
 <span data-ttu-id="c9234-135">Consulte [documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9234-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9234-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9234-136">See Also</span></span>  
 [<span data-ttu-id="c9234-137">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9234-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c9234-138">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="c9234-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
