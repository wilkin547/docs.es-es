---
title: Procedimiento para crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 97888a77dfc731be591d5f0284e87f45ef7dc437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930175"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Procedimiento para crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el diseñador
En el procedimiento siguiente, creará una interfaz de usuario de varios paneles similar a la usada en Microsoft Outlook, con una lista de **carpetas** , un panel **mensajes** y un panel de **vista previa** . Esta disposición se logra principalmente a través de los controles de acoplamiento con el formato.

 Al acoplar un control, se determina en qué borde del contenedor primario está fijado un control. Por lo tanto, si establece <xref:System.Windows.Forms.SplitContainer.Dock%2A> la propiedad <xref:System.Windows.Forms.DockStyle.Right>en, el borde derecho del control se acoplará al borde derecho de su control principal. Además, el borde acoplado del control cambia de tamaño para coincidir con el de su control contenedor. Para obtener más información sobre cómo <xref:System.Windows.Forms.SplitContainer.Dock%2A> funciona la propiedad, [consulte How to: Acoplar controles en](how-to-dock-controls-on-windows-forms.md)Windows Forms.

 Este procedimiento se centra en organizar el <xref:System.Windows.Forms.SplitContainer> y los demás controles en el formulario, no en agregar funcionalidad para que la aplicación imite Microsoft Outlook.

 Para crear esta interfaz de usuario, coloque todos los controles dentro de <xref:System.Windows.Forms.SplitContainer> un control, que contiene <xref:System.Windows.Forms.TreeView> un control en el panel izquierdo. El panel derecho <xref:System.Windows.Forms.SplitContainer> del control contiene un segundo <xref:System.Windows.Forms.SplitContainer> control con un <xref:System.Windows.Forms.ListView> control sobre un <xref:System.Windows.Forms.RichTextBox> control. Estos <xref:System.Windows.Forms.SplitContainer> controles habilitan el cambio de tamaño independiente de los demás controles del formulario. Puede adaptar las técnicas de este procedimiento para crear interfaces de usuario personalizadas propias.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Para crear una interfaz de usuario de estilo Outlook en tiempo de diseño

1. Crear un nuevo proyecto de aplicación para Windows (**archivo** > **nuevo** > **proyecto** > **Visual C#**  o **Visual Basic** > **escritorio clásico**  >  **Windows Forms aplicación**).

2. Arrastre un <xref:System.Windows.Forms.SplitContainer> control del **cuadro de herramientas** al formulario. En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

3. Arrastre un <xref:System.Windows.Forms.TreeView> control desde el **cuadro de herramientas** al panel izquierdo del <xref:System.Windows.Forms.SplitContainer> control. En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad en <xref:System.Windows.Forms.DockStyle.Left> haciendo clic en el panel izquierdo del editor de valores que se muestra al hacer clic en la flecha hacia abajo.

4. Arrastre otro <xref:System.Windows.Forms.SplitContainer> control del **cuadro de herramientas**, colóquelo en el panel derecho del <xref:System.Windows.Forms.SplitContainer> control que ha agregado al formulario. En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad en <xref:System.Windows.Forms.DockStyle.Fill> y la <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad en <xref:System.Windows.Forms.Orientation.Horizontal>.

5. Arrastre un <xref:System.Windows.Forms.ListView> control desde el **cuadro de herramientas** al panel superior del segundo <xref:System.Windows.Forms.SplitContainer> control que ha agregado al formulario. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.ListView> en <xref:System.Windows.Forms.DockStyle.Fill>.

6. Arrastre un <xref:System.Windows.Forms.RichTextBox> control desde el **cuadro de herramientas** hasta el panel inferior del <xref:System.Windows.Forms.SplitContainer> segundo control. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.RichTextBox> en <xref:System.Windows.Forms.DockStyle.Fill>.

     En este punto, si presiona F5 para ejecutar la aplicación, el formulario muestra una interfaz de usuario de tres partes, similar a la de Microsoft Outlook.

    > [!NOTE]
    > Al colocar el puntero del mouse sobre cualquiera de los separadores de <xref:System.Windows.Forms.SplitContainer> los controles, puede cambiar el tamaño de las dimensiones internas.

En este punto del desarrollo de aplicaciones, ha creado una interfaz de usuario sofisticada. El paso siguiente es continuar con la programación de la propia aplicación, quizás conectando el <xref:System.Windows.Forms.TreeView> control y <xref:System.Windows.Forms.ListView> los controles a algún tipo de origen de datos. Para obtener más información sobre la conexión de controles a datos, consulte [enlace de datos y Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
