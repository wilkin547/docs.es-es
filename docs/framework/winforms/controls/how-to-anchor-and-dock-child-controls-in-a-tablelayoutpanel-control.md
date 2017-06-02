---
title: "C&#243;mo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles secundarios, delimitar y acoplar"
  - "controles [Windows Forms], secundarios"
  - "diseño [Windows Forms], controles secundarios"
  - "TableLayoutPanel (control) [Windows Forms], controles secundarios"
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel
El control <xref:System.Windows.Forms.TableLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.  
  
### Para alinear un control secundario en una celda de TableLayoutPanel  
  
1.  Cree un control <xref:System.Windows.Forms.TableLayoutPanel> en el formulario.  
  
2.  Establezca en 1 el valor de las propiedades <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Cree un control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.TableLayoutPanel>.  El <xref:System.Windows.Forms.Button> ocupa la esquina superior izquierda de la celda.  
  
4.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Izquierda`.  El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.  
  
    > [!NOTE]
    >  Este comportamiento difiere del comportamiento de otros controles contenedor.  En otros controles contenedor, el control secundario no mueve cuando se establece la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> y la distancia entre el control delimitado y el límite del contenedor primario se fija en el momento de establecer la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
5.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Superior, Izquierda`.  El control <xref:System.Windows.Forms.Button> se mueve para ocupar la esquina superior izquierda de la celda.  
  
6.  Repita el paso 5 con un valor `Superior, Derecha` para mover el control <xref:System.Windows.Forms.Button> a la esquina superior derecha de la celda.  Repita con los valores de `Inferior, Izquierda` e `Inferior, derecha`.  
  
### Para ajustar un control secundario en una celda de TableLayoutPanel  
  
1.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Izquierda, Derecha`.  El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al ancho de la celda.  
  
    > [!NOTE]
    >  Este comportamiento difiere del comportamiento de otros controles contenedor.  En otros controles del contenedor, el control secundario no cambia de tamaño cuando la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> se establece en `Izquierda, Derecha` o `Superior, Inferior`.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Superior, Inferior`.  El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al alto de la celda.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Superior, Inferior, Izquierda, Derecha`.  El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.  
  
4.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Ninguno`.  El control <xref:System.Windows.Forms.Button> cambia de tamaño y se centra en la celda.  
  
5.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle>.  El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.  El control <xref:System.Windows.Forms.Button> conserva el ancho, pero el alto cambia para rellenar la celda verticalmente.  
  
    > [!NOTE]
    >  Este es el mismo comportamiento que se produce en otros controles del contenedor.  
  
6.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle>.  El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.  
  
## Ejemplo  
 La ilustración siguiente muestra cinco botones delimitados en cinco celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.png "VS\_TLPanchor")  
  
 En la siguiente ilustración se muestran cuatro botones delimitados en las esquinas de cuatro celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.png "VS\_TLPanchor2")  
  
 En la ilustración siguiente se muestran tres botones estirados por delimitación en tres celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS\_TLPAnchor3")  
  
 En el ejemplo de código siguiente se muestran todas las combinaciones de los valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [TableLayoutPanel \(Control\)](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)