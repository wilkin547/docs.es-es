---
title: Empaquetar e implementar extensiones de My (Visual Basic) de personalizadas | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 950592c0fb197959ce1c3cf6128093846a022709
ms.lasthandoff: 03/13/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Empaquetar e implementar extensiones de My (Visual Basic) de personalizadas
Visual Basic proporciona una manera fácil de implementar personalizado `My` extensiones de espacio de nombres mediante el uso de plantillas de Visual Studio. Si está creando una plantilla de proyecto para que la `My` extensiones son una parte integrante del nuevo tipo de proyecto, simplemente puede incluir personalizado `My` código de extensión con el proyecto al exportar la plantilla. Para obtener más información acerca de cómo exportar plantillas de proyecto, vea [Cómo: crear plantillas de proyecto](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).  
  
 Si personalizado `My` extensión en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios pueden agregar a cualquier tipo de proyecto de Visual Basic. A continuación, puede personalizar la plantilla de elemento para habilitar funciones adicionales y el comportamiento de personalizado `My` extensión en un proyecto de Visual Basic. Esas capacidades son los siguientes:  
  
-   Permitir a los usuarios administrar personalizado `My` extensión desde el **extensiones My** página del Diseñador de proyectos de Visual Basic.  
  
-   Agregar automáticamente personalizado `My` extensión cuando una referencia a un ensamblado especificado se agrega a un proyecto.  
  
-   Ocultar el `My` plantilla de elemento de extensión en el **Agregar elemento** cuadro de diálogo no se incluye en la lista de elementos de proyecto.  
  
 En este tema se explica cómo empaquetar un personalizado `My` extensión como una plantilla de elemento oculto que se puede administrar desde el **extensiones My** página del Diseñador de proyectos de Visual Basic. Personalizado `My` extensión también se puede agregar automáticamente cuando se agrega una referencia a un ensamblado especificado para un proyecto.  
  
## <a name="create-a-my-namespace-extension"></a>Crear una extensión de espacio de nombres My  
 El primer paso para crear un paquete de implementación para un personalizado `My` extensión es crear la extensión como un archivo de código único. Para obtener más información y orientación sobre cómo crear una personalizada `My` extensión, consulte [extender el Namespace My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportar una extensión de espacio de nombres My como una plantilla de elemento  
 Una vez que un archivo de código que incluye su `My` extensión del espacio de nombres, puede exportar el archivo de código como una plantilla de elemento de Visual Studio. Para obtener instrucciones acerca de cómo exportar un archivo como una plantilla de elemento de Visual Studio, consulte [Cómo: crear plantillas de elementos](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).  
  
> [!NOTE]
>  Si su `My` extensión del espacio de nombres tiene una dependencia en un ensamblado determinado, puede personalizar la plantilla de elemento para instalar automáticamente el `My` extensión del espacio de nombres cuando se agrega una referencia a dicho ensamblado. Como resultado, deberá excluir esa referencia de ensamblado al exportar el archivo de código como una plantilla de elemento de Visual Studio.  
  
## <a name="customize-the-item-template"></a>Personalizar la plantilla de elemento  
 Puede habilitar la plantilla de elemento administrarse desde el **extensiones My** página del Diseñador de proyectos de Visual Basic. También puede habilitar la plantilla de elemento que se agreguen automáticamente cuando se agrega una referencia a un ensamblado especificado para un proyecto. Para habilitar estas personalizaciones, agregará un nuevo archivo, denominado CustomData, a la plantilla y, a continuación, agregue un nuevo elemento al XML en el archivo .vstemplate.  
  
### <a name="add-the-customdata-file"></a>Agregue el archivo CustomData  
 El archivo CustomData es un archivo de texto que tiene la extensión de nombre de archivo. CustomData (el nombre de archivo puede establecerse en cualquier valor significativo para la plantilla) y que contiene XML. El XML del archivo CustomData indica a Visual Basic que incluya la `My` extensión cuando los usuarios usen el **extensiones My** página del Diseñador de proyectos de Visual Basic. Opcionalmente, puede agregar el `AssemblyFullName>` atributo al archivo CustomData XML. Esto indica a Visual Basic para instalar automáticamente personalizado `My` extensión cuando una referencia a un ensamblado determinado se agrega al proyecto. Puede usar cualquier editor de texto o editor XML para crear el archivo CustomData y, a continuación, agregarlo a la carpeta comprimida (archivo .zip) de la plantilla elemento.  
  
 Por ejemplo, el siguiente XML muestra el contenido de un archivo CustomData que agregará el elemento de plantilla a la carpeta Extensiones My de un proyecto de Visual Basic cuando una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.Vs.dll se agrega al proyecto.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 El archivo CustomData contiene un `VBMyExtensionTemplate>` elemento que tiene atributos como se muestra en la tabla siguiente.  
  
|Atributo|Descripción|  
|---|---|  
|`ID`|Obligatorio. Un identificador único para la extensión. Si la extensión que tiene este identificador ya se ha agregado al proyecto, el usuario no le pedirá que vuelva a agregarlo.|  
|`Version`|Obligatorio. Un número de versión para la plantilla de elemento.|  
|`AssemblyFullName`|Opcional. Nombre de ensamblado. Cuando se agrega una referencia a este ensamblado al proyecto, se preguntará al usuario para agregar el `My` extensión desde esta plantilla de elemento.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Agregue el \<CustomDataSignature > elemento al archivo .vstemplate  
 Para identificar la plantilla de elemento de Visual Studio como un `My` extensión del espacio de nombres, también debe modificar el archivo .vstemplate de la plantilla de elemento. Debe agregar una `<CustomDataSignature>` elemento a la `<TemplateData>` elemento. El `<CustomDataSignature>` elemento debe contener el texto `Microsoft.VisualBasic.MyExtension`, como se muestra en el ejemplo siguiente.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 No puede modificar directamente los archivos en una carpeta comprimida (archivo .zip). Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, a continuación, reemplace el archivo .vstemplate en la carpeta comprimida por la copia actualizada.  
  
 En el ejemplo siguiente se muestra el contenido de un archivo .vstemplate que tiene el `<CustomDataSignature>` elemento agregado.  
  
```  
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
 Para instalar la plantilla, puede copiar la carpeta comprimida (archivo .zip) a la carpeta de plantillas de elementos de Visual Basic (por ejemplo, Mis documentos\Visual Studio 2008\Plantillas\Plantillas Templates\Visual básica). Como alternativa, puede publicar la plantilla como un archivo de instalador de Visual Studio (.vsi).  
  
## <a name="see-also"></a>Vea también  
 [Extender el My Namespace en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Ampliar el modelo de aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Mi página de extensiones, Diseñador de proyectos](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
