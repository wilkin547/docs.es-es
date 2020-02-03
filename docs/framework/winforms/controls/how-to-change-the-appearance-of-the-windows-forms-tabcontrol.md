---
title: Cambiar la apariencia de TabControl
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
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746614"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Cómo: Cambiar la apariencia del control TabControl de Windows Forms
Puede cambiar la apariencia de las pestañas en Windows Forms mediante las propiedades de los <xref:System.Windows.Forms.TabControl> y los objetos <xref:System.Windows.Forms.TabPage> que componen las pestañas individuales en el control. Al establecer estas propiedades, puede mostrar imágenes en las pestañas, mostrar las pestañas verticalmente en lugar de hacerlo horizontalmente, mostrar varias filas de pestañas y habilitar o deshabilitar las fichas mediante programación.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Para mostrar un icono en la parte de etiqueta de una pestaña  
  
1. Agregue un control <xref:System.Windows.Forms.ImageList> al formulario.  
  
2. Agregue imágenes a la lista de imágenes.  
  
     Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3. Establezca la propiedad <xref:System.Windows.Forms.TabControl.ImageList%2A> del <xref:System.Windows.Forms.TabControl> en el control <xref:System.Windows.Forms.ImageList>.  
  
4. Establezca la propiedad <xref:System.Windows.Forms.TabPage.ImageIndex%2A> del <xref:System.Windows.Forms.TabPage> en el índice de una imagen adecuada de la lista.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Para crear varias filas de pestañas  
  
1. Agregue el número de páginas de fichas que desee.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.TabControl.Multiline%2A> de la <xref:System.Windows.Forms.TabControl> en `true`.  
  
3. Si las pestañas no aparecen en varias filas, establezca la propiedad <xref:System.Windows.Forms.Control.Width%2A> del <xref:System.Windows.Forms.TabControl> para que sea más estrecha que todas las pestañas.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Para organizar las pestañas en el lateral del control  
  
- Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> de la <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Para habilitar o deshabilitar todos los controles en una pestaña mediante programación  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TabPage.Enabled%2A> de la <xref:System.Windows.Forms.TabPage> en `true` o `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Para mostrar las pestañas como botones  
  
- Establezca la propiedad <xref:System.Windows.Forms.TabControl.Appearance%2A> de la <xref:System.Windows.Forms.TabControl> en <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Consulte también

- [TabControl (control)](tabcontrol-control-windows-forms.md)
- [Información general del control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Agregar un control a una página de fichas](how-to-add-a-control-to-a-tab-page.md)
- [Deshabilitar páginas de ficha](how-to-disable-tab-pages.md)
- [Agregar y quitar fichas con el control TabControl de Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
