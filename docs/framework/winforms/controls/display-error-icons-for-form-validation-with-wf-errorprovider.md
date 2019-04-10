---
title: Filtrar para mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms
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
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316510"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Filtrar para mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms
Puede usar un formulario Windows Forms <xref:System.Windows.Forms.ErrorProvider> componente para mostrar un icono de error cuando el usuario escribe datos no válidos. Debe tener al menos dos controles del formulario con el fin de pestaña entre ellos y, por tanto, invocar el código de validación.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Para mostrar un icono de error cuando el valor de un control no es válido  
  
1. Agregue dos controles, por ejemplo, los cuadros de texto, a un formulario de Windows.  
  
2. Agregar un <xref:System.Windows.Forms.ErrorProvider> componente al formulario.  
  
3. Seleccione el primer control y agregue código a su <xref:System.Windows.Forms.Control.Validating> controlador de eventos. En orden para que este código se ejecute correctamente, el procedimiento debe estar conectado al evento. Para obtener más información, vea [Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     El código siguiente comprueba la validez de los datos escritos por el usuario; Si los datos no son válidos, el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> se llama al método. El primer argumento de la <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método especifica qué control para mostrar el icono junto a. El segundo argumento es el texto del error para mostrar.  
  
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
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Ejecute el proyecto. Escriba datos no válidos (en este ejemplo, no numérico) en el primer control y, a continuación, pestaña a la segunda. Cuando aparezca el icono de error, apúntelo con el puntero del mouse para ver el texto del error.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Información general sobre el componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Filtrar para ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
