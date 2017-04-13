---
title: "Tutorial: Trabajar con el control MaskedTextBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "entrada, controlar para garantizar la validez"
  - "MaskedTextBox (control) [Windows Forms], validación"
  - "MaskedTextBox (control) [Windows Forms], tutoriales"
  - "texto, controles para entrada"
  - "datos proporcionados por el usuario, controlar"
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Tutorial: Trabajar con el control MaskedTextBox
Las tareas ilustradas en este tutorial incluyen:  
  
-   Inicializar el control <xref:System.Windows.Forms.MaskedTextBox>  
  
-   Utilizar el controlador de eventos <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> para avisar al usuario cuando un carácter no se ajusta a la máscara  
  
-   Asignar un tipo a la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> y utilizar el controlador de eventos <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> para avisar al usuario cuando el valor que se intenta confirmar no es válido para el tipo  
  
## Crear el proyecto y agregar un control  
  
#### Para agregar un control MaskedTextBox al formulario  
  
1.  Abra el formulario en el que desea colocar el control <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  Arrastre un control <xref:System.Windows.Forms.MaskedTextBox> desde el **Cuadro de herramientas** hasta el formulario.  
  
3.  Haga clic con el botón secundario del mouse en el control y elija **Propiedades**.  En la ventana **Propiedades**, seleccione la propiedad **Mask** y haga clic en el botón **...**. \(puntos suspensivos\) junto al nombre de propiedad.  
  
4.  En el cuadro de diálogo **Máscara de entrada**, seleccione la máscara de **Fecha corta** y haga clic en **Aceptar**.  
  
5.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> en `true`.  Esta propiedad hace que suene un bip corto cada vez que el usuario intenta introducir un carácter que infringe la definición de máscara.  
  
 Para obtener un resumen de los caracteres que la propiedad Mask admite, vea la sección Comentarios de la propiedad <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>.  
  
## Avise al usuario de los errores de entrada  
  
#### Agregue un globo de sugerencias para entradas de máscara rechazadas  
  
1.  Vuelva al **Cuadro de herramientas** y agregue <xref:System.Windows.Forms.ToolTip> al formulario.  
  
2.  Cree un controlador de eventos para el evento <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> que muestre el texto de <xref:System.Windows.Forms.ToolTip> cuando se produce un error de entrada.  El globo de sugerencias permanece visible durante cinco segundos o hasta que el usuario hace clic en él.  
  
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
  
## Avise al usuario de que tipo no es válido  
  
#### Agregue un globo de sugerencias para los tipos de datos no válidos  
  
1.  En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, asigne un objeto <xref:System.Type> que representa el tipo <xref:System.DateTime> en la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> del control <xref:System.Windows.Forms.MaskedTextBox>:  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.MaskedTextBox>   
 [MaskedTextBox \(Control\)](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)