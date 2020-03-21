---
title: para heredar desde controles existentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849385"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Cómo: Heredar de controles de formularios Windows Forms existentes

Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia. Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control. Por ejemplo, si estuviera creando un <xref:System.Windows.Forms.Button>control heredado de , el nuevo <xref:System.Windows.Forms.Button> control se vería y actuaría exactamente como un control estándar. A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados. En algunos controles, también puede cambiar la apariencia visual <xref:System.Windows.Forms.Control.OnPaint%2A> del control heredado reemplazando su método.

## <a name="to-create-an-inherited-control"></a>Para crear un control heredado

1. En Visual Studio, cree un nuevo proyecto **de aplicación de formularios Windows Forms.**

1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    Aparecerá el cuadro de diálogo **Agregar nuevo elemento** .

1. En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.

    Se agrega un nuevo control personalizado al proyecto.

1. Si está utilizando:

    - Visual Basic, en la parte superior del **Explorador**de soluciones , haga clic en **Mostrar todos los archivos**. Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.
    - Abrir CustomControl1.cs en el Editor de código.

1. Busque la declaración de <xref:System.Windows.Forms.Control>clase, que hereda de .

1. Cambie la clase base para el control a partir del que desee heredar.

     Por ejemplo, si desea <xref:System.Windows.Forms.Button>heredar de , cambie la declaración de clase a lo siguiente:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb. Abra CustomControl1.vb en el Editor de código.

1. Implemente los métodos o propiedades personalizados que vaya a incorporar el control.

1. Si desea modificar la apariencia gráfica del <xref:System.Windows.Forms.Control.OnPaint%2A> control, invalide el método.

    > [!NOTE]
    > La <xref:System.Windows.Forms.Control.OnPaint%2A> invalidación no le permitirá modificar la apariencia de todos los controles. Los controles que tienen toda su pintura realizada <xref:System.Windows.Forms.TextBox>por Windows <xref:System.Windows.Forms.Control.OnPaint%2A> (por ejemplo, ) nunca llaman a su método y, por lo tanto, nunca usarán el código personalizado. Consulte la documentación de ayuda para el control determinado <xref:System.Windows.Forms.Control.OnPaint%2A> que desea modificar para ver si el método está disponible. Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md). Si un control <xref:System.Windows.Forms.Control.OnPaint%2A> no tiene la lista como un método miembro, no puede modificar su apariencia reemplazando este método. Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. Guarde y pruebe el control.

## <a name="see-also"></a>Consulte también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Heredar de la clase control](how-to-inherit-from-the-control-class.md)
- [Cómo: Heredar de una clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Crear controles para Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Tutorial: Heredar de un control de formularios Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
