---
title: Establecer el orden de tabulación de los controles
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d53e411bda0279271e4f73e1842c52fd6d9b3a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746832"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Cómo: establecer el orden de tabulación en Windows Forms

El orden de tabulación es el orden en el que el usuario mueve el foco de un control a otro presionando la tecla TAB. Cada formulario tiene su propio orden de tabulación. De forma predeterminada, el orden de tabulación es el mismo que el orden en que se crearon los controles. La numeración del orden de tabulación empieza por cero.

## <a name="to-set-the-tab-order-of-a-control"></a>Para establecer el orden de tabulación de un control

1. En Visual Studio, en el menú **Ver** , seleccione **orden de tabulación**.

   Esto activa el modo de selección de orden de tabulación en el formulario. Aparece un número (que representa la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>) en la esquina superior izquierda de cada control.

2. Haga clic en los controles secuencialmente para establecer el orden de tabulación que desee.

   > [!NOTE]
   > El lugar de un control dentro del orden de tabulación se puede establecer en cualquier valor mayor o igual que 0. Cuando se producen duplicados, se evalúa el orden z de los dos controles y el control en la parte superior se tabula primero. (El orden z es el nivel visual de los controles en un formulario a lo largo del eje z del formulario [Depth]. El orden z determina qué controles están delante de otros controles). Para obtener más información sobre el orden z, vea [capas de objetos en Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Cuando haya terminado, seleccione el **orden de tabulación** en el menú **Ver** de nuevo para dejar el modo de orden de tabulación.

   > [!NOTE]
   > Los controles que no pueden obtener el foco, así como los controles deshabilitados e invisibles, no tienen una propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> y no se incluyen en el orden de tabulación. Cuando el usuario presiona la tecla Tab, se omiten estos controles.

Como alternativa, el orden de tabulación se puede establecer en el ventana Propiedades mediante la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>. La propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> de un control determina dónde se coloca en el orden de tabulación. De forma predeterminada, el primer control dibujado tiene un valor <xref:System.Windows.Forms.Control.TabIndex%2A> de 0, el segundo tiene un <xref:System.Windows.Forms.Control.TabIndex%2A> de 1, y así sucesivamente.

Además, de forma predeterminada, un control <xref:System.Windows.Forms.GroupBox> tiene su propio valor <xref:System.Windows.Forms.Control.TabIndex%2A>, que es un número entero. Un control de <xref:System.Windows.Forms.GroupBox> en sí no puede tener el foco en tiempo de ejecución. Por lo tanto, cada control dentro de un <xref:System.Windows.Forms.GroupBox> tiene su propio valor decimal <xref:System.Windows.Forms.Control.TabIndex%2A>, empezando por. 0. Naturalmente, a medida que se incrementa el <xref:System.Windows.Forms.Control.TabIndex%2A> de un control <xref:System.Windows.Forms.GroupBox>, los controles que contiene se incrementarán en consecuencia. Si ha cambiado un valor de <xref:System.Windows.Forms.Control.TabIndex%2A> de 5 a 6, el valor <xref:System.Windows.Forms.Control.TabIndex%2A> del primer control de su grupo cambia automáticamente a 6,0, y así sucesivamente.

Por último, se puede omitir cualquier control de los muchos del formulario en el orden de tabulación. Normalmente, al presionar Tab sucesivamente en tiempo de ejecución, se selecciona cada control en el orden de tabulación. Al desactivar la propiedad <xref:System.Windows.Forms.Control.TabStop%2A>, puede hacer que se pase un control en el orden de tabulación del formulario.

## <a name="to-remove-a-control-from-the-tab-order"></a>Para quitar un control del orden de tabulación

Establezca la propiedad <xref:System.Windows.Forms.Control.TabStop%2A> del control en **false** en la ventana **propiedades** .

Control cuya propiedad <xref:System.Windows.Forms.Control.TabStop%2A> se ha establecido en `false` mantiene su posición en el orden de tabulación, aunque el control se omita al recorrer los controles con la tecla TAB.

> [!NOTE]
> Un grupo de botones de radio tiene una sola tabulación en tiempo de ejecución. El botón seleccionado (es decir, el botón con su propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A> establecida en `true`) tiene su propiedad <xref:System.Windows.Forms.Control.TabStop%2A> establecida automáticamente en `true`, mientras que los demás botones tienen la propiedad <xref:System.Windows.Forms.Control.TabStop%2A> establecida en `false`. Para obtener más información sobre la agrupación de controles de <xref:System.Windows.Forms.RadioButton>, vea [agrupar Windows Forms controles RadioButton para que funcionen como un conjunto](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
