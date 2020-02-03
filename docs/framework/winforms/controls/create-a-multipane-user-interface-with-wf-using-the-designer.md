---
title: Crear una interfaz de usuario MULTIPANEL mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 6b41d538f1cd1633cec51c89e27adf3c5b47f9a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737276"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Diseñador
En el procedimiento siguiente, creará una interfaz de usuario de varios paneles similar a la usada en Microsoft Outlook, con una lista de **carpetas** , un panel **mensajes** y un panel de **vista previa** . Esta disposición se logra principalmente a través de los controles de acoplamiento con el formato.

 Al acoplar un control, se determina en qué borde del contenedor primario está fijado un control. Por lo tanto, si establece la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Right>, el borde derecho del control se acoplará al borde derecho de su control principal. Además, el borde acoplado del control cambia de tamaño para coincidir con el de su control contenedor. Para obtener más información sobre cómo funciona la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A>, vea [Cómo: acoplar controles en Windows Forms](how-to-dock-controls-on-windows-forms.md).

 Este procedimiento se centra en organizar el <xref:System.Windows.Forms.SplitContainer> y los demás controles del formulario, no en agregar funcionalidad para que la aplicación imite Microsoft Outlook.

 Para crear esta interfaz de usuario, coloque todos los controles dentro de un control <xref:System.Windows.Forms.SplitContainer>, que contiene un control <xref:System.Windows.Forms.TreeView> en el panel izquierdo. El panel derecho del control <xref:System.Windows.Forms.SplitContainer> contiene un segundo control <xref:System.Windows.Forms.SplitContainer> con un control <xref:System.Windows.Forms.ListView> sobre un control <xref:System.Windows.Forms.RichTextBox>. Estos controles de <xref:System.Windows.Forms.SplitContainer> habilitan el cambio de tamaño independiente de los demás controles del formulario. Puede adaptar las técnicas de este procedimiento para crear interfaces de usuario personalizadas propias.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Para crear una interfaz de usuario de estilo Outlook en tiempo de diseño

1. Cree un nuevo proyecto de aplicación para Windows (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación** > de **escritorio clásico** ).

2. Arrastre un control <xref:System.Windows.Forms.SplitContainer> desde el **cuadro de herramientas** al formulario. En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

3. Arrastre un control <xref:System.Windows.Forms.TreeView> desde el **cuadro de herramientas** al panel izquierdo del control <xref:System.Windows.Forms.SplitContainer>. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Left>; para ello, haga clic en el panel izquierdo del editor de valores que se muestra al hacer clic en la flecha hacia abajo.

4. Arrastre otro control <xref:System.Windows.Forms.SplitContainer> desde el **cuadro de herramientas**; colóquelo en el panel derecho del control <xref:System.Windows.Forms.SplitContainer> que ha agregado al formulario. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill> y la propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> en <xref:System.Windows.Forms.Orientation.Horizontal>.

5. Arrastre un control <xref:System.Windows.Forms.ListView> desde el **cuadro de herramientas** al panel superior del segundo control <xref:System.Windows.Forms.SplitContainer> que ha agregado al formulario. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.ListView> en <xref:System.Windows.Forms.DockStyle.Fill>.

6. Arrastre un control <xref:System.Windows.Forms.RichTextBox> desde el **cuadro de herramientas** hasta el panel inferior del segundo control <xref:System.Windows.Forms.SplitContainer>. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.RichTextBox> en <xref:System.Windows.Forms.DockStyle.Fill>.

     En este punto, si presiona F5 para ejecutar la aplicación, el formulario muestra una interfaz de usuario de tres partes, similar a la de Microsoft Outlook.

    > [!NOTE]
    > Al colocar el puntero del mouse sobre cualquiera de los separadores dentro de los controles <xref:System.Windows.Forms.SplitContainer>, puede cambiar el tamaño de las dimensiones internas.

En este punto del desarrollo de aplicaciones, ha creado una interfaz de usuario sofisticada. El paso siguiente es continuar con la programación de la propia aplicación, quizás conectando el control <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView> controles a algún tipo de origen de datos. Para obtener más información sobre la conexión de controles a datos, consulte [enlace de datos y Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
