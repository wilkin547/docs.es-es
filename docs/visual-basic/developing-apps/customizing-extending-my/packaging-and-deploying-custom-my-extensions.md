---
title: Empaquetado e implementación de extensiones personalizadas de My
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 6d2cc2b01b04b30bd3b1a4371352ded20ea8664b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411758"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="691b5-102">Empaquetar e implementar extensiones personalizadas de My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="691b5-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="691b5-103">Visual Basic proporciona una forma sencilla de implementar las extensiones personalizadas de espacio de nombres de `My` mediante plantillas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="691b5-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="691b5-104">Si va a crear una plantilla de proyecto para la que las extensiones de `My` son una parte integral del nuevo tipo de proyecto, puede incluir simplemente el código personalizado de la extensión de `My` con el proyecto cuando exporte la plantilla.</span><span class="sxs-lookup"><span data-stu-id="691b5-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="691b5-105">Para obtener más información sobre la exportación de plantillas de proyecto, vea [Cómo: Crear plantillas de proyecto](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="691b5-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="691b5-106">Si la extensión personalizada de `My` se encuentra en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="691b5-107">Después, puede personalizar la plantilla de elemento para habilitar un comportamiento y capacidades adicionales de la extensión personalizada de `My` en un proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="691b5-108">Dichas capacidades incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="691b5-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="691b5-109">Permitir a los usuarios administrar la extensión personalizada de `My` desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="691b5-110">Agregar automáticamente la extensión personalizada de `My` cuando se agrega a un proyecto una referencia a un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="691b5-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="691b5-111">Ocultar la plantilla de elemento de extensión de `My` en el cuadro de diálogo **Agregar elemento** para que no se incluya en la lista de elementos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="691b5-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="691b5-112">En este tema se describe cómo empaquetar una extensión personalizada de `My` como una plantilla de elemento oculta que se puede administrar desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="691b5-113">La extensión personalizada de `My` también se puede agregar automáticamente cuando se agrega a un proyecto una referencia a un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="691b5-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="691b5-114">Creación de una extensión de espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="691b5-114">Create a My namespace extension</span></span>

<span data-ttu-id="691b5-115">El primer paso para crear un paquete de implementación para una extensión personalizada de `My` es crear la extensión como un solo archivo de código.</span><span class="sxs-lookup"><span data-stu-id="691b5-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="691b5-116">Para obtener información sobre cómo crear extensiones personalizadas de `My`, vea [Extender el espacio de nombres My en Visual Basic](extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="691b5-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="691b5-117">Exportación de una extensión de espacio de nombres My como una plantilla de elementos</span><span class="sxs-lookup"><span data-stu-id="691b5-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="691b5-118">Después de tener un archivo de código que incluya la extensión de espacio de nombres `My`, puede exportar el archivo de código como una plantilla de elementos de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="691b5-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="691b5-119">Para obtener instrucciones sobre cómo exportar un archivo como una plantilla de elemento de Visual Studio, vea [Cómo: Crear plantillas de elementos](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="691b5-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="691b5-120">Si la extensión de espacio de nombres `My` tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente la extensión de espacio de nombres `My` cuando se agregue una referencia a ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="691b5-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="691b5-121">Como resultado, le interesa excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elementos de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="691b5-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="691b5-122">Personalización de la plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="691b5-122">Customize the item template</span></span>

<span data-ttu-id="691b5-123">Puede habilitar la plantilla de elemento que se va a administrar desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="691b5-124">También puede habilitar la plantilla de elemento para que se agregue automáticamente cuando se agrega a un proyecto una referencia a un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="691b5-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="691b5-125">Para habilitar estas personalizaciones, agregará a la plantilla un nuevo archivo, denominado CustomData y, después, agregará un nuevo elemento al XML en el archivo .vstemplate.</span><span class="sxs-lookup"><span data-stu-id="691b5-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="691b5-126">Adición del archivo CustomData</span><span class="sxs-lookup"><span data-stu-id="691b5-126">Add the CustomData file</span></span>

<span data-ttu-id="691b5-127">El archivo CustomData es un archivo de texto que tiene la extensión de nombre de archivo .CustomData (el nombre de archivo se puede establecer en cualquier valor significativo para la plantilla) y que contiene XML.</span><span class="sxs-lookup"><span data-stu-id="691b5-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="691b5-128">El XML en el archivo CustomData indica a Visual Basic que incluya su extensión de `My` cuando los usuarios usen la página **Extensiones de My** del Diseñador de proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="691b5-129">Opcionalmente, puede agregar el atributo <`AssemblyFullName>` al código XML del archivo CustomData.</span><span class="sxs-lookup"><span data-stu-id="691b5-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="691b5-130">Esto indica a Visual Basic que instale automáticamente la extensión personalizada de `My` cuando se agregue al proyecto una referencia a un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="691b5-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="691b5-131">Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, después, agregarlo a la carpeta comprimida de la plantilla de elemento (archivo .zip).</span><span class="sxs-lookup"><span data-stu-id="691b5-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="691b5-132">Por ejemplo, el código XML siguiente muestra el contenido de un archivo CustomData que agregará el elemento de plantilla a la carpeta Extensiones de My de un proyecto Visual Basic cuando se agregue al proyecto una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.vs.dll.</span><span class="sxs-lookup"><span data-stu-id="691b5-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="691b5-133">El archivo CustomData contiene un elemento <`VBMyExtensionTemplate>` que tiene los atributos que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="691b5-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="691b5-134">Atributo</span><span class="sxs-lookup"><span data-stu-id="691b5-134">Attribute</span></span>|<span data-ttu-id="691b5-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="691b5-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="691b5-136">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="691b5-136">Required.</span></span> <span data-ttu-id="691b5-137">Identificador único para la extensión.</span><span class="sxs-lookup"><span data-stu-id="691b5-137">A unique identifier for the extension.</span></span> <span data-ttu-id="691b5-138">Si la extensión que tiene este identificador ya se ha agregado al proyecto, no se le pedirá al usuario que la vuelva a agregar.</span><span class="sxs-lookup"><span data-stu-id="691b5-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="691b5-139">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="691b5-139">Required.</span></span> <span data-ttu-id="691b5-140">Número de versión para la plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="691b5-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="691b5-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="691b5-141">Optional.</span></span> <span data-ttu-id="691b5-142">Nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="691b5-142">An assembly name.</span></span> <span data-ttu-id="691b5-143">Cuando se agrega al proyecto una referencia a este ensamblado, se le pedirá al usuario que agregue la extensión de `My` de esta plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="691b5-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="691b5-144">Adición del elemento \<CustomDataSignature> al archivo .vstemplate</span><span class="sxs-lookup"><span data-stu-id="691b5-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="691b5-145">Para identificar la plantilla de elemento de Visual Studio como una extensión de espacio de nombres `My`, también debe modificar el archivo .vstemplate para la plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="691b5-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="691b5-146">Debe agregar un elemento `<CustomDataSignature>` al elemento `<TemplateData>`.</span><span class="sxs-lookup"><span data-stu-id="691b5-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="691b5-147">El elemento `<CustomDataSignature>` debe contener el texto `Microsoft.VisualBasic.MyExtension`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="691b5-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="691b5-148">Los archivos de una carpeta comprimida (archivo .zip) no se pueden modificar directamente.</span><span class="sxs-lookup"><span data-stu-id="691b5-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="691b5-149">Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, después, reemplazar el archivo .vstemplate de la carpeta comprimida con la copia actualizada.</span><span class="sxs-lookup"><span data-stu-id="691b5-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="691b5-150">El ejemplo siguiente muestra el contenido completo de un archivo .vstemplate al que se le ha agregado el elemento `<CustomDataSignature>`.</span><span class="sxs-lookup"><span data-stu-id="691b5-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="691b5-151">Instalación de la plantilla</span><span class="sxs-lookup"><span data-stu-id="691b5-151">Install the template</span></span>

<span data-ttu-id="691b5-152">Para instalar la plantilla, puede copiar la carpeta comprimida (archivo *.zip*) en la carpeta de plantillas de elemento de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="691b5-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="691b5-153">De manera predeterminada, las plantillas de elemento de usuario se encuentran en *%USERPROFILE%\Documentos\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="691b5-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="691b5-154">Como alternativa, puede encontrar la plantilla como un archivo del Instalador de Visual Studio ( *.vsi*).</span><span class="sxs-lookup"><span data-stu-id="691b5-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="691b5-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="691b5-155">See also</span></span>

- [<span data-ttu-id="691b5-156">Extender el espacio de nombres My en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="691b5-156">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)
- [<span data-ttu-id="691b5-157">Extensión del modelo de la aplicación de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="691b5-157">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="691b5-158">Personalización de los objetos que están disponibles en My</span><span class="sxs-lookup"><span data-stu-id="691b5-158">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="691b5-159">Página Mis extensiones del Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="691b5-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
