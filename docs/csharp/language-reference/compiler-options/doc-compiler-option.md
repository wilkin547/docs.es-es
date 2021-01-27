---
description: -doc (Opciones del compilador de C#)
title: -doc (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: e55b86e5b028fb871f309d80217477cfd164c106
ms.sourcegitcommit: f0eb7eeedf3ceec726499fa678786d03083214ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "98629259"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="0539d-103">-doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0539d-103">-doc (C# Compiler Options)</span></span>

<span data-ttu-id="0539d-104">La opción **-doc** permite insertar comentarios de documentación en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="0539d-104">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0539d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0539d-105">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="0539d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0539d-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="0539d-107">Archivo de salida para XML, que se llena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="0539d-107">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0539d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0539d-108">Remarks</span></span>  

 <span data-ttu-id="0539d-109">En los archivos de código fuente, es posible procesar y agregar al archivo XML los comentarios de documentación que preceden a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0539d-109">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
- <span data-ttu-id="0539d-110">Tipos definidos por el usuario como una [clase](../keywords/class.md), un [delegado](../builtin-types/reference-types.md#the-delegate-type) o una [interfaz](../keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="0539d-110">Such user-defined types as a [class](../keywords/class.md), [delegate](../builtin-types/reference-types.md#the-delegate-type), or [interface](../keywords/interface.md)</span></span>  
  
- <span data-ttu-id="0539d-111">Miembros como un campo, un [evento](../keywords/event.md), una [propiedad](../../programming-guide/classes-and-structs/using-properties.md) o un método</span><span class="sxs-lookup"><span data-stu-id="0539d-111">Such members as a field, [event](../keywords/event.md), [property](../../programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="0539d-112">El archivo de código fuente que contiene Main es la primera salida del XML.</span><span class="sxs-lookup"><span data-stu-id="0539d-112">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="0539d-113">Para usar el archivo .xml generado con la función [IntelliSense](/visualstudio/ide/using-intellisense), deje que el nombre del archivo .xml sea igual que el del ensamblado que quiere admitir y, después, asegúrese de que el archivo .xml se encuentra en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0539d-113">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="0539d-114">De este modo, cuando se hace referencia al ensamblado en el proyecto de Visual Studio, también se encuentra el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="0539d-114">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="0539d-115">Vea [Proporcionar comentarios del código](/visualstudio/ide/reference/generate-xml-documentation-comments) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0539d-115">See [Supplying Code Comments](/visualstudio/ide/reference/generate-xml-documentation-comments) and for more information.</span></span>  
  
 <span data-ttu-id="0539d-116">A menos que realice la compilación con [-target:module](./target-module-compiler-option.md), `file` contendrá etiquetas \<assembly>\</assembly> que especifican el nombre del archivo que incluye el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="0539d-116">Unless you compile with [-target:module](./target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0539d-117">La opción -doc se aplica a todos los archivos de entrada o, si se establece en la configuración del proyecto, a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0539d-117">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="0539d-118">Para deshabilitar las advertencias relacionadas con los comentarios de documentación para un archivo específico o una sección de código, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="0539d-118">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="0539d-119">Vea [Etiquetas recomendadas para comentarios de documentación ](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) para conocer las maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="0539d-119">See [Recommended Tags for Documentation Comments](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-2019-development-environment"></a><span data-ttu-id="0539d-120">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0539d-120">To set this compiler option in the Visual Studio 2019 development environment</span></span>  

1. <span data-ttu-id="0539d-121">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0539d-121">Open the project's **Properties** page.</span></span>  
2. <span data-ttu-id="0539d-122">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="0539d-122">Click the **Build** tab.</span></span>
3. <span data-ttu-id="0539d-123">Modifique la propiedad **Archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="0539d-123">Modify the **XML documentation file** property.</span></span>
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-for-mac-development-environment"></a><span data-ttu-id="0539d-124">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="0539d-124">To set this compiler option in the Visual Studio for Mac development environment</span></span>  
  
1. <span data-ttu-id="0539d-125">Abra la página **Opciones** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0539d-125">Open the project's **Options** page.</span></span>
2. <span data-ttu-id="0539d-126">Seleccione la pestaña **Compilador**.</span><span class="sxs-lookup"><span data-stu-id="0539d-126">Select the **Compiler** tab.</span></span>
3. <span data-ttu-id="0539d-127">Seleccione **Generar documentación XML** y escriba el nombre del archivo en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="0539d-127">Select **Generate xml documentation** and enter the file name in the text box.</span></span>

<span data-ttu-id="0539d-128">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="0539d-128">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0539d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0539d-129">See also</span></span>

- [<span data-ttu-id="0539d-130">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="0539d-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="0539d-131">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="0539d-131">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
