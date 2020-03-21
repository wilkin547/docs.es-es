---
title: 'Tutorial: Trabajar con el control MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182050"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Tutorial: Trabajar con el control MaskedTextBox
Las tareas ilustradas en este tutorial incluyen:  
  
- Inicialización <xref:System.Windows.Forms.MaskedTextBox> del control  
  
- Uso <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> del controlador de eventos para alertar al usuario cuando un carácter no se ajusta a la máscara  
  
- Asignar un tipo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> a la <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> propiedad y usar el controlador de eventos para alertar al usuario cuando el valor que intentan confirmar no es válido para el tipo  
  
## <a name="creating-the-project-and-adding-a-control"></a>Creación del proyecto y adición de un control  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Para agregar un control MaskedTextBox al formulario  
  
1. Abra el formulario en el <xref:System.Windows.Forms.MaskedTextBox> que desea colocar el control.  
  
2. Arrastre <xref:System.Windows.Forms.MaskedTextBox> un control desde el **cuadro de herramientas** al formulario.  
  
3. Haga clic con el botón derecho en el control y elija **Propiedades**. En la ventana **Propiedades,** seleccione la propiedad **Máscara** y haga clic en el botón **...** (ellipsis) situado junto al nombre de la propiedad.  
  
4. En el cuadro de diálogo Máscara de **entrada,** seleccione la máscara **Fecha corta** y haga clic en **Aceptar**.  
  
5. En la ventana <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> **Propiedades,** establezca la propiedad en . `true` Esta propiedad hace que un pitido corto suene cada vez que el usuario intenta introducir un carácter que infringe la definición de máscara.  
  
 Para obtener un resumen de los caracteres que admite <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> la propiedad Mask, vea la sección Comentarios de la propiedad.  
  
## <a name="alert-the-user-to-input-errors"></a>Alertar al usuario de los errores de entrada  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Agregue una punta de globo para la entrada de máscara rechazada  
  
1. Vuelva al cuadro de <xref:System.Windows.Forms.ToolTip> **herramientas** y agregue un al formulario.  
  
2. Cree un controlador <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> de eventos para <xref:System.Windows.Forms.ToolTip> el evento que provoca el momento en que se produce un error de entrada. La punta del globo permanece visible durante cinco segundos o hasta que el usuario hace clic en ella.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Alertar al usuario de un tipo que no es válido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Agregue una sugerencia de globo para tipos de datos no válidos  
  
1. En el controlador <xref:System.Windows.Forms.Form.Load> de eventos <xref:System.Type> del formulario, asigne un objeto que represente el <xref:System.DateTime> tipo a la <xref:System.Windows.Forms.MaskedTextBox> propiedad del <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> control:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MaskedTextBox>
- [Control MaskedTextBox](maskedtextbox-control-windows-forms.md)
