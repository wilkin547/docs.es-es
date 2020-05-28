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
ms.openlocfilehash: 06ed304e566bb437a2353dd330d7de5328f2a729
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144830"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="b99ae-102">Procedimiento para mostrar vínculos de estilo web con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b99ae-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="b99ae-103">El <xref:System.Windows.Forms.RichTextBox> control Windows Forms puede mostrar vínculos Web en color y subrayado.</span><span class="sxs-lookup"><span data-stu-id="b99ae-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="b99ae-104">Puede escribir código que abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="b99ae-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="b99ae-105">Para vincular a una página web con el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b99ae-105">To link to a Web page with the RichTextBox control</span></span>

1. <span data-ttu-id="b99ae-106">Establezca la <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad en una cadena que incluya una dirección URL válida (por ejemplo, " https://www.microsoft.com/ ").</span><span class="sxs-lookup"><span data-stu-id="b99ae-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "https://www.microsoft.com/").</span></span>

2. <span data-ttu-id="b99ae-107">Asegúrese de que la <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propiedad está establecida en `true` (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b99ae-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>

3. <span data-ttu-id="b99ae-108">Cree una nueva instancia global del <xref:System.Diagnostics.Process> objeto.</span><span class="sxs-lookup"><span data-stu-id="b99ae-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>

4. <span data-ttu-id="b99ae-109">Escriba un controlador de eventos para el <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento que envía al explorador el texto deseado.</span><span class="sxs-lookup"><span data-stu-id="b99ae-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>

    <span data-ttu-id="b99ae-110">En el ejemplo siguiente, el <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento abre una instancia de Internet Explorer en la dirección URL especificada en la <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad del <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="b99ae-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="b99ae-111">En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="b99ae-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b99ae-112">Al llamar al <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> método, se producirá una <xref:System.Security.SecurityException> excepción si está ejecutando el código en un contexto de confianza parcial porque no tiene privilegios suficientes.</span><span class="sxs-lookup"><span data-stu-id="b99ae-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="b99ae-113">Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="b99ae-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

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

    <span data-ttu-id="b99ae-114">(Visual C++) Debe inicializar `p` el proceso, que puede hacer incluyendo la siguiente instrucción en el constructor del formulario:</span><span class="sxs-lookup"><span data-stu-id="b99ae-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    <span data-ttu-id="b99ae-115">(Visual C#, Visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b99ae-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

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

    <span data-ttu-id="b99ae-116">Es importante detener inmediatamente el proceso que ha creado una vez que haya terminado de trabajar con él.</span><span class="sxs-lookup"><span data-stu-id="b99ae-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="b99ae-117">Al hacer referencia al código presentado anteriormente, el código para detener el proceso podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b99ae-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b99ae-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b99ae-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="b99ae-119">Control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b99ae-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="b99ae-120">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b99ae-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
