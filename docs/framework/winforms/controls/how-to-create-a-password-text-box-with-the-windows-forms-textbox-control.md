---
title: Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: ab5df1233c16a7ce076efa817fb14808b588ebcd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300988"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="bd59c-102">Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd59c-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="bd59c-103">Un cuadro de contraseña es un cuadro de texto de Windows Forms que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.</span><span class="sxs-lookup"><span data-stu-id="bd59c-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="bd59c-104">Para crear un cuadro de texto de contraseña</span><span class="sxs-lookup"><span data-stu-id="bd59c-104">To create a password text box</span></span>  
  
1. <span data-ttu-id="bd59c-105">Establecer el <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad de la <xref:System.Windows.Forms.TextBox> control a un carácter específico.</span><span class="sxs-lookup"><span data-stu-id="bd59c-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="bd59c-106">El <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad especifica el carácter que se muestra en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd59c-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="bd59c-107">Por ejemplo, si desea que se muestren asteriscos en el cuadro de contraseña, especifique \* para la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="bd59c-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="bd59c-108">A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.</span><span class="sxs-lookup"><span data-stu-id="bd59c-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2. <span data-ttu-id="bd59c-109">(Opcional) Establecer el <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bd59c-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="bd59c-110">La propiedad determina cuántos caracteres se pueden escribir en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd59c-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="bd59c-111">Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta caracteres más.</span><span class="sxs-lookup"><span data-stu-id="bd59c-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="bd59c-112">Tenga en cuenta que es posible que no desea hacer esto como la longitud máxima de una contraseña puede resultar útil para los hackers que intentan adivinar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="bd59c-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="bd59c-113">El ejemplo de código siguiente muestra cómo inicializar un cuadro de texto que se aceptan una cadena de hasta 14 caracteres y se muestran asteriscos en lugar de la cadena.</span><span class="sxs-lookup"><span data-stu-id="bd59c-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="bd59c-114">El `InitializeMyControl` procedimiento no se ejecutará automáticamente; debe llamarse.</span><span class="sxs-lookup"><span data-stu-id="bd59c-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bd59c-115">Mediante el <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en un cuadro de texto puede ayudar a garantizar que otras personas no podrán determinar la contraseña de un usuario si ven cuando el usuario escribe.</span><span class="sxs-lookup"><span data-stu-id="bd59c-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="bd59c-116">Esta medida de seguridad no cubre a cualquier tipo de almacenamiento o transmisión de la contraseña que se puede producir debido a la lógica de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd59c-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="bd59c-117">Dado que no se cifra el texto escrito en cualquier forma, debe tratar como lo haría con cualquier otro dato confidencial.</span><span class="sxs-lookup"><span data-stu-id="bd59c-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="bd59c-118">Aunque no aparezcan como tal, la contraseña es todavía se tratan como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).</span><span class="sxs-lookup"><span data-stu-id="bd59c-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bd59c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd59c-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="bd59c-120">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="bd59c-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="bd59c-121">Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd59c-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="bd59c-122">Filtrar para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="bd59c-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="bd59c-123">Filtrar para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="bd59c-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="bd59c-124">Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd59c-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bd59c-125">Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd59c-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bd59c-126">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="bd59c-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
