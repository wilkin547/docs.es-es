---
title: Empaquetar e implementar extensiones My personalizadas
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330260"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Empaquetar e implementar extensiones My personalizadas (Visual Basic)

Visual Basic proporciona una manera fácil de implementar las extensiones de espacio de nombres de `My` personalizadas mediante plantillas de Visual Studio. Si va a crear una plantilla de proyecto para la que las extensiones de `My` son una parte integral del nuevo tipo de proyecto, puede incluir simplemente el código personalizado de la extensión de `My` con el proyecto cuando exporte la plantilla. Para obtener más información sobre cómo exportar plantillas de proyecto, vea [Cómo: crear plantillas de proyecto](/visualstudio/ide/how-to-create-project-templates).

Si la extensión de `My` personalizada se encuentra en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic. A continuación, puede personalizar la plantilla de elemento para habilitar funciones adicionales y el comportamiento de la extensión de `My` personalizada en un proyecto de Visual Basic. Estas funcionalidades incluyen las siguientes:

- Permitir a los usuarios administrar la extensión de `My` personalizada desde la página **mis extensiones** del diseñador de proyectos de Visual Basic.

- Agregar automáticamente la extensión de `My` personalizada cuando se agrega a un proyecto una referencia a un ensamblado especificado.

- Ocultar la plantilla de elemento de extensión `My` en el cuadro de diálogo **Agregar elemento** para que no se incluya en la lista de elementos de proyecto.

En este tema se describe cómo empaquetar una extensión de `My` personalizada como una plantilla de elementos oculta que se puede administrar desde la página **mis extensiones** del diseñador de proyectos de Visual Basic. También se puede Agregar automáticamente la extensión de `My` personalizada cuando se agrega a un proyecto una referencia a un ensamblado especificado.

## <a name="create-a-my-namespace-extension"></a>Crear una extensión de espacio de nombres My

El primer paso para crear un paquete de implementación para una extensión de `My` personalizada es crear la extensión como un solo archivo de código. Para obtener información detallada e instrucciones sobre cómo crear una extensión de `My` personalizada, vea [extender el espacio de nombres My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportar una extensión de espacio de nombres My como una plantilla de elementos

Después de tener un archivo de código que incluya la extensión de espacio de nombres `My`, puede exportar el archivo de código como una plantilla de elementos de Visual Studio. Para obtener instrucciones sobre cómo exportar un archivo como una plantilla de elementos de Visual Studio, vea [Cómo: crear plantillas de elementos](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Si la extensión de espacio de nombres de `My` tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente la extensión de espacio de nombres de `My` cuando se agrega una referencia a ese ensamblado. Como resultado, querrá excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elementos de Visual Studio.

## <a name="customize-the-item-template"></a>Personalizar la plantilla de elemento

Puede habilitar la administración de la plantilla de elementos desde la página **mis extensiones** del diseñador de proyectos de Visual Basic. También puede habilitar la plantilla de elementos que se agregará automáticamente cuando se agregue una referencia a un ensamblado especificado a un proyecto. Para habilitar estas personalizaciones, agregará un nuevo archivo, denominado archivo CustomData, a la plantilla y, a continuación, agregará un nuevo elemento al XML en el archivo. vstemplate.

### <a name="add-the-customdata-file"></a>Agregar el archivo CustomData

El archivo CustomData es un archivo de texto que tiene la extensión de nombre de archivo. CustomData (el nombre de archivo se puede establecer en cualquier valor significativo para la plantilla) y que contiene XML. El XML del archivo CustomData indica a Visual Basic que incluya su extensión de `My` cuando los usuarios usen la página **mis extensiones** del diseñador de proyectos de Visual Basic. Opcionalmente, puede Agregar el <`AssemblyFullName>` atributo al archivo CustomData XML. Esto indica a Visual Basic que instale automáticamente la extensión de `My` personalizada cuando se agrega al proyecto una referencia a un ensamblado determinado. Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, a continuación, agregarlo a la carpeta comprimida de la plantilla de elementos (archivo. zip).

Por ejemplo, el código XML siguiente muestra el contenido de un archivo CustomData que agregará el elemento de plantilla a la carpeta My Extensions de un proyecto Visual Basic cuando se agregue al proyecto una referencia al ensamblado Microsoft. VisualBasic. PowerPacks. vs. dll.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

El archivo CustomData contiene un <`VBMyExtensionTemplate>` elemento que tiene los atributos que se muestran en la tabla siguiente.

|Atributo|Descripción|
|---|---|
|`ID`|Obligatorio. Identificador único de la extensión. Si la extensión que tiene este identificador ya se ha agregado al proyecto, no se le pedirá al usuario que lo agregue de nuevo.|
|`Version`|Obligatorio. Un número de versión para la plantilla de elemento.|
|`AssemblyFullName`|Opcional. Nombre de ensamblado. Cuando se agrega al proyecto una referencia a este ensamblado, se le pedirá al usuario que agregue la extensión `My` a partir de esta plantilla de elemento.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Agregue el elemento \<CustomDataSignature > al archivo. vstemplate.

Para identificar la plantilla de elementos de Visual Studio como una extensión de espacio de nombres `My`, también debe modificar el archivo. vstemplate para la plantilla de elementos. Debe agregar un elemento `<CustomDataSignature>` al elemento `<TemplateData>`. El elemento `<CustomDataSignature>` debe contener el `Microsoft.VisualBasic.MyExtension`de texto, como se muestra en el ejemplo siguiente.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Los archivos de una carpeta comprimida (archivo. zip) no se pueden modificar directamente. Debe copiar el archivo. vstemplate de la carpeta comprimida, modificarlo y, a continuación, reemplazar el archivo. vstemplate de la carpeta comprimida por la copia actualizada.

En el ejemplo siguiente se muestra el contenido de un archivo. vstemplate que tiene agregado el elemento `<CustomDataSignature>`.

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

## <a name="install-the-template"></a>Instalación de la plantilla

Para instalar la plantilla, puede copiar la carpeta comprimida (archivo *. zip* ) en la carpeta de plantillas de elementos de Visual Basic. De forma predeterminada, las plantillas de elemento de usuario se encuentran en *%userprofile%\Documents\Visual Studio \<versión\>\Templates\ItemTemplates\Visual Basic*. Como alternativa, puede publicar la plantilla como un archivo Instalador de Visual Studio ( *. VSI*).

## <a name="see-also"></a>Vea también

- [Extender el espacio de nombres My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Página Mis extensiones del Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
