---
title: Empaquetar e implementar extensiones de My (Visual Basic) de personalizadas
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 901d0b80a18d2f4d262cc65eb485dcc628bc6a08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Empaquetar e implementar extensiones de My (Visual Basic) de personalizadas
Visual Basic proporciona una manera sencilla de implementar su personalizado `My` extensiones de espacio de nombres mediante el uso de plantillas de Visual Studio. Si va a crear una plantilla de proyecto para que su `My` las extensiones son una parte integral del nuevo tipo de proyecto, solo puede incluir su personalizado `My` código de extensión con el proyecto al exportar la plantilla. Para obtener más información acerca de cómo exportar plantillas de proyecto, vea [Cómo: crear plantillas de proyecto](/visualstudio/ide/how-to-create-project-templates).  
  
 Si su personalizado `My` extensión en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic. A continuación, puede personalizar la plantilla de elemento para habilitar características adicionales y el comportamiento para su personalizado `My` extensión en un proyecto de Visual Basic. Esas funciones incluyen lo siguiente:  
  
-   Lo que permite a los usuarios administrar su personalizado `My` extensión desde el **extensiones My** página del Diseñador de proyectos de Visual Basic.  
  
-   Agregar automáticamente personalizado `My` extensión cuando una referencia a un ensamblado especificado se agrega a un proyecto.  
  
-   Ocultar el `My` plantilla de elemento de extensión en la **Agregar elemento** cuadro de diálogo para que no se incluye en la lista de elementos de proyecto.  
  
 Este tema describe cómo empaquetar un personalizado `My` extensión como una plantilla de elemento oculto que se puede administrar desde el **extensiones My** página del Diseñador de proyectos de Visual Basic. Personalizado `My` extensión también se puede agregar automáticamente cuando se agrega una referencia a un ensamblado especificado para un proyecto.  
  
## <a name="create-a-my-namespace-extension"></a>Crear una extensión de espacio de nombres My  
 El primer paso para crear un paquete de implementación para un personalizado `My` extensión consiste en crear la extensión como un archivo de código único. Para obtener más información e instrucciones sobre cómo crear una personalizada `My` extensión, vea [extender el Namespace My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportar una extensión de espacio de nombres My como una plantilla de elementos  
 Una vez haya un archivo de código que incluye su `My` extensión del espacio de nombres, puede exportar el archivo de código como una plantilla de elemento de Visual Studio. Para obtener instrucciones sobre cómo exportar un archivo como una plantilla de elemento de Visual Studio, consulte [Cómo: crear plantillas de elementos](/visualstudio/ide/how-to-create-item-templates).  
  
> [!NOTE]
>  Si su `My` extensión de espacio de nombres tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente el `My` extensión de espacio de nombres cuando se agrega una referencia a dicho ensamblado. Como resultado, deberá excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elemento de Visual Studio.  
  
## <a name="customize-the-item-template"></a>Personalizar la plantilla de elemento  
 Puede habilitar la plantilla de elemento para administrarse desde la **extensiones My** página del Diseñador de proyectos de Visual Basic. También puede habilitar la plantilla de elemento que se agregará automáticamente cuando se agrega una referencia a un ensamblado especificado para un proyecto. Para habilitar estas personalizaciones, agregará un nuevo archivo, denominado archivo CustomData, a la plantilla y, a continuación, agregue un nuevo elemento al XML en el archivo .vstemplate.  
  
### <a name="add-the-customdata-file"></a>Agregue el archivo CustomData  
 El archivo CustomData es un archivo de texto que tiene una extensión de nombre de archivo. CustomData (el nombre de archivo puede establecerse en cualquier valor significativo para la plantilla) y que contiene XML. El código XML del archivo CustomData indica a Visual Basic que incluya la `My` extensión cuando los usuarios usen el **extensiones My** página del Diseñador de proyectos de Visual Basic. Puede agregar opcionalmente el <`AssemblyFullName>` atributo al archivo CustomData XML. Esto indica a Visual Basic para instalar automáticamente personalizado `My` extensión cuando una referencia a un ensamblado determinado se agrega al proyecto. Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, a continuación, agregarlo a la carpeta comprimida de la plantilla de elemento (archivo .zip).  
  
 Por ejemplo, el siguiente XML muestra el contenido de un archivo CustomData que agregará el elemento de plantilla en la carpeta Extensiones My de un proyecto de Visual Basic cuando una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.Vs.dll se agrega al proyecto.  
  
```xml  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 El archivo CustomData contiene un <`VBMyExtensionTemplate>` elemento que tiene atributos como se muestra en la tabla siguiente.  
  
|Atributo|Descripción|  
|---|---|  
|`ID`|Requerido. Un identificador único para la extensión. Si la extensión que tiene este identificador ya se ha agregado al proyecto, el usuario no le pedirá que vuelva a agregarlo.|  
|`Version`|Requerido. Un número de versión para la plantilla de elemento.|  
|`AssemblyFullName`|Opcional. Nombre de ensamblado. Cuando se agrega una referencia a este ensamblado al proyecto, se preguntará al usuario para agregar el `My` extensión desde esta plantilla de elemento.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Agregar el \<CustomDataSignature > elemento al archivo .vstemplate  
 Para identificar la plantilla de elementos de Visual Studio como un `My` extensión del espacio de nombres, también debe modificar el archivo .vstemplate de la plantilla de elemento. Debe agregar una `<CustomDataSignature>` elemento a la `<TemplateData>` elemento. El `<CustomDataSignature>` elemento debe contener el texto `Microsoft.VisualBasic.MyExtension`, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 No se puede modificar directamente los archivos en una carpeta comprimida (archivo .zip). Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, a continuación, reemplace el archivo .vstemplate en la carpeta comprimida con la copia actualizada.  
  
 En el ejemplo siguiente se muestra el contenido de un archivo .vstemplate que tiene el `<CustomDataSignature>` elemento agregado.  
  
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
  
## <a name="install-the-template"></a>Instalar la plantilla  
 Para instalar la plantilla, puede copiar la carpeta comprimida (archivo .zip) a la carpeta de plantillas de elementos de Visual Basic (por ejemplo, Mis documentos\Visual Studio 2008\Plantillas\Plantillas de elementos\Visual Basic). Como alternativa, puede publicar la plantilla como un archivo de instalador de Visual Studio (VSI).  
  
## <a name="see-also"></a>Vea también  
 [Extender el espacio de nombres My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Mi página de extensiones, Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
