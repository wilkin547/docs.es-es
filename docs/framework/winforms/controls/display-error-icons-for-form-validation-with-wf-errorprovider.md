---
title: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745908"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms
Puede usar un componente de <xref:System.Windows.Forms.ErrorProvider> de Windows Forms para mostrar un icono de error cuando el usuario escribe datos no válidos. Debe tener al menos dos controles en el formulario para que el tabulador entre ellos y, de este modo, invoque el código de validación.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Para mostrar un icono de error cuando el valor de un control no es válido  
  
1. Agregue dos controles (por ejemplo, cuadros de texto) a un formulario de Windows Forms.  
  
2. Agregue un componente de <xref:System.Windows.Forms.ErrorProvider> al formulario.  
  
3. Seleccione el primer control y agregue código a su controlador de eventos <xref:System.Windows.Forms.Control.Validating>. Para que este código se ejecute correctamente, el procedimiento debe estar conectado al evento. Para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     En el código siguiente se prueba la validez de los datos que el usuario ha especificado; Si los datos no son válidos, se llama al método <xref:System.Windows.Forms.ErrorProvider.SetError%2A>. El primer argumento del método <xref:System.Windows.Forms.ErrorProvider.SetError%2A> especifica en qué control se va a mostrar el icono situado junto a. El segundo argumento es el texto de error que se va a mostrar.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Ejecute el proyecto. Escriba los datos no válidos (en este ejemplo, no numéricos) en el primer control y, a continuación, presione la tecla TAB hasta el segundo. Cuando se muestre el icono de error, apunte con el puntero del mouse para ver el texto del error.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Información general del componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
