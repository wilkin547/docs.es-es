---
title: Procedimiento para agregar controles a formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 04597283a8ff2e21a0f227268671d3605eac6356
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343595"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Procedimiento para agregar controles a formularios Windows Forms
Mayoría de los formularios está diseñada agregando controles a la superficie del formulario para definir una interfaz de usuario (UI). Un *control* es un componente en un formulario que se usa para mostrar información o Aceptar la entrada del usuario. Para obtener más información acerca de los controles, vea [controles de formularios Windows Forms](index.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-control-on-a-form"></a>Para dibujar un control en un formulario  
  
1. Abra el formulario. Para obtener más información, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2. En el **cuadro de herramientas**, haga clic en el control que desea agregar al formulario.  
  
3. En el formulario, haga clic donde desee que la esquina superior izquierda del control que se ubiquen y arrastre hasta donde desee que la esquina inferior derecha del control que se encuentra.  
  
     El control se agrega al formulario con el tamaño y la ubicación especificada.  
  
    > [!NOTE]
    >  Cada control tiene definido un tamaño predeterminado. Puede agregar un control al formulario en el tamaño del control de forma predeterminada si lo arrastra desde el **cuadro de herramientas** al formulario.  
  
### <a name="to-drag-a-control-to-a-form"></a>Para arrastrar un control a un formulario  
  
1. Abra el formulario. Para obtener más información, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2. En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo al formulario.  
  
     El control se agrega al formulario en la ubicación especificada en su tamaño predeterminado.  
  
    > [!NOTE]
    >  Haga doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.  
  
     También puede agregar controles dinámicamente a un formulario en tiempo de ejecución. En el ejemplo de código siguiente, un <xref:System.Windows.Forms.TextBox> control se agregarán al formulario cuando un <xref:System.Windows.Forms.Button> se hace clic en el control.  
  
    > [!NOTE]
    >  El procedimiento siguiente requiere la existencia de un formulario con un **botón** control, `Button1`, ya colocados en él.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Para agregar un control a un formulario mediante programación  
  
1. En el método que controla el botón `Click` evento dentro de la clase del formulario, insertar código similar al siguiente para agregar una referencia a la variable de control, establezca el control `Location`y agregar el control.  
  
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
    >  Podría exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un malintencionado `UserControl`. Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Cómo: Cambiar el tamaño de los controles de Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Cómo: Establecer el texto mostrado por un Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
