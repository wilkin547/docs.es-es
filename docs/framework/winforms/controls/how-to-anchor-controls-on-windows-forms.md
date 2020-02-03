---
title: para controles de anclado
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747179"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Cómo: delimitar controles en Windows Forms

Si está diseñando un formulario que el usuario puede cambiar de tamaño en tiempo de ejecución, los controles del formulario deben cambiar de tamaño y de posición correctamente. Para cambiar el tamaño de los controles dinámicamente con el formulario, puede usar la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> de los controles de Windows Forms. La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> define una posición de delimitador para el control. Cuando un control se delimita en un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de delimitador. Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> que está anclado a los bordes izquierdo, derecho e inferior del formulario, a medida que se cambia el tamaño del formulario, el control <xref:System.Windows.Forms.TextBox> cambia de tamaño horizontalmente para mantener la misma distancia desde los lados derecho e izquierdo del formulario. Además, el control se coloca verticalmente de forma que su ubicación siempre sea la misma distancia del borde inferior del formulario. Si un control no está delimitado y se cambia el tamaño del formulario, se cambia la posición del control con respecto a los bordes del formulario.

La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Delimitar un control en un formulario

1. En Visual Studio, seleccione el control que quiere delimitar.

    > [!NOTE]
    > Para delimitar varios controles simultáneamente, presione la tecla CTRL, haga clic en cada control para seleccionarlo y, a continuación, siga el resto de este procedimiento.

2. En la ventana **propiedades** , haga clic en la flecha situada a la derecha de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.

     Se muestra un editor que muestra una cruz.

3. Para establecer un delimitador, haga clic en la sección superior, izquierda, derecha o inferior de la Cruz.

     Los controles se delimitan a la parte superior e izquierda de forma predeterminada.

4. Para borrar un lado del control que se ha anclado, haga clic en ese brazo de la Cruz.

5. Para cerrar el editor de propiedades de <xref:System.Windows.Forms.Control.Anchor%2A>, vuelva a hacer clic en el nombre de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.

Cuando se muestra el formulario en tiempo de ejecución, el control cambia de tamaño para permanecer colocado a la misma distancia del borde del formulario. La distancia desde el borde delimitado siempre permanece igual que la distancia definida cuando el control se coloca en el Diseñador de Windows Forms.

> [!NOTE]
> Algunos controles, como el control <xref:System.Windows.Forms.ComboBox>, tienen un límite de alto. Al delimitar el control a la parte inferior de su formulario o contenedor no se puede forzar que el control supere su límite de alto.

Los controles heredados deben estar `Protected` para poder ser delimitados. Para cambiar el nivel de acceso de un control, establezca su propiedad `Modifiers` en la ventana **propiedades** .

## <a name="see-also"></a>Consulte también

- [Controles de Windows Forms](index.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Procedimiento para acoplar controles en formularios Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
