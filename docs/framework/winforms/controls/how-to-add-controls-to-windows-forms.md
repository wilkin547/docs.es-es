---
title: "C&#243;mo: Agregar controles a formularios Windows Forms | Microsoft Docs"
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
  - "controles [Windows Forms], agregar"
  - "controles de Windows Forms, agregar a un formulario"
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Agregar controles a formularios Windows Forms
La mayoría de los formularios se diseñan agregando controles a la superficie del formulario para definir una interfaz de usuario.  Un *control* es un componente de un formulario que se utiliza para mostrar información o aceptar los datos introducidos por el usuario.  Para obtener más información sobre controles, vea [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para dibujar un control en un formulario  
  
1.  Abra el formulario.  Para obtener más información, vea [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/es-es/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **Cuadro de herramientas**, haga clic en el control que desee agregar al formulario.  
  
3.  En el formulario, haga clic en el punto en que desee que se encuentre la esquina superior izquierda del control y arrastre hasta donde desee que se encuentre la esquina inferior derecha del control.  
  
     El control se agregará al formulario con la ubicación y el tamaño especificados.  
  
    > [!NOTE]
    >  Cada control tiene definido un tamaño predeterminado.  Puede agregar un control al formulario con su tamaño predeterminado arrastrándolo desde el **Cuadro de herramientas** al formulario.  
  
### Para agregar un control a un formulario  
  
1.  Abra el formulario.  Para obtener más información, vea [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/es-es/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **Cuadro de herramientas**, haga clic en el control que desee y arrástrelo al formulario.  
  
     El control se agregará al formulario en la ubicación especificada, con su tamaño predeterminado.  
  
    > [!NOTE]
    >  Puede hacer doble clic en un control del **Cuadro de herramientas** para agregarlo al margen superior izquierdo del formulario con su tamaño predeterminado.  
  
     También puede agregar controles dinámicamente a un formulario en tiempo de ejecución.  En el ejemplo de código siguiente, un control <xref:System.Windows.Forms.TextBox> se agregará al formulario cuando se hace clic en un control <xref:System.Windows.Forms.Button>.  
  
    > [!NOTE]
    >  El procedimiento siguiente requiere la existencia de un formulario con un control **Button**, `Button1`, ya colocado en él.  
  
### Para agregar un control a un formulario mediante programación  
  
1.  En el método que controla el evento `Click` del botón dentro de la clase del formulario, inserte código similar al siguiente para agregar una referencia a la variable de control, establecer el valor de `Location` para el control y agregar el control:  
  
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
    >  También puede agregar código para inicializar otras propiedades del control.  
  
    > [!IMPORTANT]
    >  Puede exponer el equipo local a un riesgo de seguridad a través de la red si hace referencia a un `UserControl` creado con fines malintencionados.  El problema se puede presentar en el caso de que una persona malintencionada cree un control personalizado perjudicial que, a continuación, se agregue por error a su proyecto.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Cómo: Cambiar el tamaño de los controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)   
 [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)