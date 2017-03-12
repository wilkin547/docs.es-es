---
title: "Empaquetar e implementar extensiones de My personalizadas (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My (espacio de nombres)"
  - "My (espacio de nombres), personalizar"
  - "My (espacio de nombres), extender"
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Empaquetar e implementar extensiones de My personalizadas (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic proporciona un método sencillo para implementar las extensiones de espacio de nombres `My` personalizadas mediante plantillas de Visual Studio.  Si crea una plantilla de proyecto cuyas extensiones `My` forman parte integrante del nuevo tipo de proyecto, simplemente puede incluir el código de extensión `My` personalizado con el proyecto al exportar la plantilla.  Para obtener más información sobre cómo exportar plantillas de proyecto, vea [Cómo: Crear plantillas de proyectos](../Topic/How%20to:%20Create%20Project%20Templates.md).  
  
 Si la extensión `My` personalizada está en un solo archivo de código, puede exportar el archivo como una plantilla de elementos que los usuarios puedan agregar a cualquier tipo de proyecto de Visual Basic.  A continuación, puede personalizar la plantilla de elementos para habilitar las funciones y comportamientos adicionales de la extensión `My` personalizada en un proyecto de Visual Basic.  Esas funciones incluyen lo siguiente:  
  
-   Permitir a los usuarios administrar la extensión `My` personalizada desde la página **Extensiones My** del Diseñador de proyectos de Visual Basic.  
  
-   Agregar automáticamente la extensión `My` personalizada cuando se agrega a un proyecto una referencia a un ensamblado específico.  
  
-   Ocultar la plantilla de elementos de extensión `My` en el cuadro de diálogo **Agregar elemento** para que no se incluya en la lista de elementos del proyecto.  
  
 En este tema se describe cómo empaquetar una extensión `My` personalizada como una plantilla de elementos oculta que se puede administrar desde la página **Extensiones My** del Diseñador de proyectos de Visual Basic.  La extensión `My` personalizada también se puede agregar automáticamente cuando se agrega a un proyecto una referencia a un ensamblado específico.  
  
## Crear una extensión de espacio de nombres My  
 El primer paso para crear un paquete de implementación para una extensión `My` personalizada es crear la extensión como un archivo de código único.  Para obtener información detallada e instrucciones sobre cómo crear una extensión `My` personalizada, vea [Extender el espacio de nombres My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## Exportar una extensión de espacio de nombres My como plantilla de elementos  
 Cuando disponga de un archivo de código que incluye la extensión de espacio de nombres `My`, puede exportar el archivo de código como plantilla de elementos de Visual Studio.  Para obtener instrucciones sobre cómo exportar un archivo como plantilla de elementos de Visual Studio, vea [Cómo: Crear plantillas de elementos](../Topic/How%20to:%20Create%20Item%20Templates.md).  
  
> [!NOTE]
>  Si la extensión de espacio de nombres `My` depende de un ensamblado determinado, la plantilla de elementos puede personalizarse para que instale automáticamente la extensión de espacio de nombres `My` cuando se agregue una referencia a ese ensamblado.  En consecuencia, es conveniente excluir esa referencia de ensamblado al exportar el archivo de código como plantilla de elementos de Visual Studio.  
  
## Personalizar la plantilla de elementos  
 Puede habilitar la administración de la plantilla de elementos desde la página **Extensiones My** del Diseñador de proyectos de Visual Basic.  También puede permitir que la plantilla de elementos se agregue automáticamente cuando se agrega a un proyecto una referencia a un ensamblado específico.  Para habilitar estas personalizaciones, debe agregar un nuevo archivo, denominado CustomData, a la plantilla y, a continuación, agregar un nuevo elemento al XML en el archivo .vstemplate.  
  
### Agregar el archivo CustomData  
 El archivo CustomData es un archivo de texto que tiene una extensión de nombre de archivo .CustomData \(el nombre de archivo puede establecerse como cualquier valor significativo para la plantilla\) y contiene XML.  El XML del archivo CustomData indica a Visual Basic que incluya la extensión `My` cuando los usuarios usen la página **Extensiones My** del Diseñador de proyectos de Visual Basic.  Opcionalmente, puede agregar el atributo \<`AssemblyFullName>` al archivo CustomData XML.  Esto indica a Visual Basic que instale automáticamente la extensión `My` personalizada cuando se agrega al proyecto una referencia a un ensamblado determinado.  Puede usar cualquier editor de texto o editor de XML para crear el archivo CustomData y, a continuación, agregarlo a la carpeta comprimida de la plantilla de elementos \(archivo .zip\).  
  
 Por ejemplo, el XML siguiente muestra el contenido de un archivo CustomData que agregará el elemento de plantilla a la carpeta Extensiones My de un proyecto de Visual Basic cuando se agregue al proyecto una referencia al ensamblado Microsoft.VisualBasic.PowerPacks.Vs.dll.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 El archivo CustomData contiene un elemento `VBMyExtensionTemplate>` que tiene los atributos mostrados en la tabla siguiente.  
  
|||  
|-|-|  
|Atributo|Descripción|  
|`ID`|Obligatorio.  Identificador único para la extensión.  Si la extensión que tiene este Id. ya se ha agregado al proyecto, no se solicitará al usuario que la vuelva a agregar.|  
|`Version`|Obligatorio.  Número de versión para la plantilla de elementos.|  
|`AssemblyFullName`|Opcional.  Nombre de ensamblado.  Cuando se agrega al proyecto una referencia a este ensamblado, se solicitará al usuario que agregue la extensión `My` de esta plantilla de elementos.|  
  
### Agregar el elemento \<CustomDataSignature\> al archivo .vstemplate  
 Para identificar la plantilla de elementos de Visual Studio como una extensión de espacio de nombres `My`, debe también modificar el archivo .vstemplate correspondiente a la plantilla de elementos.  Debe agregar un elemento `<CustomDataSignature>` al elemento `<TemplateData>`.  El elemento `<CustomDataSignature>` debe contener el texto `Microsoft.VisualBasic.MyExtension`, como se muestra en el ejemplo siguiente.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 No puede modificar directamente los archivos en una carpeta comprimida \(archivo .zip\).  Debe copiar el archivo .vstemplate de la carpeta comprimida, modificarlo y, a continuación, reemplazar el archivo .vstemplate de la carpeta comprimida por la copia actualizada.  
  
 En el ejemplo siguiente se muestra el contenido de un archivo .vstemplate al que se ha agregado el elemento `<CustomDataSignature>`.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature       >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
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
  
## Instalar la plantilla  
 Para instalar la plantilla, puede copiar la carpeta comprimida \(archivo .zip\) en la carpeta de plantillas de elementos de Visual Basic \(por ejemplo, Mis documentos\\Visual Studio 2008\\Plantillas\\Plantillas de elementos\\Visual Basic\).  Alternativamente, puede publicar la plantilla como un archivo Visual Studio Installer \(.vsi\).  Para obtener información sobre cómo publicar la plantilla como un archivo de Visual Studio Installer, vea [NIB: How to: Publish Project Templates](http://msdn.microsoft.com/es-es/b9087f58-64e9-4767-bf54-e3bf40d63b20).  
  
## Vea también  
 [Extender el espacio de nombres My en Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Ampliar el modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Extensiones My \(página del Diseñador de proyectos\)](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)