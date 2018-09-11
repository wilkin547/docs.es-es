---
title: Empaquetar e implementar extensiones My (Visual Basic) de personalizadas
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271132"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="41df5-102">Empaquetar e implementar extensiones My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41df5-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="41df5-103">Visual Basic proporciona una manera fácil de implementar personalizado `My` extensiones de espacio de nombres mediante el uso de plantillas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41df5-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="41df5-104">Si va a crear una plantilla de proyecto para que su `My` las extensiones son una parte integral del nuevo tipo de proyecto, simplemente puede incluir el personalizado `My` código de extensión con el proyecto al exportar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="41df5-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="41df5-105">Para obtener más información acerca de cómo exportar las plantillas de proyecto, vea [Cómo: crear plantillas de proyecto](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="41df5-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="41df5-106">Si su custom `My` extensión está en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="41df5-107">A continuación, puede personalizar la plantilla de elemento para habilitar funcionalidades adicionales y el comportamiento personalizado `My` extensión en un proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="41df5-108">Estas funcionalidades incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41df5-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="41df5-109">Lo que permite a los usuarios administrar personalizado `My` extensión desde el **extensiones My** página del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="41df5-110">Agregar automáticamente personalizado `My` extensión cuando una referencia a un ensamblado especificado se agrega a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="41df5-111">Ocultar el `My` plantilla de elemento de extensión en el **Agregar elemento** cuadro de diálogo para que no se incluye en la lista de elementos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="41df5-112">Este tema describe cómo empaquetar una personalizada `My` extensión como una plantilla de elemento oculto que se puede administrar desde el **extensiones My** página del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="41df5-113">Personalizado `My` extensión también se puede agregar automáticamente cuando se agrega una referencia a un ensamblado especificado a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="41df5-114">Crear una extensión de espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="41df5-114">Create a My namespace extension</span></span>

<span data-ttu-id="41df5-115">El primer paso para crear un paquete de implementación para un personalizado `My` extensión consiste en crear la extensión como un archivo de código único.</span><span class="sxs-lookup"><span data-stu-id="41df5-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="41df5-116">Para obtener detalles y orientación sobre cómo crear una personalizada `My` extensión, vea [extender el Namespace My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="41df5-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="41df5-117">Exportar una extensión de espacio de nombres My como una plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="41df5-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="41df5-118">Una vez que tenga un archivo de código que incluye su `My` extensión del espacio de nombres, puede exportar el archivo de código como una plantilla de elemento de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41df5-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="41df5-119">Para obtener instrucciones sobre cómo exportar un archivo como una plantilla de elemento de Visual Studio, consulte [Cómo: crear plantillas de elementos](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="41df5-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="41df5-120">Si su `My` extensión del espacio de nombres tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente su `My` extensión del espacio de nombres cuando se agrega una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41df5-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="41df5-121">Como resultado, que desea excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elemento de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41df5-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="41df5-122">Personalizar la plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="41df5-122">Customize the item template</span></span>

<span data-ttu-id="41df5-123">Puede habilitar la plantilla de elemento para administrarse desde el **extensiones My** página del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="41df5-124">También puede habilitar la plantilla de elemento que se agregará automáticamente cuando se agrega una referencia a un ensamblado especificado a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="41df5-125">Para habilitar estas personalizaciones, agregará un nuevo archivo denominado CustomData, a la plantilla y, a continuación, agregue un nuevo elemento al XML en el archivo .vstemplate.</span><span class="sxs-lookup"><span data-stu-id="41df5-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="41df5-126">Agregue el archivo CustomData</span><span class="sxs-lookup"><span data-stu-id="41df5-126">Add the CustomData file</span></span>

<span data-ttu-id="41df5-127">El archivo CustomData es un archivo de texto que tiene una extensión de nombre de archivo. CustomData (el nombre de archivo puede establecerse en cualquier valor significativo para la plantilla) y que contiene XML.</span><span class="sxs-lookup"><span data-stu-id="41df5-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="41df5-128">El XML en el archivo CustomData indica a Visual Basic para incluir su `My` extensión cuando los usuarios usen el **extensiones My** página del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="41df5-129">Opcionalmente, puede agregar el <`AssemblyFullName>` atributo al archivo CustomData XML.</span><span class="sxs-lookup"><span data-stu-id="41df5-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="41df5-130">Esto indica a Visual Basic para instalar automáticamente el personalizado `My` extensión cuando una referencia a un ensamblado determinado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="41df5-131">Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, a continuación, agregarlo a la carpeta comprimida (archivo .zip) de la plantilla del elemento.</span><span class="sxs-lookup"><span data-stu-id="41df5-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="41df5-132">Por ejemplo, el siguiente XML muestra el contenido de un archivo CustomData que agregará el elemento de plantilla en la carpeta Extensiones My de un proyecto de Visual Basic cuando una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.Vs.dll se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="41df5-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="41df5-133">El archivo CustomData contiene un <`VBMyExtensionTemplate>` elemento que tiene atributos como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="41df5-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="41df5-134">Atributo</span><span class="sxs-lookup"><span data-stu-id="41df5-134">Attribute</span></span>|<span data-ttu-id="41df5-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="41df5-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="41df5-136">Requerido.</span><span class="sxs-lookup"><span data-stu-id="41df5-136">Required.</span></span> <span data-ttu-id="41df5-137">Un identificador único para la extensión.</span><span class="sxs-lookup"><span data-stu-id="41df5-137">A unique identifier for the extension.</span></span> <span data-ttu-id="41df5-138">Si la extensión que tiene este identificador ya se ha agregado al proyecto, no se pedirá al usuario que vuelva a agregarlo.</span><span class="sxs-lookup"><span data-stu-id="41df5-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="41df5-139">Requerido.</span><span class="sxs-lookup"><span data-stu-id="41df5-139">Required.</span></span> <span data-ttu-id="41df5-140">Un número de versión para la plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="41df5-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="41df5-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="41df5-141">Optional.</span></span> <span data-ttu-id="41df5-142">Nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41df5-142">An assembly name.</span></span> <span data-ttu-id="41df5-143">Cuando se agrega una referencia a este ensamblado al proyecto, se pedirá al usuario para agregar el `My` extensión desde esta plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="41df5-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="41df5-144">Agregar el \<CustomDataSignature > elemento para el archivo .vstemplate</span><span class="sxs-lookup"><span data-stu-id="41df5-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="41df5-145">Para identificar la plantilla de elemento de Visual Studio como un `My` extensión del espacio de nombres, también debe modificar el archivo .vstemplate para la plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="41df5-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="41df5-146">Debe agregar un `<CustomDataSignature>` elemento a la `<TemplateData>` elemento.</span><span class="sxs-lookup"><span data-stu-id="41df5-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="41df5-147">El `<CustomDataSignature>` elemento debe contener el texto `Microsoft.VisualBasic.MyExtension`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="41df5-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="41df5-148">No puede modificar directamente los archivos en una carpeta comprimida (archivo .zip).</span><span class="sxs-lookup"><span data-stu-id="41df5-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="41df5-149">Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, a continuación, reemplace el archivo .vstemplate en la carpeta comprimida por la copia actualizada.</span><span class="sxs-lookup"><span data-stu-id="41df5-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="41df5-150">El ejemplo siguiente muestra el contenido de un archivo .vstemplate que tiene el `<CustomDataSignature>` elemento agregado.</span><span class="sxs-lookup"><span data-stu-id="41df5-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a><span data-ttu-id="41df5-151">Instalar la plantilla</span><span class="sxs-lookup"><span data-stu-id="41df5-151">Install the template</span></span>

<span data-ttu-id="41df5-152">Para instalar la plantilla, puede copiar la carpeta comprimida (*.zip* archivo) a la carpeta de plantillas de elemento de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="41df5-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="41df5-153">De forma predeterminada, las plantillas de elemento de usuario se encuentran en *%USERPROFILE%\Documents\Visual Studio \<versión\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="41df5-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="41df5-154">Como alternativa, puede publicar la plantilla como un instalador de Visual Studio (*.vsi*) archivo.</span><span class="sxs-lookup"><span data-stu-id="41df5-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="41df5-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="41df5-155">See also</span></span>

- [<span data-ttu-id="41df5-156">Extender el espacio de nombres My en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41df5-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="41df5-157">Extensión del modelo de la aplicación de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41df5-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="41df5-158">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="41df5-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="41df5-159">Página Mis extensiones del Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="41df5-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
