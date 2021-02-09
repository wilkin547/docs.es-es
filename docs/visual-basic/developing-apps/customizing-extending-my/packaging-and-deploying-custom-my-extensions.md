---
description: 'Más información acerca de: Empaquetar e implementar extensiones personalizadas de My (Visual Basic)'
title: Empaquetado e implementación de extensiones personalizadas de My
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 7037cc72951fc5228ae47998f39dca3455bf57de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775414"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Empaquetar e implementar extensiones personalizadas de My (Visual Basic)

Visual Basic proporciona una forma sencilla de implementar las extensiones personalizadas de espacio de nombres de `My` mediante plantillas de Visual Studio. Si va a crear una plantilla de proyecto para la que las extensiones de `My` son una parte integral del nuevo tipo de proyecto, puede incluir simplemente el código personalizado de la extensión de `My` con el proyecto cuando exporte la plantilla. Para obtener más información sobre la exportación de plantillas de proyecto, vea [Cómo: Crear plantillas de proyecto](/visualstudio/ide/how-to-create-project-templates).

Si la extensión personalizada de `My` se encuentra en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic. Después, puede personalizar la plantilla de elemento para habilitar un comportamiento y capacidades adicionales de la extensión personalizada de `My` en un proyecto de Visual Basic. Dichas capacidades incluyen las siguientes:

- Permitir a los usuarios administrar la extensión personalizada de `My` desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic.

- Agregar automáticamente la extensión personalizada de `My` cuando se agrega a un proyecto una referencia a un ensamblado especificado.

- Ocultar la plantilla de elemento de extensión de `My` en el cuadro de diálogo **Agregar elemento** para que no se incluya en la lista de elementos de proyecto.

En este tema se describe cómo empaquetar una extensión personalizada de `My` como una plantilla de elemento oculta que se puede administrar desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic. La extensión personalizada de `My` también se puede agregar automáticamente cuando se agrega a un proyecto una referencia a un ensamblado especificado.

## <a name="create-a-my-namespace-extension"></a>Creación de una extensión de espacio de nombres My

El primer paso para crear un paquete de implementación para una extensión personalizada de `My` es crear la extensión como un solo archivo de código. Para obtener información sobre cómo crear extensiones personalizadas de `My`, vea [Extender el espacio de nombres My en Visual Basic](extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportación de una extensión de espacio de nombres My como una plantilla de elementos

Después de tener un archivo de código que incluya la extensión de espacio de nombres `My`, puede exportar el archivo de código como una plantilla de elementos de Visual Studio. Para obtener instrucciones sobre cómo exportar un archivo como una plantilla de elemento de Visual Studio, vea [Cómo: Crear plantillas de elementos](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Si la extensión de espacio de nombres `My` tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente la extensión de espacio de nombres `My` cuando se agregue una referencia a ese ensamblado. Como resultado, le interesa excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elementos de Visual Studio.

## <a name="customize-the-item-template"></a>Personalización de la plantilla de elemento

Puede habilitar la plantilla de elemento que se va a administrar desde la página **Extensiones de My** del Diseñador de proyectos de Visual Basic. También puede habilitar la plantilla de elemento para que se agregue automáticamente cuando se agrega a un proyecto una referencia a un ensamblado especificado. Para habilitar estas personalizaciones, agregará a la plantilla un nuevo archivo, denominado CustomData y, después, agregará un nuevo elemento al XML en el archivo .vstemplate.

### <a name="add-the-customdata-file"></a>Adición del archivo CustomData

El archivo CustomData es un archivo de texto que tiene la extensión de nombre de archivo .CustomData (el nombre de archivo se puede establecer en cualquier valor significativo para la plantilla) y que contiene XML. El XML en el archivo CustomData indica a Visual Basic que incluya su extensión de `My` cuando los usuarios usen la página **Extensiones de My** del Diseñador de proyectos de Visual Basic. Opcionalmente, puede agregar el atributo <`AssemblyFullName>` al código XML del archivo CustomData. Esto indica a Visual Basic que instale automáticamente la extensión personalizada de `My` cuando se agregue al proyecto una referencia a un ensamblado determinado. Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, después, agregarlo a la carpeta comprimida de la plantilla de elemento (archivo .zip).

Por ejemplo, el código XML siguiente muestra el contenido de un archivo CustomData que agregará el elemento de plantilla a la carpeta Extensiones de My de un proyecto Visual Basic cuando se agregue al proyecto una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.vs.dll.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

El archivo CustomData contiene un elemento <`VBMyExtensionTemplate>` que tiene los atributos que se muestran en la tabla siguiente.

|Atributo|Descripción|
|---|---|
|`ID`|Obligatorio. Identificador único para la extensión. Si la extensión que tiene este identificador ya se ha agregado al proyecto, no se le pedirá al usuario que la vuelva a agregar.|
|`Version`|Obligatorio. Número de versión para la plantilla de elemento.|
|`AssemblyFullName`|Opcional. Nombre de ensamblado. Cuando se agrega al proyecto una referencia a este ensamblado, se le pedirá al usuario que agregue la extensión de `My` de esta plantilla de elemento.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Adición del elemento \<CustomDataSignature> al archivo .vstemplate

Para identificar la plantilla de elemento de Visual Studio como una extensión de espacio de nombres `My`, también debe modificar el archivo .vstemplate para la plantilla de elemento. Debe agregar un elemento `<CustomDataSignature>` al elemento `<TemplateData>`. El elemento `<CustomDataSignature>` debe contener el texto `Microsoft.VisualBasic.MyExtension`, como se muestra en el ejemplo siguiente.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Los archivos de una carpeta comprimida (archivo .zip) no se pueden modificar directamente. Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, después, reemplazar el archivo .vstemplate de la carpeta comprimida con la copia actualizada.

El ejemplo siguiente muestra el contenido completo de un archivo .vstemplate al que se le ha agregado el elemento `<CustomDataSignature>`.

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

Para instalar la plantilla, puede copiar la carpeta comprimida (archivo *.zip*) en la carpeta de plantillas de elemento de Visual Basic. De manera predeterminada, las plantillas de elemento de usuario se encuentran en *%USERPROFILE%\Documentos\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*. Como alternativa, puede encontrar la plantilla como un archivo del Instalador de Visual Studio ( *.vsi*).

## <a name="see-also"></a>Vea también

- [Extender el espacio de nombres My en Visual Basic](extending-the-my-namespace.md)
- [Extensión del modelo de la aplicación de Visual Basic](extending-the-visual-basic-application-model.md)
- [Personalización de los objetos que están disponibles en My](customizing-which-objects-are-available-in-my.md)
- [Página Mis extensiones del Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
