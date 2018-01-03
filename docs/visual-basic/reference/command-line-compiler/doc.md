---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1f9d4f584f217e6996a499614b97f184b28664f8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="doc"></a><span data-ttu-id="63ed7-102">/doc</span><span class="sxs-lookup"><span data-stu-id="63ed7-102">/doc</span></span>
<span data-ttu-id="63ed7-103">Procesa los comentarios de documentación generando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="63ed7-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ed7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ed7-104">Syntax</span></span>  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="63ed7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="63ed7-105">Arguments</span></span>  
  
|<span data-ttu-id="63ed7-106">Término</span><span class="sxs-lookup"><span data-stu-id="63ed7-106">Term</span></span>|<span data-ttu-id="63ed7-107">Definición</span><span class="sxs-lookup"><span data-stu-id="63ed7-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="63ed7-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="63ed7-108">`+` &#124; `-`</span></span>|<span data-ttu-id="63ed7-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="63ed7-109">Optional.</span></span> <span data-ttu-id="63ed7-110">Especificar +, o simplemente `/doc`, hace que el compilador genera información de documentación y lo coloca en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="63ed7-110">Specifying +, or just `/doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="63ed7-111">Especificar `-` equivale a no especificar `/doc`, haciendo que se generará ninguna información de documentación.</span><span class="sxs-lookup"><span data-stu-id="63ed7-111">Specifying `-` is the equivalent of not specifying `/doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="63ed7-112">Es necesario si se usa `/doc:`.</span><span class="sxs-lookup"><span data-stu-id="63ed7-112">Required if `/doc:` is used.</span></span> <span data-ttu-id="63ed7-113">Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="63ed7-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="63ed7-114">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="63ed7-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63ed7-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63ed7-115">Remarks</span></span>  
 <span data-ttu-id="63ed7-116">El `/doc` opción controla si el compilador genera un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="63ed7-116">The `/doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="63ed7-117">Si usas el `/doc:``file` sintaxis, la `file` parámetro especifica el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="63ed7-117">If you use the `/doc:``file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="63ed7-118">Si usa `/doc` o `/doc+`, el compilador usa el nombre del archivo XML desde el archivo ejecutable o biblioteca que está creando el compilador.</span><span class="sxs-lookup"><span data-stu-id="63ed7-118">If you use `/doc` or `/doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="63ed7-119">Si usa `/doc-` o no especifique el `/doc` opción, el compilador no crea un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="63ed7-119">If you use `/doc-` or do not specify the `/doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="63ed7-120">En los archivos de código fuente, los comentarios de documentación pueden preceder a las definiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="63ed7-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="63ed7-121">Definido por el usuario tipos, como un [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [(interfaz)](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="63ed7-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="63ed7-122">Miembros, como un campo, [eventos](../../../visual-basic/language-reference/statements/event-statement.md), [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), [función](../../../visual-basic/language-reference/statements/function-statement.md), o [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="63ed7-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="63ed7-123">Para usar el archivo XML generado con el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) de características, supongamos que el nombre de archivo del archivo XML es el mismo que el ensamblado que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="63ed7-123">To use the generated XML file with the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="63ed7-124">Asegúrese de que el archivo XML está en el mismo directorio que el ensamblado para que cuando se hace referencia el ensamblado en el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] proyecto, se encuentra el archivo .xml así.</span><span class="sxs-lookup"><span data-stu-id="63ed7-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="63ed7-125">Archivos de documentación XML no son necesarios para que IntelliSense funcione para un código dentro de un proyecto o dentro de los proyectos que se hace referencia a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="63ed7-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="63ed7-126">A menos que se compila con `/target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="63ed7-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="63ed7-127">Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="63ed7-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="63ed7-128">Vea [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="63ed7-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="63ed7-129">Para establecer a /doc en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="63ed7-129">To set /doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="63ed7-130">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="63ed7-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="63ed7-131">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="63ed7-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="63ed7-132">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="63ed7-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="63ed7-133">3.  Establezca el valor el **archivo de documentación XML generar** cuadro.</span><span class="sxs-lookup"><span data-stu-id="63ed7-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="63ed7-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63ed7-134">Example</span></span>  
 <span data-ttu-id="63ed7-135">Vea [documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="63ed7-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ed7-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ed7-136">See Also</span></span>  
 [<span data-ttu-id="63ed7-137">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63ed7-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="63ed7-138">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="63ed7-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
