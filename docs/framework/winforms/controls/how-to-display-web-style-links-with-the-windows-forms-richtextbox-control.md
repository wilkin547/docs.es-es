---
title: Mostrar vínculos de estilo Web con el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 78a07a250744018f121b03f2973b1661ed6bf764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745531"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="d1f8e-102">Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1f8e-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="d1f8e-103">El control Windows Forms <xref:System.Windows.Forms.RichTextBox> puede mostrar vínculos Web en color y subrayado.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="d1f8e-104">Puede escribir código que abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="d1f8e-105">Para vincular a una página web con el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d1f8e-105">To link to a Web page with the RichTextBox control</span></span>

1. <span data-ttu-id="d1f8e-106">Establezca la <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad en una cadena que incluya una dirección URL válida (por ejemplo,"http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="d1f8e-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>

2. <span data-ttu-id="d1f8e-107">Asegúrese de que la propiedad <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> está establecida en `true` (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="d1f8e-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>

3. <span data-ttu-id="d1f8e-108">Cree una nueva instancia global del objeto <xref:System.Diagnostics.Process>.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>

4. <span data-ttu-id="d1f8e-109">Escriba un controlador de eventos para el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> que envía el texto deseado al explorador.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>

    <span data-ttu-id="d1f8e-110">En el ejemplo siguiente, el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> abre una instancia de Internet Explorer en la dirección URL especificada en la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="d1f8e-111">En este ejemplo se da por supuesto un formulario con un control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d1f8e-112">Al llamar al método <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>, se producirá una excepción <xref:System.Security.SecurityException> si se ejecuta el código en un contexto de confianza parcial debido a privilegios insuficientes.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="d1f8e-113">Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="d1f8e-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    <span data-ttu-id="d1f8e-114">(Visual C++) Debe inicializar el proceso `p`, lo que puede hacer si incluye la siguiente instrucción en el constructor del formulario:</span><span class="sxs-lookup"><span data-stu-id="d1f8e-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    <span data-ttu-id="d1f8e-115">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    <span data-ttu-id="d1f8e-116">Es importante detener inmediatamente el proceso que ha creado una vez que haya terminado de trabajar con él.</span><span class="sxs-lookup"><span data-stu-id="d1f8e-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="d1f8e-117">Al hacer referencia al código presentado anteriormente, el código para detener el proceso podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1f8e-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a><span data-ttu-id="d1f8e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1f8e-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="d1f8e-119">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="d1f8e-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="d1f8e-120">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1f8e-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
