---
title: Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960622"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms
El explorador de Windows es una opción de interfaz de usuario común para las aplicaciones debido a su familiaridad.

 El explorador de Windows es, esencialmente <xref:System.Windows.Forms.TreeView> , un control <xref:System.Windows.Forms.ListView> y un control en paneles independientes. Un divisor realiza el redimensionamiento de los paneles. Esta disposición de controles es muy eficaz para mostrar y examinar la información.

 En los pasos siguientes se muestra cómo organizar los controles en un formulario similar al explorador de Windows. No muestran cómo agregar la funcionalidad de exploración de archivos de la aplicación del explorador de Windows.

## <a name="to-create-a-windows-explorer-style-windows-form"></a>Para crear un Windows Form con estilo Explorador de Windows

1. Crear un nuevo proyecto de aplicación para Windows (**archivo** > **nuevo** > **proyecto** > **Visual C#**  o **Visual Basic** > **escritorio clásico**  >  **Windows Forms aplicación**).

2. En el **cuadro de herramientas**:

    1. Arrastre un <xref:System.Windows.Forms.SplitContainer> control al formulario.

    2. Arrastre un <xref:System.Windows.Forms.TreeView> control a **SplitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> el panel del control marcado como **Panel1**).

    3. Arrastre un <xref:System.Windows.Forms.ListView> control a **SplitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> el panel del control marcado como **Panel2**).

3. Seleccione los tres controles presionando la tecla CTRL y haciendo clic en ellos a su vez. Al seleccionar el <xref:System.Windows.Forms.SplitContainer> control, haga clic en la barra de división, en lugar de en los paneles.

    > [!NOTE]
    > No use el comando **seleccionar todo** en el menú **edición** . Si lo hace, la propiedad necesaria en el paso siguiente no aparecerá en la ventana **propiedades** .

4. En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

5. Presione F5 para ejecutar la aplicación.

     El formulario muestra una interfaz de usuario de dos partes, similar a la del explorador de Windows.

    > [!NOTE]
    > Al arrastrar el divisor, los paneles cambian de tamaño.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [Procedimientos: Cree una interfaz de usuario de MULTIPANEL con Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Cómo: Definir el comportamiento de ajuste de tamaño y colocación en una ventana dividida](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Cómo: Dividir una ventana horizontalmente](how-to-split-a-window-horizontally.md)
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
