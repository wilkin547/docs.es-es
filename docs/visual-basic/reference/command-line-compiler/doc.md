---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 57a81983278c26090c62995f4da55c5cbfd66047
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408678"
---
# <a name="-doc"></a><span data-ttu-id="2cd52-102">-doc</span><span class="sxs-lookup"><span data-stu-id="2cd52-102">-doc</span></span>
<span data-ttu-id="2cd52-103">Procesa los comentarios de documentación generando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2cd52-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cd52-104">Syntax</span></span>  
  
```console  
-doc[+ | -]  
```

<span data-ttu-id="2cd52-105">o</span><span class="sxs-lookup"><span data-stu-id="2cd52-105">or</span></span>  

```console
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cd52-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2cd52-106">Arguments</span></span>  
  
|<span data-ttu-id="2cd52-107">Término</span><span class="sxs-lookup"><span data-stu-id="2cd52-107">Term</span></span>|<span data-ttu-id="2cd52-108">Definición</span><span class="sxs-lookup"><span data-stu-id="2cd52-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2cd52-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2cd52-109">`+` &#124; `-`</span></span>|<span data-ttu-id="2cd52-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2cd52-110">Optional.</span></span> <span data-ttu-id="2cd52-111">Si se especifica + o solo `-doc`, el compilador genera información de documentación y la coloca en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2cd52-111">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="2cd52-112">Especificar `-` es el equivalente a no especificar `-doc`, lo que causa que no se cree ninguna información de documentación.</span><span class="sxs-lookup"><span data-stu-id="2cd52-112">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="2cd52-113">Es necesario si se usa `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="2cd52-113">Required if `-doc:` is used.</span></span> <span data-ttu-id="2cd52-114">Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="2cd52-114">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="2cd52-115">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="2cd52-115">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cd52-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2cd52-116">Remarks</span></span>  
 <span data-ttu-id="2cd52-117">La opción `-doc` controla si el compilador genera un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="2cd52-117">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="2cd52-118">Si usa la sintaxis `-doc:file`, el parámetro `file` especifica el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2cd52-118">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="2cd52-119">Si usa `-doc` o `-doc+`, el compilador toma el nombre del archivo XML desde el archivo ejecutable o la biblioteca que el compilador va a crear.</span><span class="sxs-lookup"><span data-stu-id="2cd52-119">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="2cd52-120">Si usa `-doc-` o no especifica la opción `-doc`, el compilador no crea un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2cd52-120">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="2cd52-121">En los archivos de código fuente, los comentarios de documentación pueden preceder a las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="2cd52-121">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="2cd52-122">Tipos definidos por el usuario como una [clase](../../language-reference/statements/class-statement.md) o una [interfaz](../../language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2cd52-122">User-defined types, such as a [class](../../language-reference/statements/class-statement.md) or [interface](../../language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="2cd52-123">Miembros, como un campo, un [evento](../../language-reference/statements/event-statement.md), una [propiedad](../../language-reference/statements/property-statement.md), una [función](../../language-reference/statements/function-statement.md) o una [subrutina](../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2cd52-123">Members, such as a field, [event](../../language-reference/statements/event-statement.md), [property](../../language-reference/statements/property-statement.md), [function](../../language-reference/statements/function-statement.md), or [subroutine](../../language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="2cd52-124">Para usar el archivo XML generado con la característica [IntelliSense](/visualstudio/ide/using-intellisense) de Visual Studio, deje que el nombre del archivo XML sea igual que el del ensamblado que quiere admitir.</span><span class="sxs-lookup"><span data-stu-id="2cd52-124">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="2cd52-125">Asegúrese de que el archivo XML se encuentra en el mismo directorio que el ensamblado, para que cuando se haga referencia al ensamblado en el proyecto de Visual Studio, también se encuentre el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="2cd52-125">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="2cd52-126">Los archivos de documentación XML no son necesarios para que IntelliSense funcione para el código dentro de un proyecto o de los proyectos a los que el proyecto hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2cd52-126">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="2cd52-127">A menos que compile con `-target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="2cd52-127">Unless you compile with `-target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="2cd52-128">Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="2cd52-128">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="2cd52-129">Vea [Etiquetas XML para comentarios](../../language-reference/xmldoc/index.md) para conocer las maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="2cd52-129">See [XML Comment Tags](../../language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="2cd52-130">Para definir -doc en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2cd52-130">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2cd52-131">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2cd52-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2cd52-132">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2cd52-132">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2cd52-133">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="2cd52-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2cd52-134">3.  Establezca el valor en el cuadro **Generar archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="2cd52-134">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cd52-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd52-135">Example</span></span>  
 <span data-ttu-id="2cd52-136">Vea [Documentar el código con XML (Visual Basic)](../../programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2cd52-136">See [Documenting Your Code with XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd52-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cd52-137">See also</span></span>

- [<span data-ttu-id="2cd52-138">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2cd52-138">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2cd52-139">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="2cd52-139">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
