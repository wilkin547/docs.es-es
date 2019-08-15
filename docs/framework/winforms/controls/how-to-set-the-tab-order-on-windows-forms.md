---
title: Procedimiento para establecer el orden de tabulación en formularios Windows Forms
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
ms.openlocfilehash: 5559a3a3e4e62ce9e620de23feef3cbfa0ab8f60
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039855"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Procedimiento para establecer el orden de tabulación en formularios Windows Forms
El orden de tabulación es el orden en el que el usuario mueve el foco de un control a otro presionando la tecla TAB. Cada formulario tiene su propio orden de tabulación. De forma predeterminada, el orden de tabulación es el mismo que el orden en que se crearon los controles. La numeración del orden de tabulación empieza por cero.

## <a name="to-set-the-tab-order-of-a-control"></a>Para establecer el orden de tabulación de un control

1. En el menú **Ver** , haga clic en **orden**de tabulación.

     Esto activa el modo de selección de orden de tabulación en el formulario. Un número (que representa <xref:System.Windows.Forms.Control.TabIndex%2A> la propiedad) aparece en la esquina superior izquierda de cada control.

2. Haga clic en los controles secuencialmente para establecer el orden de tabulación que desee.

    > [!NOTE]
    >  El lugar de un control dentro del orden de tabulación se puede establecer en cualquier valor mayor o igual que 0. Cuando se producen duplicados, se evalúa el orden z de los dos controles y el control en la parte superior se tabula primero. (El orden z es el nivel visual de los controles en un formulario a lo largo del eje z del formulario [Depth]. El orden z determina qué controles están delante de otros controles). Para obtener más información sobre el orden z, vea [capas de objetos en Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Cuando haya terminado, haga clic en **orden** de tabulación en el menú **Ver** de nuevo para dejar el modo de orden de tabulación.

    > [!NOTE]
    >  Los controles que no pueden obtener el foco, así como los controles deshabilitados e invisibles, no tienen una <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad y no se incluyen en el orden de tabulación. Cuando el usuario presiona la tecla TAB, se omiten estos controles.

 Como alternativa, el orden de tabulación se puede establecer en el <xref:System.Windows.Forms.Control.TabIndex%2A> ventana propiedades mediante la propiedad. La <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de un control determina dónde se coloca en el orden de tabulación. De forma predeterminada, el primer control dibujado tiene <xref:System.Windows.Forms.Control.TabIndex%2A> un valor de 0, el segundo tiene <xref:System.Windows.Forms.Control.TabIndex%2A> un de 1, y así sucesivamente.

 Además, de forma predeterminada, <xref:System.Windows.Forms.GroupBox> un control tiene su <xref:System.Windows.Forms.Control.TabIndex%2A> propio valor, que es un número entero. Un <xref:System.Windows.Forms.GroupBox> control en sí no puede tener el foco en tiempo de ejecución. Por lo tanto, cada control <xref:System.Windows.Forms.GroupBox> dentro de tiene su <xref:System.Windows.Forms.Control.TabIndex%2A> propio valor decimal, empezando por. 0. Naturalmente, a medida <xref:System.Windows.Forms.Control.TabIndex%2A> que se <xref:System.Windows.Forms.GroupBox> incrementa el de un control, los controles que contiene se incrementarán en consecuencia. Si ha cambiado un <xref:System.Windows.Forms.Control.TabIndex%2A> valor de 5 a 6, el <xref:System.Windows.Forms.Control.TabIndex%2A> valor del primer control de su grupo cambia automáticamente a 6,0, y así sucesivamente.

 Por último, se puede omitir cualquier control de los muchos del formulario en el orden de tabulación. Normalmente, al presionar TAB sucesivamente en tiempo de ejecución, se selecciona cada control en el orden de tabulación. Al desactivar la <xref:System.Windows.Forms.Control.TabStop%2A> propiedad, puede hacer que se pase un control en el orden de tabulación del formulario.

## <a name="to-remove-a-control-from-the-tab-order"></a>Para quitar un control del orden de tabulación

1. Establezca la <xref:System.Windows.Forms.Control.TabStop%2A> `false` propiedad del control en en el ventana Propiedades.

     Un control cuya <xref:System.Windows.Forms.Control.TabStop%2A> propiedad se ha establecido en `false` todavía mantiene su posición en el orden de tabulación, aunque el control se omita al recorrer los controles con la tecla TAB.

    > [!NOTE]
    >  Un grupo de botones de radio tiene una sola tabulación en tiempo de ejecución. El botón seleccionado (es decir, el botón con su <xref:System.Windows.Forms.RadioButton.Checked%2A> propiedad establecida en `true`) tiene su <xref:System.Windows.Forms.Control.TabStop%2A> propiedad establecida automáticamente <xref:System.Windows.Forms.Control.TabStop%2A> en `true`, mientras que los demás botones tienen la propiedad establecida `false`en. Para obtener más información sobre la <xref:System.Windows.Forms.RadioButton> agrupación de controles, vea [agrupar Windows Forms controles RadioButton para que funcionen como un conjunto](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
