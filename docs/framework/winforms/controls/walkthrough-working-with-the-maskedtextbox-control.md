---
title: 'Tutorial: Trabajar con el control MaskedTextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06b8ffd2bda9597198d94c99a785c59cc7cc052e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Tutorial: Trabajar con el control MaskedTextBox
Las tareas ilustradas en este tutorial incluyen:  
  
-   Inicializar el <xref:System.Windows.Forms.MaskedTextBox> control  
  
-   Mediante el <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> controlador de eventos para alertar al usuario cuando un carácter no se ajusta a la máscara  
  
-   Asignar un tipo a la <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propiedad y el uso del <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> controlador de eventos para alertar al usuario cuando el valor que se intenta confirmar no es válido para el tipo  
  
## <a name="creating-the-project-and-adding-a-control"></a>Crear el proyecto y agregar un Control  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Para agregar un control MaskedTextBox al formulario  
  
1.  Abra el formulario en el que desea colocar el <xref:System.Windows.Forms.MaskedTextBox> control.  
  
2.  Arrastre un <xref:System.Windows.Forms.MaskedTextBox> controlar desde la **cuadro de herramientas** al formulario.  
  
3.  Haga clic en el control y elija **propiedades**. En el **propiedades** ventana, seleccione la **máscara** propiedad y haga clic en el **...**  () puntos suspensivos junto al nombre de la propiedad.  
  
4.  En el **máscara de entrada** cuadro de diálogo, seleccione la **fecha corta** enmascarar y haga clic en **Aceptar**.  
  
5.  En el **propiedades** ventana conjunto el <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> propiedad `true`. Esta propiedad hace que un bip corto para cada vez que el usuario intenta un carácter que infringe la definición de máscara de entrada de sonido.  
  
 Para obtener un resumen de los caracteres que la propiedad Mask admite, vea la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
## <a name="alert-the-user-to-input-errors"></a>Alertar al usuario para errores de entrada  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Agregue un globo de sugerencias para entradas de máscara rechazadas  
  
1.  Vuelva a la **cuadro de herramientas** y agregue un <xref:System.Windows.Forms.ToolTip> al formulario.  
  
2.  Crear un controlador de eventos para el <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> eventos provocados por la <xref:System.Windows.Forms.ToolTip> cuando se produce un error en la entrada. El globo de sugerencias permanece visible durante cinco segundos, o hasta que el usuario hace clic en él.  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Alertar al usuario a un tipo que no es válido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Agregue un globo de sugerencias para los tipos de datos no válidos  
  
1.  En el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos, asignar un <xref:System.Type> objeto que representa el <xref:System.DateTime> escriba a la <xref:System.Windows.Forms.MaskedTextBox> del control <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propiedad:  
  
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
  
2.  Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [MaskedTextBox (control)](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
