---
title: "C&#243;mo: Alinear y expandir un control en un control TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], alinear"
  - "controles [Windows Forms], expandir"
  - "TableLayoutPanel (control) [Windows Forms], expandir controles"
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Alinear y expandir un control en un control TableLayoutPanel
Puede alinear y ajustar controles en un control <xref:System.Windows.Forms.TableLayoutPanel> mediante las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para alinear y ajustar un control  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** a la celda superior izquierda del control <xref:System.Windows.Forms.TableLayoutPanel>.  El control <xref:System.Windows.Forms.Button> está centrado en la celda.  
  
3.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en `Izquierda,Derecha`.  El control <xref:System.Windows.Forms.Button> se estira para ajustarse al ancho de la celda.  
  
4.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en `Superior,Inferior`.  El control <xref:System.Windows.Forms.Button> se estira para ajustarse al alto de la celda.  
  
5.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> en <xref:System.Windows.Forms.DockStyle>.  El control <xref:System.Windows.Forms.Button> se expande para rellenar la celda.  
  
6.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> en <xref:System.Windows.Forms.DockStyle>.  El control <xref:System.Windows.Forms.Button> vuelve a su tamaño original y se mueve a la esquina superior izquierda de la celda.  El **Diseñador de Windows Forms** ha establecido la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> en `Superior, Izquierda`.  
  
7.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en `Inferior,Derecha`.  El control <xref:System.Windows.Forms.Button> se mueve a la esquina inferior derecha de la celda.  
  
8.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en <xref:System.Windows.Forms.AnchorStyles>.  El control <xref:System.Windows.Forms.Button> se mueve al centro de la celda.  
  
## Vea también  
 [TableLayoutPanel \(Control\)](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)