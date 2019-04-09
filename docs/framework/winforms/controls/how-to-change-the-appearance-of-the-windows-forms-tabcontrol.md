---
title: Filtrar para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: c84ce67225b70933e65b8f88da1eaef6b1f3de99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133138"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Filtrar para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms
Puede cambiar la apariencia de fichas en Windows Forms mediante el uso de las propiedades de la <xref:System.Windows.Forms.TabControl> y <xref:System.Windows.Forms.TabPage> objetos que componen las fichas individuales en el control. Al establecer estas propiedades, puede mostrar imágenes en las fichas, mostrar pestañas verticalmente en lugar de horizontalmente, mostrar varias filas de pestañas y habilitar o deshabilitar las fichas mediante programación.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Para mostrar un icono en la parte de una pestaña de etiqueta  
  
1.  Agregar un <xref:System.Windows.Forms.ImageList> control al formulario.  
  
2.  Agregar imágenes a la lista de imágenes.  
  
     Para obtener más información acerca de las listas de imágenes, consulte [componente ImageList](imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Establecer el <xref:System.Windows.Forms.TabControl.ImageList%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a la <xref:System.Windows.Forms.ImageList> control.  
  
4.  Establecer el <xref:System.Windows.Forms.TabPage.ImageIndex%2A> propiedad de la <xref:System.Windows.Forms.TabPage> al índice de una imagen adecuada en la lista.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Para crear varias filas de pestañas  
  
1.  Agregue el número de páginas de ficha que desee.  
  
2.  Establecer el <xref:System.Windows.Forms.TabControl.Multiline%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a `true`.  
  
3.  Si las fichas no aparecen ya en varias filas, establezca el <xref:System.Windows.Forms.Control.Width%2A> propiedad de la <xref:System.Windows.Forms.TabControl> sea más estrechas que todas las fichas.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Para organizar las fichas en el lado del control  
  
-   Establecer el <xref:System.Windows.Forms.TabControl.Alignment%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Para habilitar o deshabilitar todos los controles en una ficha mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.TabPage.Enabled%2A> propiedad de la <xref:System.Windows.Forms.TabPage> a `true` o `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Para mostrar fichas como botones  
  
-   Establecer el <xref:System.Windows.Forms.TabControl.Appearance%2A> propiedad de la <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Vea también

- [TabControl (Control)](tabcontrol-control-windows-forms.md)
- [Información general sobre el control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Filtrar para agregar un control a una ficha](how-to-add-a-control-to-a-tab-page.md)
- [Filtrar para deshabilitar fichas](how-to-disable-tab-pages.md)
- [Filtrar para agregar y quitar fichas con el control TabControl de formularios Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
