---
title: Crear un cuadro de texto de contraseña con el control TextBox
description: Obtenga información sobre cómo cerate un texto Windows Forms que muestra caracteres de marcador de posición mientras un usuario escribe una cadena.
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
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904317"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="5b057-103">Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b057-103">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="5b057-104">Un cuadro de contraseña es un Windows Forms cuadro de texto que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.</span><span class="sxs-lookup"><span data-stu-id="5b057-104">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="5b057-105">Para crear un cuadro de texto de contraseña</span><span class="sxs-lookup"><span data-stu-id="5b057-105">To create a password text box</span></span>

1. <span data-ttu-id="5b057-106">Establezca la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad del <xref:System.Windows.Forms.TextBox> control en un carácter específico.</span><span class="sxs-lookup"><span data-stu-id="5b057-106">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="5b057-107">La <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad especifica el carácter que se muestra en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5b057-107">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="5b057-108">Por ejemplo, si desea que se muestren asteriscos en el cuadro contraseña, especifique \* para la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en el ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="5b057-108">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="5b057-109">A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.</span><span class="sxs-lookup"><span data-stu-id="5b057-109">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="5b057-110">Opta Establezca la <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5b057-110">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="5b057-111">La propiedad determina el número de caracteres que se pueden escribir en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5b057-111">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="5b057-112">Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta más caracteres.</span><span class="sxs-lookup"><span data-stu-id="5b057-112">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="5b057-113">Tenga en cuenta que es posible que no quiera hacer esto, ya que la longitud máxima de una contraseña puede ser de uso para los hackers que intentan adivinar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5b057-113">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="5b057-114">En el ejemplo de código siguiente se muestra cómo inicializar un cuadro de texto que aceptará una cadena de hasta 14 caracteres y mostrará asteriscos en lugar de la cadena.</span><span class="sxs-lookup"><span data-stu-id="5b057-114">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="5b057-115">El `InitializeMyControl` procedimiento no se ejecutará automáticamente; se debe llamar a.</span><span class="sxs-lookup"><span data-stu-id="5b057-115">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5b057-116">El uso de la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en un cuadro de texto puede ayudarle a garantizar que otras personas no podrán determinar la contraseña de un usuario si observan que el usuario la escribe.</span><span class="sxs-lookup"><span data-stu-id="5b057-116">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="5b057-117">Esta medida de seguridad no cubre ningún tipo de almacenamiento o transmisión de la contraseña que puede producirse debido a la lógica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b057-117">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="5b057-118">Dado que el texto escrito no está cifrado de ningún modo, debe tratarlo como lo haría con cualquier otra información confidencial.</span><span class="sxs-lookup"><span data-stu-id="5b057-118">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="5b057-119">Aunque no aparece como tal, la contraseña todavía se trata como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).</span><span class="sxs-lookup"><span data-stu-id="5b057-119">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5b057-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b057-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="5b057-121">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="5b057-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5b057-122">Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b057-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="5b057-123">Procedimiento para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="5b057-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="5b057-124">Procedimiento para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="5b057-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="5b057-125">Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b057-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5b057-126">Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b057-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5b057-127">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="5b057-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
