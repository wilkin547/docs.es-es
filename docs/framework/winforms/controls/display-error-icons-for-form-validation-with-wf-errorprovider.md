---
title: 'Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms'
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
ms.openlocfilehash: 237a61cc21a18805fa502c9870d8ea472ac54d71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527305"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="524a0-102">Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="524a0-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="524a0-103">Puede utilizar un formulario Windows Forms <xref:System.Windows.Forms.ErrorProvider> componente para mostrar un icono de error cuando el usuario escriba datos no válidos.</span><span class="sxs-lookup"><span data-stu-id="524a0-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="524a0-104">Debe tener al menos dos controles en el formulario con el fin de pestaña entre ellos y, por tanto, invocar el código de validación.</span><span class="sxs-lookup"><span data-stu-id="524a0-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="524a0-105">Para mostrar un icono de error cuando el valor de un control no es válido</span><span class="sxs-lookup"><span data-stu-id="524a0-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="524a0-106">Agregue dos controles: por ejemplo, los cuadros de texto, en un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="524a0-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="524a0-107">Agregar un <xref:System.Windows.Forms.ErrorProvider> componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="524a0-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="524a0-108">Seleccione el primer control y agregue código a su <xref:System.Windows.Forms.Control.Validating> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="524a0-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="524a0-109">En orden para este código se ejecute correctamente, el procedimiento debe estar conectado al evento.</span><span class="sxs-lookup"><span data-stu-id="524a0-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="524a0-110">Para obtener más información, consulte [Cómo: crear controladores de eventos en tiempo de ejecución para formularios Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="524a0-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="524a0-111">El código siguiente comprueba la validez de los datos escritos por el usuario; Si los datos no son válidos, el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="524a0-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="524a0-112">El primer argumento de la <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método especifica que el control a mostrar el icono junto a.</span><span class="sxs-lookup"><span data-stu-id="524a0-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="524a0-113">El segundo argumento es el texto del error para mostrar.</span><span class="sxs-lookup"><span data-stu-id="524a0-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="524a0-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="524a0-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="524a0-115">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="524a0-115">Run the project.</span></span> <span data-ttu-id="524a0-116">Escribir datos no válidos (en este ejemplo, no numéricos) en el primer control y, a continuación, ficha al segundo.</span><span class="sxs-lookup"><span data-stu-id="524a0-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="524a0-117">Cuando se muestra el icono de error, apunte al icono con el puntero del mouse para ver el texto del error.</span><span class="sxs-lookup"><span data-stu-id="524a0-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524a0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="524a0-118">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [<span data-ttu-id="524a0-119">Información general del componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="524a0-119">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="524a0-120">Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="524a0-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
