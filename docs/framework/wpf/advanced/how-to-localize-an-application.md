---
title: 'Cómo: Localizar una aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: 7e034e92e1ff2b9bec0eaf8e0f3330f7a832a7e5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095174"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="29a28-102">Cómo: Localizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="29a28-102">How to: Localize an Application</span></span>
<span data-ttu-id="29a28-103">En este tutorial se explica cómo crear una aplicación localizada mediante la herramienta LocBaml.</span><span class="sxs-lookup"><span data-stu-id="29a28-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29a28-104">La herramienta LocBaml no es una aplicación lista para producción.</span><span class="sxs-lookup"><span data-stu-id="29a28-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="29a28-105">Se presenta como un ejemplo que usa algunas de las API de localización y muestra cómo se podría escribir una herramienta de localización.</span><span class="sxs-lookup"><span data-stu-id="29a28-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="29a28-106">Información general</span><span class="sxs-lookup"><span data-stu-id="29a28-106">Overview</span></span>  
 <span data-ttu-id="29a28-107">En este artículo se ofrece un enfoque detallado para la localización de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="29a28-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="29a28-108">En primer lugar, prepare su aplicación para que se puede extraer el texto que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="29a28-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="29a28-109">Una vez traducido el texto, tendrá que combinar el texto traducido en una nueva copia de la aplicación original.</span><span class="sxs-lookup"><span data-stu-id="29a28-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="29a28-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29a28-110">Requirements</span></span>  
 <span data-ttu-id="29a28-111">En el transcurso de este debate, usará Microsoft Build Engine (MSBuild), que es un compilador que se ejecuta desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="29a28-111">Over the course of this discussion, you will use Microsoft build engine (MSBuild), which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="29a28-112">Además, se le pedirá que use un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="29a28-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="29a28-113">Para obtener instrucciones sobre cómo usar MSBuild y archivos de proyecto, vea [compilar e implementar](../app-development/building-and-deploying-wpf-applications.md).</span><span class="sxs-lookup"><span data-stu-id="29a28-113">For instructions on how to use MSBuild and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="29a28-114">Todos los ejemplos de este artículo usan en-US (inglés-Estados Unidos) como referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="29a28-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="29a28-115">Esto le permitirá trabajar siguiendo los pasos de los ejemplos sin necesidad de instalar un idioma diferente.</span><span class="sxs-lookup"><span data-stu-id="29a28-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="29a28-116">Crear una aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="29a28-116">Create a Sample Application</span></span>  
 <span data-ttu-id="29a28-117">En este paso, preparará la aplicación para la localización.</span><span class="sxs-lookup"><span data-stu-id="29a28-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="29a28-118">En los ejemplos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se proporciona una HelloApp que se usará para los ejemplos de código de este artículo.</span><span class="sxs-lookup"><span data-stu-id="29a28-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="29a28-119">Si desea usar este ejemplo, descargue los archivos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] desde el ejemplo de la [herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="29a28-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="29a28-120">Desarrolle su aplicación hasta el punto donde desea iniciar la localización.</span><span class="sxs-lookup"><span data-stu-id="29a28-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="29a28-121">Especifique el lenguaje de desarrollo en el archivo de proyecto para que MSBuild genere un ensamblado principal y un ensamblado satélite (un archivo con la extensión. Resources. dll) para que contenga los recursos de idioma neutro.</span><span class="sxs-lookup"><span data-stu-id="29a28-121">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="29a28-122">El archivo de proyecto en el ejemplo HelloApp es HelloApp.csproj.</span><span class="sxs-lookup"><span data-stu-id="29a28-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="29a28-123">En ese archivo, encontrará el lenguaje de desarrollo que se identifica como sigue:</span><span class="sxs-lookup"><span data-stu-id="29a28-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="29a28-124">Agregue UID a sus archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29a28-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="29a28-125">Los UID se usan para realizar un seguimiento de los cambios en los archivos y para identificar los elementos que se deben traducir.</span><span class="sxs-lookup"><span data-stu-id="29a28-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="29a28-126">Para agregar UID a los archivos, ejecute **updateuid** en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="29a28-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="29a28-127">**MSBuild-t:updateuid HelloApp. csproj**</span><span class="sxs-lookup"><span data-stu-id="29a28-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="29a28-128">Para comprobar que no faltan UID ni están duplicados, ejecute **checkuid**:</span><span class="sxs-lookup"><span data-stu-id="29a28-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="29a28-129">**MSBuild-t:checkuid HelloApp. csproj**</span><span class="sxs-lookup"><span data-stu-id="29a28-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="29a28-130">Después de ejecutar **updateuid**, los archivos deben contener UID.</span><span class="sxs-lookup"><span data-stu-id="29a28-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="29a28-131">Por ejemplo, en el archivo Pane1.xaml de HelloApp, busque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29a28-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="29a28-132">Crear el ensamblado satélite de recursos de idioma neutro</span><span class="sxs-lookup"><span data-stu-id="29a28-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="29a28-133">Después de configurar la aplicación para que genere un ensamblado satélite de recursos de idioma neutro, compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29a28-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="29a28-134">Esto genera el ensamblado de aplicación principal, así como el ensamblado satélite de recursos de idioma neutro que LocBaml necesita para la localización.</span><span class="sxs-lookup"><span data-stu-id="29a28-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="29a28-135">Para compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="29a28-135">To build the application:</span></span>  
  
1. <span data-ttu-id="29a28-136">Compile HelloApp para crear una biblioteca de vínculos dinámicos (DLL):</span><span class="sxs-lookup"><span data-stu-id="29a28-136">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
     <span data-ttu-id="29a28-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="29a28-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="29a28-138">El ensamblado de aplicación principal que se acaba de crear, HelloApp.exe, se encuentra en la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="29a28-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="29a28-139">El ensamblado satélite de recursos de idioma neutro que se acaba de crear, HelloApp.resources.dll, se crea en la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="29a28-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="29a28-140">Compilar la herramienta LocBaml</span><span class="sxs-lookup"><span data-stu-id="29a28-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="29a28-141">Todos los archivos necesarios para compilar LocBaml se encuentran en los ejemplos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29a28-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="29a28-142">Descargue los C# archivos desde el [ejemplo de la herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span><span class="sxs-lookup"><span data-stu-id="29a28-142">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="29a28-143">Desde la línea de comandos, ejecute el archivo de proyecto (locbaml.csproj) para compilar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="29a28-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="29a28-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="29a28-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="29a28-145">Vaya al directorio Bin\Release para buscar el archivo ejecutable recién creado (locbaml.exe).</span><span class="sxs-lookup"><span data-stu-id="29a28-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="29a28-146">Ejemplo: C:\LocBaml\Bin\Release\locbaml.exe.</span><span class="sxs-lookup"><span data-stu-id="29a28-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="29a28-147">Las opciones que puede especificar al ejecutar LocBaml son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="29a28-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="29a28-148">**Parse** o **-p:** analiza BAML, recursos o archivos DLL para generar un archivo. csv o. txt.</span><span class="sxs-lookup"><span data-stu-id="29a28-148">**parse** or **-p:** Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="29a28-149">**Generate** o **-g:** genera un archivo binario localizado mediante un archivo traducido.</span><span class="sxs-lookup"><span data-stu-id="29a28-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="29a28-150">**out** o **-o** {*filedirectory*] **:** nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="29a28-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="29a28-151">**Culture** o **-CUL** {*Culture*] **:** configuración regional de los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="29a28-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="29a28-152">**Translation** o **-Trans** {*Translation. csv*] **:** archivo traducido o localizado.</span><span class="sxs-lookup"><span data-stu-id="29a28-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="29a28-153">**asmpath** o **-asmpath:** {*filedirectory*] **:** si el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contiene controles personalizados, debe proporcionar el **asmpath** al ensamblado del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="29a28-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="29a28-154">**nologo:** no se muestra ningún logotipo ni la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="29a28-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="29a28-155">**verbose:** se muestra información en modo detallado.</span><span class="sxs-lookup"><span data-stu-id="29a28-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="29a28-156">Si necesita una lista de las opciones cuando ejecute la herramienta, escriba **LocBaml. exe** y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="29a28-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="29a28-157">Usar LocBaml para analizar un archivo</span><span class="sxs-lookup"><span data-stu-id="29a28-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="29a28-158">Ahora que ya ha creado la herramienta LocBaml, está listo para usarla para analizar HelloApp.resources.dll y extraer el contenido de texto que se traducirá.</span><span class="sxs-lookup"><span data-stu-id="29a28-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="29a28-159">Copie LocBaml.exe en la carpeta bin\debug de la aplicación, que es donde se creó el ensamblado de aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="29a28-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="29a28-160">Para analizar el archivo de ensamblado satélite y almacenar la salida como un archivo .csv, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="29a28-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="29a28-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="29a28-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="29a28-162">Si el archivo de entrada, HelloApp.resources.dll, no está en el mismo directorio que LocBaml.exe, mueva uno de los archivos para que ambos archivos se encuentren en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="29a28-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="29a28-163">Cuando se ejecuta LocBaml para analizar los archivos, la salida se compone de siete campos delimitados por comas (archivos .csv) o tabuladores (archivos .txt).</span><span class="sxs-lookup"><span data-stu-id="29a28-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="29a28-164">A continuación se muestra el archivo .csv analizado para HelloApp.resources.dll:</span><span class="sxs-lookup"><span data-stu-id="29a28-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="29a28-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="29a28-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="29a28-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="29a28-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="29a28-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="29a28-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="29a28-168">Los siete campos son:</span><span class="sxs-lookup"><span data-stu-id="29a28-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="29a28-169">**Nombre de BAML**.</span><span class="sxs-lookup"><span data-stu-id="29a28-169">**BAML Name**.</span></span> <span data-ttu-id="29a28-170">Es el nombre del recurso BAML con respecto al ensamblado satélite de lenguaje de origen.</span><span class="sxs-lookup"><span data-stu-id="29a28-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="29a28-171">**Clave de recurso**.</span><span class="sxs-lookup"><span data-stu-id="29a28-171">**Resource Key**.</span></span> <span data-ttu-id="29a28-172">Es el identificador de recursos localizado.</span><span class="sxs-lookup"><span data-stu-id="29a28-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="29a28-173">**Categoría**.</span><span class="sxs-lookup"><span data-stu-id="29a28-173">**Category**.</span></span> <span data-ttu-id="29a28-174">Tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="29a28-174">The value type.</span></span> <span data-ttu-id="29a28-175">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="29a28-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="29a28-176">**Legibilidad**.</span><span class="sxs-lookup"><span data-stu-id="29a28-176">**Readability**.</span></span> <span data-ttu-id="29a28-177">Indica si un localizador puede leer el valor.</span><span class="sxs-lookup"><span data-stu-id="29a28-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="29a28-178">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="29a28-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="29a28-179">**Modificabilidad**.</span><span class="sxs-lookup"><span data-stu-id="29a28-179">**Modifiability**.</span></span> <span data-ttu-id="29a28-180">Indica si un localizador puede modificar el valor.</span><span class="sxs-lookup"><span data-stu-id="29a28-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="29a28-181">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="29a28-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="29a28-182">**Comentarios**.</span><span class="sxs-lookup"><span data-stu-id="29a28-182">**Comments**.</span></span> <span data-ttu-id="29a28-183">Descripción adicional del valor para ayudar a determinar cómo se localiza.</span><span class="sxs-lookup"><span data-stu-id="29a28-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="29a28-184">Vea [atributos y comentarios de localización](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="29a28-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="29a28-185">**Valor**.</span><span class="sxs-lookup"><span data-stu-id="29a28-185">**Value**.</span></span> <span data-ttu-id="29a28-186">Es el valor de texto que se va a traducir a la referencia cultural deseada.</span><span class="sxs-lookup"><span data-stu-id="29a28-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="29a28-187">En la tabla siguiente se muestra la correspondencia entre estos campos y los valores delimitados del archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="29a28-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="29a28-188">Nombre de BAML</span><span class="sxs-lookup"><span data-stu-id="29a28-188">BAML name</span></span>|<span data-ttu-id="29a28-189">Clave de recurso</span><span class="sxs-lookup"><span data-stu-id="29a28-189">Resource key</span></span>|<span data-ttu-id="29a28-190">Category</span><span class="sxs-lookup"><span data-stu-id="29a28-190">Category</span></span>|<span data-ttu-id="29a28-191">Legibilidad</span><span class="sxs-lookup"><span data-stu-id="29a28-191">Readability</span></span>|<span data-ttu-id="29a28-192">Modificabilidad</span><span class="sxs-lookup"><span data-stu-id="29a28-192">Modifiability</span></span>|<span data-ttu-id="29a28-193">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29a28-193">Comments</span></span>|<span data-ttu-id="29a28-194">Value</span><span class="sxs-lookup"><span data-stu-id="29a28-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="29a28-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="29a28-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="29a28-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="29a28-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="29a28-197">Ignore</span><span class="sxs-lookup"><span data-stu-id="29a28-197">Ignore</span></span>|<span data-ttu-id="29a28-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="29a28-198">FALSE</span></span>|<span data-ttu-id="29a28-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="29a28-199">FALSE</span></span>||<span data-ttu-id="29a28-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="29a28-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="29a28-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="29a28-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="29a28-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="29a28-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="29a28-203">None</span><span class="sxs-lookup"><span data-stu-id="29a28-203">None</span></span>|<span data-ttu-id="29a28-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="29a28-204">TRUE</span></span>|<span data-ttu-id="29a28-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="29a28-205">TRUE</span></span>||<span data-ttu-id="29a28-206">Hola mundo</span><span class="sxs-lookup"><span data-stu-id="29a28-206">Hello World</span></span>|
   |<span data-ttu-id="29a28-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="29a28-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="29a28-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="29a28-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="29a28-209">None</span><span class="sxs-lookup"><span data-stu-id="29a28-209">None</span></span>|<span data-ttu-id="29a28-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="29a28-210">TRUE</span></span>|<span data-ttu-id="29a28-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="29a28-211">TRUE</span></span>||<span data-ttu-id="29a28-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="29a28-212">Goodbye World</span></span>|
  
   <span data-ttu-id="29a28-213">Observe que todos los valores del campo **comentarios** no contienen valores; Si un campo no tiene un valor, está vacío.</span><span class="sxs-lookup"><span data-stu-id="29a28-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="29a28-214">Observe también que el elemento de la primera fila no es legible ni modificable y tiene "ignore" como su valor de **categoría** , lo que indica que el valor no es localizable.</span><span class="sxs-lookup"><span data-stu-id="29a28-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="29a28-215">Para facilitar la detección de los elementos localizables en los archivos analizados, especialmente en los archivos de gran tamaño, puede ordenar o filtrar los elementos por **categoría**, **legibilidad**y **modificabilidad**.</span><span class="sxs-lookup"><span data-stu-id="29a28-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="29a28-216">Por ejemplo, puede filtrar los valores ilegibles y no modificables.</span><span class="sxs-lookup"><span data-stu-id="29a28-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="29a28-217">Traducir el contenido Localizable</span><span class="sxs-lookup"><span data-stu-id="29a28-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="29a28-218">Use cualquier herramienta disponible traducir el contenido extraído.</span><span class="sxs-lookup"><span data-stu-id="29a28-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="29a28-219">Una buena forma de hacerlo es escribir los recursos en un archivo. csv y verlos en Microsoft Excel, realizando cambios de traducción en la última columna (valor).</span><span class="sxs-lookup"><span data-stu-id="29a28-219">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="29a28-220">Usar LocBaml para generar un nuevo archivo .resources.dll</span><span class="sxs-lookup"><span data-stu-id="29a28-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="29a28-221">El contenido que se identificó al analizar HelloApp.resources.dll con LocBaml se ha traducido y debe combinarse en la aplicación original.</span><span class="sxs-lookup"><span data-stu-id="29a28-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="29a28-222">Use la opción **Generate** o **-g** para generar un nuevo archivo. Resources. dll.</span><span class="sxs-lookup"><span data-stu-id="29a28-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="29a28-223">Use la sintaxis siguiente para generar un nuevo archivo HelloApp.resources.dll.</span><span class="sxs-lookup"><span data-stu-id="29a28-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="29a28-224">Marque la referencia cultural como en-US (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="29a28-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="29a28-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="29a28-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="29a28-226">Si el archivo de entrada, Hello.csv, no está en el mismo directorio que el ejecutable, LocBaml.exe, mueva uno de los archivos para que ambos se encuentren en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="29a28-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="29a28-227">Reemplace el archivo HelloApp.resources.dll anterior en el directorio C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll por el archivo HelloApp.resources.dll recién creado.</span><span class="sxs-lookup"><span data-stu-id="29a28-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="29a28-228">“Hello World” y “Goodbye World” deberían aparecer ya traducidos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29a28-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="29a28-229">Para traducir a una referencia cultural diferente, use la referencia cultural del idioma al que va a traducir.</span><span class="sxs-lookup"><span data-stu-id="29a28-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="29a28-230">En el ejemplo siguiente se muestra cómo traducir al francés canadiense:</span><span class="sxs-lookup"><span data-stu-id="29a28-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="29a28-231">**LocBaml. exe/Generate HelloApp. Resources. dll/trans: Hellofr-CA. csv/out: c:\/CUL: FR-CA**</span><span class="sxs-lookup"><span data-stu-id="29a28-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="29a28-232">En el mismo ensamblado que el ensamblado de aplicación principal, cree una nueva carpeta específica de la referencia cultural para alojar el nuevo ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="29a28-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="29a28-233">Para el francés canadiense, la carpeta sería fr-CA.</span><span class="sxs-lookup"><span data-stu-id="29a28-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="29a28-234">Copie el ensamblado satélite generado en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="29a28-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="29a28-235">Para probar el nuevo ensamblado satélite, deberá cambiar la referencia cultural en la que se ejecutará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29a28-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="29a28-236">Puede hacerlo de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="29a28-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="29a28-237">Cambie la configuración regional de su sistema operativo (**Inicio** &#124; configuración **regional y de idioma**del panel &#124; de **control** ).</span><span class="sxs-lookup"><span data-stu-id="29a28-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="29a28-238">En la aplicación, agregue el código siguiente a App.xaml.cs:</span><span class="sxs-lookup"><span data-stu-id="29a28-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="29a28-239">Algunas sugerencias para el uso de LocBaml</span><span class="sxs-lookup"><span data-stu-id="29a28-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="29a28-240">Todos los ensamblados dependientes que definen controles personalizados se deben copiar en el directorio local de LocBaml o instalarse en la GAC (caché global de ensamblados).</span><span class="sxs-lookup"><span data-stu-id="29a28-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="29a28-241">Esto es necesario porque la API de localización debe tener acceso a los ensamblados dependientes cuando lee el XAML binario (BAML).</span><span class="sxs-lookup"><span data-stu-id="29a28-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="29a28-242">Si el ensamblado principal está firmado, la DLL de recursos generada también debe estar firmada para que se pueda cargar.</span><span class="sxs-lookup"><span data-stu-id="29a28-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="29a28-243">La versión de la DLL de recursos localizados debe estar sincronizada con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="29a28-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="29a28-244">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="29a28-244">What's Next</span></span>  
 <span data-ttu-id="29a28-245">Ahora que ya tiene un conocimiento básico de cómo usar la herramienta LocBaml,</span><span class="sxs-lookup"><span data-stu-id="29a28-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="29a28-246">será capaz de crear un archivo que contenga UID.</span><span class="sxs-lookup"><span data-stu-id="29a28-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="29a28-247">Al usar la herramienta LocBaml, podrá analizar un archivo para extraer el contenido localizable y, después de traducir el contenido, podrá generar un archivo .resources.dll en el que se combine el contenido traducido.</span><span class="sxs-lookup"><span data-stu-id="29a28-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="29a28-248">En este tema no incluyen todos los detalles posibles, pero ahora ya dispone de los conocimientos necesarios para usar LocBaml en la localización de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="29a28-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a28-249">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29a28-249">See also</span></span>

- [<span data-ttu-id="29a28-250">Globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="29a28-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="29a28-251">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="29a28-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
