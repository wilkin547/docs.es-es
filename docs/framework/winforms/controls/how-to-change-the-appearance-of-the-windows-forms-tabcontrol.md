---
title: "C&#243;mo: Cambiar la apariencia del control TabControl de formularios Windows Forms | Microsoft Docs"
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
  - "botones, mostrar fichas como"
  - "iconos, mostrar en fichas"
  - "TabControl (control) [Windows Forms], cambiar la apariencia de la página"
  - "pestañas, controlar la apariencia"
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Cambiar la apariencia del control TabControl de formularios Windows Forms
Puede cambiar la apariencia de fichas de formularios Windows Forms utilizando propiedades del control <xref:System.Windows.Forms.TabControl> y los objetos <xref:System.Windows.Forms.TabPage> que constituyen las fichas individuales en el control.  Al establecer estas propiedades, podrá mostrar imágenes en las fichas, mostrar fichas en posición vertical en lugar de hacerlo en horizontal, mostrar varias filas de fichas y habilitar o deshabilitar las fichas mediante programación.  
  
### Para mostrar un icono en la parte de etiqueta de una ficha  
  
1.  Agregue un control <xref:System.Windows.Forms.ImageList> al formulario.  
  
2.  Agregue imágenes a la lista de imágenes.  
  
     Para obtener más información sobre las listas de imágenes, vea [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.ImageList%2A> del <xref:System.Windows.Forms.TabControl> en el control <xref:System.Windows.Forms.ImageList>.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.TabPage.ImageIndex%2A> del objeto <xref:System.Windows.Forms.TabPage> en el índice de una imagen adecuada de la lista.  
  
### Para crear varias filas de fichas  
  
1.  Agregue el número de páginas de fichas que desea.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.Multiline%2A> del control <xref:System.Windows.Forms.TabControl> en `true`.  
  
3.  Si las fichas no aparecen ya en varias filas, establezca la propiedad <xref:System.Windows.Forms.Control.Width%2A> del control <xref:System.Windows.Forms.TabControl> para que sea más estrecha que el total de las fichas.  
  
### Para organizar las fichas a un lado del control  
  
-   Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> del control <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAlignment> o <xref:System.Windows.Forms.TabAlignment>.  
  
### Habilitar o deshabilitar mediante programación todos los controles de una pestaña  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TabPage.Enabled%2A> del control <xref:System.Windows.Forms.TabPage> en `true` o `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### Para mostrar las fichas en forma de botones  
  
-   Establezca la propiedad <xref:System.Windows.Forms.TabControl.Appearance%2A> del control <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAppearance> o <xref:System.Windows.Forms.TabAppearance>.  
  
## Vea también  
 [TabControl \(Control\)](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Cómo: Agregar un control a una página de fichas](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Cómo: Deshabilitar páginas de ficha](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Cómo: Agregar y quitar fichas con el control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)