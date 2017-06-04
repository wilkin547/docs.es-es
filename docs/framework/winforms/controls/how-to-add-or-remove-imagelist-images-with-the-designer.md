---
title: "C&#243;mo: Agregar o quitar im&#225;genes del componente ImageList mediante el Dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ImageList (componente) [Windows Forms], agregar imágenes"
  - "ImageList (componente) [Windows Forms], quitar imágenes"
  - "imágenes [Windows Forms], agregar al componente ImageList"
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Agregar o quitar im&#225;genes del componente ImageList mediante el Dise&#241;ador
Puede agregar imágenes a un componente <xref:System.Windows.Forms.ImageList> de varias maneras distintas.  Puede agregar imágenes muy rápidamente utilizando la etiqueta inteligente asociada al componente <xref:System.Windows.Forms.ImageList> o si establece otras propiedades varias en <xref:System.Windows.Forms.ImageList>, quizá le resulte más cómodo agregar imágenes con la ventana Propiedades.  También puede agregar imágenes utilizando código.  Para obtener más información sobre cómo agregar imágenes con código, vea [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  Normalmente puede rellenar el componente <xref:System.Windows.Forms.ImageList> con imágenes antes de asociarlo a un control, pero esto no es necesario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar o quitar imágenes utilizando la ventana Propiedades  
  
1.  Seleccione el componente <xref:System.Windows.Forms.ImageList> o agregue uno al formulario.  
  
2.  En la ventana Propiedades, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.ImageList.Images%2A>.  
  
3.  En el **Editor de la colección de imágenes**, haga clic en **Agregar** o **Quitar** para agregar o quitar las imágenes de la lista.  
  
### Para agregar o quitar imágenes mediante la etiqueta inteligente  
  
1.  Seleccione el componente <xref:System.Windows.Forms.ImageList> o agregue uno al formulario.  
  
2.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\).  
  
3.  En el cuadro de diálogo **Tareas de ImageList**, seleccione **Elegir imágenes**.  
  
4.  En el **Editor de la colección de imágenes**, haga clic en **Agregar** o **Quitar** para agregar o quitar las imágenes de la lista.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)   
 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)