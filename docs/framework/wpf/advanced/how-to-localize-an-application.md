---
title: Localizar una aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209687"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="58956-102">Cómo: localizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="58956-102">How to: Localize an application</span></span>

<span data-ttu-id="58956-103">En este tutorial se explica cómo crear una aplicación localizada mediante la herramienta LocBaml.</span><span class="sxs-lookup"><span data-stu-id="58956-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58956-104">La herramienta LocBaml no es una aplicación lista para producción.</span><span class="sxs-lookup"><span data-stu-id="58956-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="58956-105">Se presenta como un ejemplo que usa algunas de las API de localización y muestra cómo se podría escribir una herramienta de localización.</span><span class="sxs-lookup"><span data-stu-id="58956-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="58956-106">Información general</span><span class="sxs-lookup"><span data-stu-id="58956-106">Overview</span></span>

<span data-ttu-id="58956-107">En este artículo se ofrece un enfoque paso a paso para localizar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="58956-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="58956-108">En primer lugar, prepare la aplicación para que se pueda extraer el texto que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="58956-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="58956-109">Una vez traducido el texto, combine el texto traducido en una nueva copia de la aplicación original.</span><span class="sxs-lookup"><span data-stu-id="58956-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="58956-110">Creación de una aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="58956-110">Create a sample application</span></span>

