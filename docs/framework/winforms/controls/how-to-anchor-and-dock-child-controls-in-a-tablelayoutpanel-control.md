---
title: 'Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cb27454582dd4f3b299893c13b1202b33d9cacb9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a>Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel
El control <xref:System.Windows.Forms.TableLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a>Para alinear un control secundario en una celda de TableLayoutPanel  
  
1.  Cree un control <xref:System.Windows.Forms.TableLayoutPanel> en el formulario.  
  
2.  Establezca el valor de la <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> propiedades **1**.  
  
3.  Cree un control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.TableLayoutPanel>. El <xref:System.Windows.Forms.Button> ocupa la esquina superior izquierda de la celda.  
  
4.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Left`. El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.  
  
    > [!NOTE]
    >  Este comportamiento difiere del comportamiento de otros controles contenedor. En otros controles contenedor, el control secundario no mueve cuando se establece la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> y la distancia entre el control delimitado y el límite del contenedor primario se fija en el momento de establecer la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
5.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Left`. El control <xref:System.Windows.Forms.Button> se mueve para ocupar la esquina superior izquierda de la celda.  
  
6.  Repita el paso 5 con un valor de `Top, Right` para mover el <xref:System.Windows.Forms.Button> control a la esquina superior derecha de la celda. Repita con los valores de `Bottom, Left` e `Bottom, Right`.  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a>Para ajustar un control secundario en una celda de TableLayoutPanel  
  
1.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Left, Right`. El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al ancho de la celda.  
  
    > [!NOTE]
    >  Este comportamiento difiere del comportamiento de otros controles contenedor. En otros controles contenedor, el control secundario no cambia de tamaño cuando el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad está establecida en `Left, Right` o `Top, Bottom`.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Bottom`. El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al alto de la celda.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Bottom, Left, Right`. El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.  
  
4.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `None`. El control <xref:System.Windows.Forms.Button> cambia de tamaño y se centra en la celda.  
  
5.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle.Left>. El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda. El control <xref:System.Windows.Forms.Button> conserva el ancho, pero el alto cambia para rellenar la celda verticalmente.  
  
    > [!NOTE]
    >  Este es el mismo comportamiento que se produce en otros controles del contenedor.  
  
6.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle.Fill>. El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.  
  
## <a name="example"></a>Ejemplo  
 La ilustración siguiente muestra cinco botones delimitados en cinco celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")  
  
 En la siguiente ilustración se muestran cuatro botones delimitados en las esquinas de cuatro celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")  
  
 En la ilustración siguiente se muestran tres botones estirados por delimitación en tres celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")  
  
 En el ejemplo de código siguiente se muestran todas las combinaciones de los valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
