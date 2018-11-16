---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: d786a77a0f787515ce1ab2ca61cbc1251aa14563
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "50192465"
---
# <a name="-doc"></a><span data-ttu-id="2a218-102">-doc</span><span class="sxs-lookup"><span data-stu-id="2a218-102">-doc</span></span>
<span data-ttu-id="2a218-103">Procesa los comentarios de documentación generando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2a218-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a218-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a218-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a218-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2a218-105">Arguments</span></span>  
  
|<span data-ttu-id="2a218-106">Término</span><span class="sxs-lookup"><span data-stu-id="2a218-106">Term</span></span>|<span data-ttu-id="2a218-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="2a218-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2a218-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2a218-108">`+` &#124; `-`</span></span>|<span data-ttu-id="2a218-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2a218-109">Optional.</span></span> <span data-ttu-id="2a218-110">Si se especifica + o solo `-doc`, el compilador genera información de documentación y la coloca en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2a218-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="2a218-111">Especificar `-` es el equivalente a no especificar `-doc`, lo que causa que no se cree ninguna información de documentación.</span><span class="sxs-lookup"><span data-stu-id="2a218-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="2a218-112">Es necesario si se usa `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="2a218-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="2a218-113">Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="2a218-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="2a218-114">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="2a218-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a218-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a218-115">Remarks</span></span>  
 <span data-ttu-id="2a218-116">La opción `-doc` controla si el compilador genera un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="2a218-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="2a218-117">Si usa la sintaxis `-doc:file`, el parámetro `file` especifica el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2a218-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="2a218-118">Si usa `-doc` o `-doc+`, el compilador toma el nombre del archivo XML desde el archivo ejecutable o la biblioteca que el compilador va a crear.</span><span class="sxs-lookup"><span data-stu-id="2a218-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="2a218-119">Si usa `-doc-` o no especifica la opción `-doc`, el compilador no crea un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2a218-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="2a218-120">En los archivos de código fuente, los comentarios de documentación pueden preceder a las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="2a218-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="2a218-121">Tipos definidos por el usuario como una [clase](../../../visual-basic/language-reference/statements/class-statement.md) o una [interfaz](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2a218-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="2a218-122">Miembros, como un campo, un [evento](../../../visual-basic/language-reference/statements/event-statement.md), una [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), una [función](../../../visual-basic/language-reference/statements/function-statement.md) o una [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2a218-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="2a218-123">Para usar el archivo XML generado con la característica [IntelliSense](/visualstudio/ide/using-intellisense) de Visual Studio, deje que el nombre del archivo XML sea igual que el del ensamblado que quiere admitir.</span><span class="sxs-lookup"><span data-stu-id="2a218-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="2a218-124">Asegúrese de que el archivo XML se encuentra en el mismo directorio que el ensamblado, para que cuando se haga referencia al ensamblado en el proyecto de Visual Studio, también se encuentre el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="2a218-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="2a218-125">Los archivos de documentación XML no son necesarios para que IntelliSense funcione para el código dentro de un proyecto o de los proyectos a los que el proyecto hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2a218-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="2a218-126">A menos que compile con `/target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="2a218-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="2a218-127">Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="2a218-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="2a218-128">Vea [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md) para conocer las maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="2a218-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="2a218-129">Para definir -doc en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a218-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2a218-130">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2a218-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2a218-131">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2a218-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2a218-132">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="2a218-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2a218-133">3.  Establezca el valor en el cuadro **Generar archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="2a218-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a218-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a218-134">Example</span></span>  
 <span data-ttu-id="2a218-135">Vea [Documentar el código con XML (Visual Basic)](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2a218-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a218-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a218-136">See Also</span></span>  
 [<span data-ttu-id="2a218-137">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a218-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2a218-138">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="2a218-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
