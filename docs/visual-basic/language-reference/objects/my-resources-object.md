---
title: "My.Resources (Objeto) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.Resources"
  - "My.Resources.MyResources.ResourceManager"
  - "My.Resources.MyResources.Culture"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources (objeto)"
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# My.Resources (Objeto)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona propiedades y clases para obtener acceso a los recursos de la aplicación.  
  
## Comentarios  
 El objeto `My.Resources` proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de su aplicación.  Para obtener más información, vea [Administrar los recursos de la aplicación \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
 El objeto `My.Resources` expone sólo recursos globales.  No proporciona acceso a archivos de recursos asociados a formularios.  Debe tener acceso a los recursos de formulario de los formularios.  Para obtener más información, vea [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/es-es/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Puede tener acceso a los archivos de recursos específicos de referencia cultural de la aplicación desde el objeto `My.Resources`.  De manera predeterminada, el objeto `My.Resources` busca recursos en el archivo de recursos que coincide con la referencia cultural especificada en la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>.  Sin embargo, puede reemplazar este comportamiento y especificar una referencia cultural determinada para utilizarla con los recursos.  Para obtener más información, vea [Recursos de aplicaciones de escritorio](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Propiedades  
 Las propiedades del objeto `My.Resources` proporcionan acceso de sólo lectura a los recursos de su aplicación.  Para agregar o quitar recursos, utilice el **Diseñador de proyectos**.  Para obtener más información, vea [How to: Add or Remove Resources](http://msdn.microsoft.com/es-es/7b77bc06-3952-4799-b029-def3f8f7f88d).  Puede tener acceso a los recursos agregados a través del **Diseñador de proyectos** mediante `My.Resources.``resourceName`.  
  
 También, puede agregar o quitar archivos de recursos seleccionando el proyecto en el **Explorador de soluciones** y haciendo clic en **Agregar nuevo elemento** o **Agregar elemento existente** del menú **Proyecto**.  De esta forma, puede tener acceso a los recursos agregados mediante `My.Resources.``resourceFileName`.`resourceName`.  
  
 Cada recurso tiene un nombre, una categoría y un valor, y estos valores de recurso determinan cómo aparece en el objeto `My.Resources` la propiedad para tener acceso al recurso.  Para los recursos agregados en el **Diseñador de proyectos**:  
  
-   El nombre determina el nombre de la propiedad;  
  
-   Los datos de recursos son el valor de la propiedad;  
  
-   La categoría determina el tipo de la propiedad:  
  
|||  
|-|-|  
|Categoría|Tipo de datos de la propiedad|  
|**Cadenas**|[Cadena.](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Imágenes**|<xref:System.Drawing.Bitmap>|  
|**Iconos**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> La clase <xref:System.IO.UnmanagedMemoryStream> deriva de la clase <xref:System.IO.Stream>, por lo que se puede utilizar con métodos que toman secuencias, como el método <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>.|  
|**Files \(Archivos\)**|-   [Cadena](../../../visual-basic/language-reference/data-types/string-data-type.md) para los archivos de texto.<br />-   <xref:System.Drawing.Bitmap> para los archivos de imagen.<br />-   <xref:System.Drawing.Icon> para los archivos de icono.<br />-   <xref:System.IO.UnmanagedMemoryStream> para los archivos de sonido.|  
|**Otros**|Vienen determinados por la información contenida en la columna **Tipo** del diseñador.|  
  
## Clases  
 El objeto `My.Resources` expone cada archivo de recursos como una clase con propiedades compartidas.  El nombre de clase es el mismo que el nombre del archivo de recursos.  Como se explica en la sección anterior, los recursos contenidos en un archivo de recursos se exponen como propiedades de la clase.  
  
## Ejemplo  
 Este ejemplo establece el título de un formulario en el recurso de cadena denominado `Form1Title` en el archivo de recursos de la aplicación.  Para que el ejemplo funcione, la aplicación debe tener una cadena denominada `Form1Title` en el archivo de recursos.  Para obtener más información, vea [How to: Add or Remove Resources](http://msdn.microsoft.com/es-es/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#1)]  
  
## Ejemplo  
 Este ejemplo establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.  Para que el ejemplo funcione, la aplicación debe tener un icono denominado `Form1Icon` en el archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#2)]  
  
## Ejemplo  
 Este ejemplo establece la imagen de fondo de un formulario en el recurso de imagen denominado `Form1Background`, que está en el archivo de recursos de la aplicación.  Para que este ejemplo funcione, la aplicación debe tener un recurso de imagen denominado `Form1Background` en el archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#3)]  
  
## Ejemplo  
 Este ejemplo reproduce el sonido que se almacena como un recurso de sonido denominado `Form1Greeting` en el archivo de recursos de la aplicación.  Para que el ejemplo funcione, la aplicación debe tener un recurso de sonido denominado `Form1Greeting` en el archivo de recursos.  El método `My.Computer.Audio.Play` está disponible sólo para las aplicaciones de Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#4)]  
  
## Ejemplo  
 Este ejemplo recupera la versión de referencia cultural francesa de un recurso de cadena de la aplicación.  Se llama al recurso `Message`.  Para cambiar la referencia cultural que el objeto de `My.Resources` usa, el ejemplo utiliza <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Para que este ejemplo funcione, la aplicación debe tener una cadena denominada `Message` en el archivo de recursos, y debe tener la versión de referencia cultural francesa de ese archivo de recursos, Resources.fr\-FR.resx.  Para obtener más información, vea [How to: Add or Remove Resources](http://msdn.microsoft.com/es-es/7b77bc06-3952-4799-b029-def3f8f7f88d).  Si la aplicación no tiene la versión de referencia cultural francesa del archivo de recursos, el objeto de `My.Resource` recupera el recurso del archivo de recursos de referencia cultural predeterminado.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#10)]  
  
## Vea también  
 [How to: Add or Remove Resources](http://msdn.microsoft.com/es-es/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Administrar los recursos de la aplicación \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet)   
 [Recursos de aplicaciones de escritorio](../Topic/Resources%20in%20Desktop%20Apps.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/es-es/9a96220d-a19b-4de0-9f48-01e5d82679e5)