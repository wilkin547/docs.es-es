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
ms.openlocfilehash: d0025ba136698c0a74a73e64a83fa4f526e44843
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736485"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Cómo: Heredar de controles de formularios Windows Forms existentes

Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia. Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control. Por ejemplo, si estuviera creando un control heredado de <xref:System.Windows.Forms.Button>, el nuevo control tendría un aspecto y actuaría exactamente igual que un control de <xref:System.Windows.Forms.Button> estándar. A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados. En algunos controles, también puede cambiar la apariencia visual del control heredado invalidando su método <xref:System.Windows.Forms.Control.OnPaint%2A>.

## <a name="to-create-an-inherited-control"></a>Para crear un control heredado

1. En Visual Studio, cree un nuevo proyecto de **aplicación de Windows Forms** .

1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    Aparecerá el cuadro de diálogo **Agregar nuevo elemento** .

1. En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.

    Se agrega un nuevo control personalizado al proyecto.

1. Si usa:

    - Visual Basic, en la parte superior de **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**. Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.
    - C#, abra CustomControl1.cs en el editor de código.

1. Busque la declaración de clase, que hereda de <xref:System.Windows.Forms.Control>.

1. Cambie la clase base para el control a partir del que desee heredar.

     Por ejemplo, si desea heredar de <xref:System.Windows.Forms.Button>, cambie la declaración de clase a lo siguiente:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb. Abra CustomControl1.vb en el Editor de código.

1. Implemente los métodos o propiedades personalizados que vaya a incorporar el control.

1. Si desea modificar la apariencia gráfica del control, invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A>.

    > [!NOTE]
    > Reemplazar <xref:System.Windows.Forms.Control.OnPaint%2A> no le permitirá modificar la apariencia de todos los controles. Los controles que tienen todo su dibujo realizado por Windows (por ejemplo, <xref:System.Windows.Forms.TextBox>) nunca llaman a su método de <xref:System.Windows.Forms.Control.OnPaint%2A> y, por tanto, nunca usarán el código personalizado. Consulte la documentación de ayuda del control determinado que desea modificar para ver si el método <xref:System.Windows.Forms.Control.OnPaint%2A> está disponible. Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md). Si un control no tiene <xref:System.Windows.Forms.Control.OnPaint%2A> enumerado como un método de miembro, no se puede modificar su apariencia invalidando este método. Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).

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
- [Cómo: Heredar de una clase de control](how-to-inherit-from-the-control-class.md)
- [cómo: Heredar de la clase UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Crear controles de Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Tutorial: heredar de un control Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
