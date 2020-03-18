---
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
ms.openlocfilehash: 01ea71f3de9e30abe25184e38a59f3707b54bd5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73422971"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="c400e-102">-doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="c400e-102">-doc (C# Compiler Options)</span></span>
<span data-ttu-id="c400e-103">La opción **-doc** permite insertar comentarios de documentación en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c400e-103">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c400e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c400e-104">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="c400e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c400e-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="c400e-106">Archivo de salida para XML, que se llena con los comentarios de los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c400e-106">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c400e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c400e-107">Remarks</span></span>  
 <span data-ttu-id="c400e-108">En los archivos de código fuente, es posible procesar y agregar al archivo XML los comentarios de documentación que preceden a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c400e-108">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
- <span data-ttu-id="c400e-109">Tipos definidos por el usuario como una [clase](../keywords/class.md), un [delegado](../builtin-types/reference-types.md#the-delegate-type) o una [interfaz](../keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="c400e-109">Such user-defined types as a [class](../keywords/class.md), [delegate](../builtin-types/reference-types.md#the-delegate-type), or [interface](../keywords/interface.md)</span></span>  
  
- <span data-ttu-id="c400e-110">Miembros como un campo, un [evento](../keywords/event.md), una [propiedad](../../programming-guide/classes-and-structs/using-properties.md) o un método</span><span class="sxs-lookup"><span data-stu-id="c400e-110">Such members as a field, [event](../keywords/event.md), [property](../../programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="c400e-111">El archivo de código fuente que contiene Main es la primera salida del XML.</span><span class="sxs-lookup"><span data-stu-id="c400e-111">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="c400e-112">Para usar el archivo .xml generado con la función [IntelliSense](/visualstudio/ide/using-intellisense), deje que el nombre del archivo .xml sea igual que el del ensamblado que quiere admitir y, después, asegúrese de que el archivo .xml se encuentra en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c400e-112">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="c400e-113">De este modo, cuando se hace referencia al ensamblado en el proyecto de Visual Studio, también se encuentra el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="c400e-113">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="c400e-114">Vea [Proporcionar comentarios del código](/visualstudio/ide/reference/generate-xml-documentation-comments) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c400e-114">See [Supplying Code Comments](/visualstudio/ide/reference/generate-xml-documentation-comments) and for more information.</span></span>  
  
 <span data-ttu-id="c400e-115">A menos que compile con [-target:module](./target-module-compiler-option.md), `file` contendrá etiquetas \<assembly>\</assembly> que especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c400e-115">Unless you compile with [-target:module](./target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c400e-116">La opción -doc se aplica a todos los archivos de entrada o, si se establece en la configuración del proyecto, a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c400e-116">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="c400e-117">Para deshabilitar las advertencias relacionadas con los comentarios de documentación para un archivo específico o una sección de código, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="c400e-117">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="c400e-118">Vea [Etiquetas recomendadas para comentarios de documentación ](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) para conocer las maneras de generar documentación a partir de comentarios en el código.</span><span class="sxs-lookup"><span data-stu-id="c400e-118">See [Recommended Tags for Documentation Comments](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c400e-119">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c400e-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="c400e-120">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c400e-120">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="c400e-121">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="c400e-121">Click the **Build** tab.</span></span>  
  
3. <span data-ttu-id="c400e-122">Modifique la propiedad **Archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="c400e-122">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="c400e-123">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="c400e-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c400e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c400e-124">See also</span></span>

- [<span data-ttu-id="c400e-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c400e-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c400e-126">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="c400e-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
