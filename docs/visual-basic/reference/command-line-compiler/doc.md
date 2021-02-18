---
description: Más información sobre -doc
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: da1ff6ad133dd2f46484b61ff73e1c6159eae557
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461429"
---
# <a name="-doc"></a><span data-ttu-id="73aa6-103">-doc</span><span class="sxs-lookup"><span data-stu-id="73aa6-103">-doc</span></span>

<span data-ttu-id="73aa6-104">Procesa los comentarios de documentación generando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="73aa6-104">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73aa6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73aa6-105">Syntax</span></span>  
  
```console  
-doc[+ | -]  
```

<span data-ttu-id="73aa6-106">o</span><span class="sxs-lookup"><span data-stu-id="73aa6-106">or</span></span>  

```console
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="73aa6-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73aa6-107">Arguments</span></span>  
  
|<span data-ttu-id="73aa6-108">Término</span><span class="sxs-lookup"><span data-stu-id="73aa6-108">Term</span></span>|<span data-ttu-id="73aa6-109">Definición</span><span class="sxs-lookup"><span data-stu-id="73aa6-109">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="73aa6-110">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="73aa6-110">`+` &#124; `-`</span></span>|<span data-ttu-id="73aa6-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73aa6-111">Optional.</span></span> <span data-ttu-id="73aa6-112">Si se especifica + o solo `-doc`, el compilador genera información de documentación y la coloca en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="73aa6-112">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="73aa6-113">Especificar `-` es el equivalente a no especificar `-doc`, lo que causa que no se cree ninguna información de documentación.</span><span class="sxs-lookup"><span data-stu-id="73aa6-113">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="73aa6-114">Es necesario si se usa `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="73aa6-114">Required if `-doc:` is used.</span></span> <span data-ttu-id="73aa6-115">Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="73aa6-115">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="73aa6-116">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="73aa6-116">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73aa6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73aa6-117">Remarks</span></span>  

 <span data-ttu-id="73aa6-118">La opción `-doc` controla si el compilador genera un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="73aa6-118">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="73aa6-119">Si usa la sintaxis `-doc:file`, el parámetro `file` especifica el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="73aa6-119">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="73aa6-120">Si usa `-doc` o `-doc+`, el compilador toma el nombre del archivo XML desde el archivo ejecutable o la biblioteca que el compilador va a crear.</span><span class="sxs-lookup"><span data-stu-id="73aa6-120">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="73aa6-121">Si usa `-doc-` o no especifica la opción `-doc`, el compilador no crea un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="73aa6-121">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="73aa6-122">En los archivos de código fuente, los comentarios de documentación pueden preceder a las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="73aa6-122">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="73aa6-123">Tipos definidos por el usuario como una [clase](../../language-reference/statements/class-statement.md) o una [interfaz](../../language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="73aa6-123">User-defined types, such as a [class](../../language-reference/statements/class-statement.md) or [interface](../../language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="73aa6-124">Miembros, como un campo, un [evento](../../language-reference/statements/event-statement.md), una [propiedad](../../language-reference/statements/property-statement.md), una [función](../../language-reference/statements/function-statement.md) o una [subrutina](../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73aa6-124">Members, such as a field, [event](../../language-reference/statements/event-statement.md), [property](../../language-reference/statements/property-statement.md), [function](../../language-reference/statements/function-statement.md), or [subroutine](../../language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="73aa6-125">Para usar el archivo XML generado con la característica [IntelliSense](/visualstudio/ide/using-intellisense) de Visual Studio, deje que el nombre del archivo XML sea igual que el del ensamblado que quiere admitir.</span><span class="sxs-lookup"><span data-stu-id="73aa6-125">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="73aa6-126">Asegúrese de que el archivo XML se encuentra en el mismo directorio que el ensamblado, para que cuando se haga referencia al ensamblado en el proyecto de Visual Studio, también se encuentre el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="73aa6-126">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="73aa6-127">Los archivos de documentación XML no son necesarios para que IntelliSense funcione para el código dentro de un proyecto o de los proyectos a los que el proyecto hace referencia.</span><span class="sxs-lookup"><span data-stu-id="73aa6-127">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="73aa6-128">A menos que compile con `-target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="73aa6-128">Unless you compile with `-target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="73aa6-129">Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="73aa6-129">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="73aa6-130">Vea [Etiquetas XML para comentarios](../../language-reference/xmldoc/index.md) para conocer las maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="73aa6-130">See [XML Comment Tags](../../language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="73aa6-131">Para definir -doc en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73aa6-131">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="73aa6-132">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="73aa6-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73aa6-133">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="73aa6-133">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="73aa6-134">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="73aa6-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="73aa6-135">3.  Establezca el valor en el cuadro **Generar archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="73aa6-135">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73aa6-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73aa6-136">Example</span></span>  

 <span data-ttu-id="73aa6-137">Vea [Documentar el código con XML (Visual Basic)](../../programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="73aa6-137">See [Documenting Your Code with XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73aa6-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="73aa6-138">See also</span></span>

- [<span data-ttu-id="73aa6-139">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73aa6-139">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="73aa6-140">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="73aa6-140">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
