---
title: para agregar controles
description: Obtenga información sobre cómo dibujar un control en Windows Forms. Un control es un componente de un formulario que puede usar para mostrar información o aceptar datos proporcionados por el usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325886"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Cómo: Agregar controles a formularios Windows Forms

La mayoría de los formularios se diseñan agregando controles a la superficie del formulario para definir una interfaz de usuario (UI). Un *control* es un componente de un formulario que se usa para mostrar información o para aceptar datos proporcionados por el usuario. Para obtener más información sobre los controles, vea [controles de Windows Forms](index.md).

## <a name="to-draw-a-control-on-a-form"></a>Para dibujar un control en un formulario

1. Abra el formulario. Para obtener más información, vea [Cómo: mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. En el **cuadro de herramientas**, haga clic en el control que desee agregar al formulario.

3. En el formulario, haga clic en el lugar en el que desea que se encuentre la esquina superior izquierda del control y arrastre hasta donde desee que se encuentre la esquina inferior derecha del control.

    El control se agrega al formulario con la ubicación y el tamaño especificados.

    > [!NOTE]
    > Cada control tiene definido un tamaño predeterminado. Puede Agregar un control al formulario en el tamaño predeterminado del control arrastrándolo desde el **cuadro de herramientas** al formulario.

## <a name="to-drag-a-control-to-a-form"></a>Para arrastrar un control a un formulario

1. Abra el formulario. Para obtener más información, vea [Cómo: mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo al formulario.

    El control se agrega al formulario en la ubicación especificada en su tamaño predeterminado.

    > [!NOTE]
    > Puede hacer doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.

    También puede Agregar controles de forma dinámica a un formulario en tiempo de ejecución. En el ejemplo de código siguiente, se <xref:System.Windows.Forms.TextBox> agregará un control al formulario cuando <xref:System.Windows.Forms.Button> se haga clic en un control.

    > [!NOTE]
    > El procedimiento siguiente requiere la existencia de un formulario con un control **botón** , `Button1` , ya colocado en él.

## <a name="to-add-a-control-to-a-form-programmatically"></a>Para agregar un control a un formulario mediante programación

1. En el método que controla el evento del botón `Click` dentro de la clase del formulario, inserte código similar al siguiente para agregar una referencia a la variable de control, establecer la clase del control `Location` y agregar el control.

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > También puede agregar código para inicializar otras propiedades del control.

    > [!IMPORTANT]
    > Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un malintencionado `UserControl` . Esto solo suponer un problema en el caso de que una persona malintencionada cree un control personalizado perjudicial y, después, lo agregue por error a su proyecto.

## <a name="see-also"></a>Vea también

- [Windows Forms controles](index.md)
- [Cómo: Cambiar el tamaño de los controles en formularios Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
