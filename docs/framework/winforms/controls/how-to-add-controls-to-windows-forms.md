---
title: "Cómo: Agregar controles a formularios Windows Forms"
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
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1f5f739afa914a69017dbba2a9a4afb990f6e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-controls-to-windows-forms"></a>Cómo: Agregar controles a formularios Windows Forms
Mayoría de los formularios se diseñan agregando controles a la superficie del formulario para definir una interfaz de usuario (UI). A *control* es un componente en un formulario que se utiliza para mostrar información o Aceptar proporcionados por el usuario. Para obtener más información acerca de los controles, consulte [controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-draw-a-control-on-a-form"></a>Para dibujar un control en un formulario  
  
1.  Abra el formulario. Para obtener más información, consulte [Cómo: mostrar Windows Forms en el diseñador](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **cuadro de herramientas**, haga clic en el control que desea agregar al formulario.  
  
3.  En el formulario, haga clic donde desee que la esquina superior izquierda del control para que se encuentre y arrastre hasta donde desee que la esquina inferior derecha del control para que se encuentre.  
  
     El control se agrega al formulario con el tamaño y la ubicación especificada.  
  
    > [!NOTE]
    >  Cada control tiene definido un tamaño predeterminado. Puede agregar un control al formulario en el tamaño del control predeterminado arrastrándolo desde el **cuadro de herramientas** al formulario.  
  
### <a name="to-drag-a-control-to-a-form"></a>Al arrastrar un control a un formulario  
  
1.  Abra el formulario. Para obtener más información, consulte [Cómo: mostrar Windows Forms en el diseñador](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo hasta el formulario.  
  
     El control se agrega al formulario en la ubicación especificada con su tamaño predeterminado.  
  
    > [!NOTE]
    >  Haga doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.  
  
     También puede agregar controles de forma dinámica a un formulario en tiempo de ejecución. En el ejemplo de código siguiente, un <xref:System.Windows.Forms.TextBox> control se agregará al formulario cuando un <xref:System.Windows.Forms.Button> se hace clic en el control.  
  
    > [!NOTE]
    >  El siguiente procedimiento requiere la existencia de un formulario con un **botón** control, `Button1`, ya colocados en él.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Para agregar un control a un formulario mediante programación  
  
1.  En el método que controla el botón `Click` evento dentro de la clase del formulario, insertar código similar al siguiente para agregar una referencia a la variable de control, establezca el control `Location`y agregar el control.  
  
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
    >  Puede exponer el equipo local a un riesgo de seguridad a través de la red mediante una referencia a un malintencionado `UserControl`. Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Procedimiento para cambiar el tamaño de los controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [Establecer el texto mostrado por un control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