<span data-ttu-id="58956-111">En este paso, va a preparar la aplicación para la localización.</span><span class="sxs-lookup"><span data-stu-id="58956-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="58956-112">En los ejemplos de Windows Presentation Foundation (WPF), se proporciona un ejemplo de HelloApp que se usará para los ejemplos de código de este debate.</span><span class="sxs-lookup"><span data-stu-id="58956-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="58956-113">Si desea usar este ejemplo, descargue los archivos lenguaje XAML (XAML) del ejemplo de la [herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="58956-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="58956-114">Desarrolle su aplicación hasta el punto donde desea iniciar la localización.</span><span class="sxs-lookup"><span data-stu-id="58956-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="58956-115">Especifique el lenguaje de desarrollo en el archivo de proyecto para que MSBuild genere un ensamblado principal y un ensamblado satélite (un archivo con la extensión. Resources. dll) para que contenga los recursos de idioma neutro.</span><span class="sxs-lookup"><span data-stu-id="58956-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="58956-116">El archivo de proyecto en el ejemplo HelloApp es HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="58956-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="58956-117">En ese archivo, encontrará el lenguaje de desarrollo que se identifica como sigue:</span><span class="sxs-lookup"><span data-stu-id="58956-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="58956-118">Agregue UID a los archivos XAML.</span><span class="sxs-lookup"><span data-stu-id="58956-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="58956-119">Los UID se usan para realizar un seguimiento de los cambios en los archivos y para identificar los elementos que se deben traducir.</span><span class="sxs-lookup"><span data-stu-id="58956-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="58956-120">Para agregar UID a los archivos, ejecute `updateuid` en el archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="58956-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="58956-121">Para comprobar que no faltan UID ni están duplicados, ejecute `checkuid` :</span><span class="sxs-lookup"><span data-stu-id="58956-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="58956-122">Después de ejecutar `updateuid` , los archivos deben contener UID.</span><span class="sxs-lookup"><span data-stu-id="58956-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="58956-123">Por ejemplo, en el archivo *Pane1. Xaml* de HelloApp, debería encontrar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="58956-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="58956-124">Crear el ensamblado satélite de recursos de idioma neutro</span><span class="sxs-lookup"><span data-stu-id="58956-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="58956-125">Después de configurar la aplicación para que genere un ensamblado satélite de recursos de idioma neutro, compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58956-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="58956-126">Esto genera el ensamblado de aplicación principal, así como el ensamblado satélite de recursos de idioma neutro que LocBaml necesita para la localización.</span><span class="sxs-lookup"><span data-stu-id="58956-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="58956-127">Para compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="58956-127">To build the application:</span></span>  
  
1. <span data-ttu-id="58956-128">Compile HelloApp para crear una biblioteca de vínculos dinámicos (DLL):</span><span class="sxs-lookup"><span data-stu-id="58956-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="58956-129">El ensamblado de aplicación principal que se acaba de crear, HelloApp. exe, se crea en la siguiente carpeta: *C:\HelloApp\Bin\Debug*</span><span class="sxs-lookup"><span data-stu-id="58956-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="58956-130">El ensamblado satélite de recursos de idioma neutro que se acaba de crear, HelloApp. Resources. dll, se crea en la siguiente carpeta: *C:\HelloApp\Bin\Debug\en-US*</span><span class="sxs-lookup"><span data-stu-id="58956-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="58956-131">Compilar la herramienta LocBaml</span><span class="sxs-lookup"><span data-stu-id="58956-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="58956-132">Todos los archivos necesarios para compilar LocBaml se encuentran en los ejemplos de WPF.</span><span class="sxs-lookup"><span data-stu-id="58956-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="58956-133">Descargue los archivos de C# del [ejemplo de la herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="58956-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="58956-134">Desde la línea de comandos, ejecute el archivo de proyecto (locbaml.csproj) para compilar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="58956-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="58956-135">Vaya al directorio *Bin\Release* para buscar el archivo ejecutable recién creado (LocBaml. exe).</span><span class="sxs-lookup"><span data-stu-id="58956-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="58956-136">Ejemplo: *C:\LocBaml\Bin\Release\locbaml.exe*</span><span class="sxs-lookup"><span data-stu-id="58956-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="58956-137">Las opciones que puede especificar al ejecutar LocBaml son las siguientes.</span><span class="sxs-lookup"><span data-stu-id="58956-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="58956-138">Opción</span><span class="sxs-lookup"><span data-stu-id="58956-138">Option</span></span> | <span data-ttu-id="58956-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="58956-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="58956-140">`parse` o `-p`</span><span class="sxs-lookup"><span data-stu-id="58956-140">`parse` or `-p`</span></span> | <span data-ttu-id="58956-141">Analiza los archivos BAML, Resources o DLL para generar un archivo. csv o. txt.</span><span class="sxs-lookup"><span data-stu-id="58956-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="58956-142">`generate` o `-g`</span><span class="sxs-lookup"><span data-stu-id="58956-142">`generate` or `-g`</span></span> | <span data-ttu-id="58956-143">Genera un archivo binario localizado mediante un archivo traducido.</span><span class="sxs-lookup"><span data-stu-id="58956-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="58956-144">`out`o `-o` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="58956-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="58956-145">Nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="58956-145">Output file name.</span></span> |
   | <span data-ttu-id="58956-146">`culture`o `-cul` {*Culture*]</span><span class="sxs-lookup"><span data-stu-id="58956-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="58956-147">Configuración regional de los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="58956-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="58956-148">`translation`o `-trans` {*Translation. csv*]</span><span class="sxs-lookup"><span data-stu-id="58956-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="58956-149">Archivo traducido o localizado.</span><span class="sxs-lookup"><span data-stu-id="58956-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="58956-150">`asmpath`o `-asmpath` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="58956-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="58956-151">Si el código XAML contiene controles personalizados, debe proporcionar `asmpath` al ensamblado del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="58956-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="58956-152"> no muestra un logotipo ni información de copyright.</span><span class="sxs-lookup"><span data-stu-id="58956-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="58956-153"> muestra información en modo detallado.</span><span class="sxs-lookup"><span data-stu-id="58956-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="58956-154">Si necesita una lista de las opciones cuando ejecute la herramienta, escriba `LocBaml.exe` y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="58956-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="58956-155">Usar LocBaml para analizar un archivo</span><span class="sxs-lookup"><span data-stu-id="58956-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="58956-156">Ahora que ya ha creado la herramienta LocBaml, está listo para usarla para analizar HelloApp.resources.dll y extraer el contenido de texto que se traducirá.</span><span class="sxs-lookup"><span data-stu-id="58956-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="58956-157">Copie LocBaml.exe en la carpeta bin\debug de la aplicación, que es donde se creó el ensamblado de aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="58956-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="58956-158">Para analizar el archivo de ensamblado satélite y almacenar la salida como un archivo .csv, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="58956-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="58956-159">Si el archivo de entrada, HelloApp.resources.dll, no está en el mismo directorio que LocBaml.exe, mueva uno de los archivos para que ambos archivos se encuentren en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="58956-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="58956-160">Cuando se ejecuta LocBaml para analizar los archivos, la salida se compone de siete campos delimitados por comas (archivos .csv) o tabuladores (archivos .txt).</span><span class="sxs-lookup"><span data-stu-id="58956-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="58956-161">A continuación se muestra el archivo .csv analizado para HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="58956-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="58956-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="58956-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="58956-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="58956-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="58956-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="58956-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="58956-165">Los siete campos son:</span><span class="sxs-lookup"><span data-stu-id="58956-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="58956-166">**Nombre BAML**.</span><span class="sxs-lookup"><span data-stu-id="58956-166">**BAML Name**.</span></span> <span data-ttu-id="58956-167">Es el nombre del recurso BAML con respecto al ensamblado satélite de lenguaje de origen.</span><span class="sxs-lookup"><span data-stu-id="58956-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="58956-168">**Clave de recurso**.</span><span class="sxs-lookup"><span data-stu-id="58956-168">**Resource Key**.</span></span> <span data-ttu-id="58956-169">Es el identificador de recursos localizado.</span><span class="sxs-lookup"><span data-stu-id="58956-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="58956-170">**Categoría**.</span><span class="sxs-lookup"><span data-stu-id="58956-170">**Category**.</span></span> <span data-ttu-id="58956-171">Tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="58956-171">The value type.</span></span> <span data-ttu-id="58956-172">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="58956-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="58956-173">**Legibilidad**.</span><span class="sxs-lookup"><span data-stu-id="58956-173">**Readability**.</span></span> <span data-ttu-id="58956-174">Indica si un localizador puede leer el valor.</span><span class="sxs-lookup"><span data-stu-id="58956-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="58956-175">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="58956-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="58956-176">**Modificabilidad**.</span><span class="sxs-lookup"><span data-stu-id="58956-176">**Modifiability**.</span></span> <span data-ttu-id="58956-177">Indica si un localizador puede modificar el valor.</span><span class="sxs-lookup"><span data-stu-id="58956-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="58956-178">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="58956-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="58956-179">**Comentarios**.</span><span class="sxs-lookup"><span data-stu-id="58956-179">**Comments**.</span></span> <span data-ttu-id="58956-180">Descripción adicional del valor para ayudar a determinar cómo se localiza.</span><span class="sxs-lookup"><span data-stu-id="58956-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="58956-181">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="58956-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="58956-182">**Valor**.</span><span class="sxs-lookup"><span data-stu-id="58956-182">**Value**.</span></span> <span data-ttu-id="58956-183">Es el valor de texto que se va a traducir a la referencia cultural deseada.</span><span class="sxs-lookup"><span data-stu-id="58956-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="58956-184">En la tabla siguiente se muestra la correspondencia entre estos campos y los valores delimitados del archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="58956-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="58956-185">Nombre de BAML</span><span class="sxs-lookup"><span data-stu-id="58956-185">BAML name</span></span>|<span data-ttu-id="58956-186">Clave del recurso</span><span class="sxs-lookup"><span data-stu-id="58956-186">Resource key</span></span>|<span data-ttu-id="58956-187">Category</span><span class="sxs-lookup"><span data-stu-id="58956-187">Category</span></span>|<span data-ttu-id="58956-188">Legibilidad</span><span class="sxs-lookup"><span data-stu-id="58956-188">Readability</span></span>|<span data-ttu-id="58956-189">Modificabilidad</span><span class="sxs-lookup"><span data-stu-id="58956-189">Modifiability</span></span>|<span data-ttu-id="58956-190">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58956-190">Comments</span></span>|<span data-ttu-id="58956-191">Valor</span><span class="sxs-lookup"><span data-stu-id="58956-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="58956-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="58956-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="58956-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="58956-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="58956-194">Ignore</span><span class="sxs-lookup"><span data-stu-id="58956-194">Ignore</span></span>|<span data-ttu-id="58956-195">FALSE</span><span class="sxs-lookup"><span data-stu-id="58956-195">FALSE</span></span>|<span data-ttu-id="58956-196">FALSE</span><span class="sxs-lookup"><span data-stu-id="58956-196">FALSE</span></span>||<span data-ttu-id="58956-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="58956-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="58956-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="58956-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="58956-199">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="58956-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="58956-200">None</span><span class="sxs-lookup"><span data-stu-id="58956-200">None</span></span>|<span data-ttu-id="58956-201">TRUE</span><span class="sxs-lookup"><span data-stu-id="58956-201">TRUE</span></span>|<span data-ttu-id="58956-202">TRUE</span><span class="sxs-lookup"><span data-stu-id="58956-202">TRUE</span></span>||<span data-ttu-id="58956-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="58956-203">Hello World</span></span>|
   |<span data-ttu-id="58956-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="58956-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="58956-205">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="58956-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="58956-206">None</span><span class="sxs-lookup"><span data-stu-id="58956-206">None</span></span>|<span data-ttu-id="58956-207">TRUE</span><span class="sxs-lookup"><span data-stu-id="58956-207">TRUE</span></span>|<span data-ttu-id="58956-208">TRUE</span><span class="sxs-lookup"><span data-stu-id="58956-208">TRUE</span></span>||<span data-ttu-id="58956-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="58956-209">Goodbye World</span></span>|
  
   <span data-ttu-id="58956-210">Observe que todos los valores del campo **comentarios** no contienen valores; Si un campo no tiene un valor, está vacío.</span><span class="sxs-lookup"><span data-stu-id="58956-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="58956-211">Observe también que el elemento de la primera fila no es legible ni modificable y tiene "ignore" como su valor de **categoría** , lo que indica que el valor no es localizable.</span><span class="sxs-lookup"><span data-stu-id="58956-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="58956-212">Para facilitar la detección de los elementos localizables en los archivos analizados, especialmente en los archivos de gran tamaño, puede ordenar o filtrar los elementos por **categoría**, **legibilidad**y **modificabilidad**.</span><span class="sxs-lookup"><span data-stu-id="58956-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="58956-213">Por ejemplo, puede filtrar los valores ilegibles y no modificables.</span><span class="sxs-lookup"><span data-stu-id="58956-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="58956-214">Traducir el contenido localizable</span><span class="sxs-lookup"><span data-stu-id="58956-214">Translate the localizable content</span></span>

<span data-ttu-id="58956-215">Use cualquier herramienta disponible traducir el contenido extraído.</span><span class="sxs-lookup"><span data-stu-id="58956-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="58956-216">Una buena forma de hacerlo es escribir los recursos en un archivo. csv y verlos en Microsoft Excel, realizando cambios de traducción en la última columna (valor).</span><span class="sxs-lookup"><span data-stu-id="58956-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="58956-217">Usar LocBaml para generar un nuevo archivo. Resources. dll</span><span class="sxs-lookup"><span data-stu-id="58956-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="58956-218">El contenido que se identificó al analizar HelloApp.resources.dll con LocBaml se ha traducido y debe combinarse en la aplicación original.</span><span class="sxs-lookup"><span data-stu-id="58956-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="58956-219">Use la `generate` `-g` opción o para generar un nuevo archivo. Resources. dll.</span><span class="sxs-lookup"><span data-stu-id="58956-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="58956-220">Use la sintaxis siguiente para generar un nuevo archivo HelloApp.resources.dll.</span><span class="sxs-lookup"><span data-stu-id="58956-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="58956-221">Marque la referencia cultural como en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="58956-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="58956-222">Si el archivo de entrada, Hello.csv, no está en el mismo directorio que el ejecutable, LocBaml.exe, mueva uno de los archivos para que ambos se encuentren en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="58956-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="58956-223">Reemplace el archivo *HelloApp. Resources. dll* anterior en el directorio *C:\HelloApp\Bin\Debug\en-US\HelloApp.Resources.dll* por el archivo *HelloApp. Resources. dll* recién creado.</span><span class="sxs-lookup"><span data-stu-id="58956-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="58956-224">“Hello World” y “Goodbye World” deberían aparecer ya traducidos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58956-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="58956-225">Para traducir a una referencia cultural diferente, use la referencia cultural del idioma al que va a traducir.</span><span class="sxs-lookup"><span data-stu-id="58956-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="58956-226">En el ejemplo siguiente se muestra cómo traducir al francés canadiense:</span><span class="sxs-lookup"><span data-stu-id="58956-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="58956-227">En el mismo ensamblado que el ensamblado de aplicación principal, cree una nueva carpeta específica de la referencia cultural para alojar el nuevo ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="58956-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="58956-228">Para el francés canadiense, la carpeta sería fr-CA.</span><span class="sxs-lookup"><span data-stu-id="58956-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="58956-229">Copie el ensamblado satélite generado en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="58956-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="58956-230">Para probar el nuevo ensamblado satélite, deberá cambiar la referencia cultural en la que se ejecutará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58956-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="58956-231">Puede hacerlo de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="58956-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="58956-232">Cambiar la configuración regional del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="58956-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="58956-233">En la aplicación, agregue el código siguiente a App.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="58956-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="58956-234">Sugerencias para usar LocBaml</span><span class="sxs-lookup"><span data-stu-id="58956-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="58956-235">Todos los ensamblados dependientes que definen controles personalizados se deben copiar en el directorio local de LocBaml o instalarse en la GAC (caché global de ensamblados).</span><span class="sxs-lookup"><span data-stu-id="58956-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="58956-236">Esto es necesario porque la API de localización debe tener acceso a los ensamblados dependientes cuando lee el XAML binario (BAML).</span><span class="sxs-lookup"><span data-stu-id="58956-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="58956-237">Si el ensamblado principal está firmado, la DLL de recursos generada también debe estar firmada para que se pueda cargar.</span><span class="sxs-lookup"><span data-stu-id="58956-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="58956-238">La versión de la DLL de recursos localizados debe estar sincronizada con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="58956-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58956-239">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58956-239">See also</span></span>

- [<span data-ttu-id="58956-240">Globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="58956-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="58956-241">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="58956-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
