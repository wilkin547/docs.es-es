---
title: Vincular a un objeto o una página web con el control LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 1669a9d6aba39b02d228c735701ca4e31c8f8291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745209"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="1e531-102">Cómo: Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e531-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="1e531-103">El control Windows Forms <xref:System.Windows.Forms.LinkLabel> permite crear vínculos de estilo Web en el formulario.</span><span class="sxs-lookup"><span data-stu-id="1e531-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="1e531-104">Cuando se hace clic en el vínculo, puede cambiar su color para indicar que se ha visitado el vínculo.</span><span class="sxs-lookup"><span data-stu-id="1e531-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="1e531-105">Para obtener más información sobre cómo cambiar el color, vea [Cómo: cambiar la apariencia del control LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="1e531-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="1e531-106">Vincular a otro formulario</span><span class="sxs-lookup"><span data-stu-id="1e531-106">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="1e531-107">Para vincular a otro formulario con un control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="1e531-107">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="1e531-108">Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A> en un título adecuado.</span><span class="sxs-lookup"><span data-stu-id="1e531-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="1e531-109">Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte del título se indicará como un vínculo.</span><span class="sxs-lookup"><span data-stu-id="1e531-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="1e531-110">La forma en que se indique depende de las propiedades relacionadas con la apariencia de la etiqueta de vínculo.</span><span class="sxs-lookup"><span data-stu-id="1e531-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="1e531-111">El valor <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se representa mediante un objeto <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> que contiene dos números, la posición del carácter inicial y el número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1e531-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="1e531-112">La propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se puede establecer en el ventana Propiedades o en el código de una manera similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e531-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

    ```vb
    ' In this code example, the link area has been set to begin
    ' at the first character and extend for eight characters.
    ' You may need to modify this based on the text entered in Step 1.
    LinkLabel1.LinkArea = New LinkArea(0, 8)
    ```

    ```csharp
    // In this code example, the link area has been set to begin
    // at the first character and extend for eight characters.
    // You may need to modify this based on the text entered in Step 1.
    linkLabel1.LinkArea = new LinkArea(0,8);
    ```

    ```cpp
    // In this code example, the link area has been set to begin
    // at the first character and extend for eight characters.
    // You may need to modify this based on the text entered in Step 1.
    linkLabel1->LinkArea = LinkArea(0,8);
    ```

3. <span data-ttu-id="1e531-113">En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, invoque el método <xref:System.Windows.Forms.Form.Show%2A> para abrir otro formulario del proyecto y establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="1e531-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e531-114">Una instancia de la clase <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> incluye una referencia al control <xref:System.Windows.Forms.LinkLabel> en el que se ha hecho clic, por lo que no es necesario convertir el objeto `sender`.</span><span class="sxs-lookup"><span data-stu-id="1e531-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

    ```vb
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _
       Handles LinkLabel1.LinkClicked
       ' Show another form.
       Dim f2 As New Form()
       f2.Show
       LinkLabel1.LinkVisited = True
    End Sub
    ```

    ```csharp
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)
    {
       // Show another form.
       Form f2 = new Form();
       f2.Show();
       linkLabel1.LinkVisited = true;
    }
    ```

    ```cpp
    private:
       void linkLabel1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)
       {
          // Show another form.
          Form ^ f2 = new Form();
          f2->Show();
          linkLabel1->LinkVisited = true;
       }
    ```

## <a name="linking-to-a-web-page"></a><span data-ttu-id="1e531-115">Vincular a una página web</span><span class="sxs-lookup"><span data-stu-id="1e531-115">Linking to a Web Page</span></span>

<span data-ttu-id="1e531-116">También se puede usar el control <xref:System.Windows.Forms.LinkLabel> para mostrar una página web con el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e531-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="1e531-117">Para iniciar Internet Explorer y vincular a una página web con un control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="1e531-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="1e531-118">Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A> en un título adecuado.</span><span class="sxs-lookup"><span data-stu-id="1e531-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="1e531-119">Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte del título se indicará como un vínculo.</span><span class="sxs-lookup"><span data-stu-id="1e531-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="1e531-120">En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, en medio de un bloque de control de excepciones, llame a un segundo procedimiento que establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true` y use el método <xref:System.Diagnostics.Process.Start%2A> para iniciar el explorador predeterminado con una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="1e531-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="1e531-121">Para usar el método <xref:System.Diagnostics.Process.Start%2A> debe agregar una referencia al espacio de nombres <xref:System.Diagnostics?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e531-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1e531-122">Si el código siguiente se ejecuta en un entorno de confianza parcial (por ejemplo, en una unidad compartida), se produce un error en el compilador JIT cuando se llama al método `VisitLink`.</span><span class="sxs-lookup"><span data-stu-id="1e531-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="1e531-123">La instrucción `System.Diagnostics.Process.Start` produce una petición de vínculo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="1e531-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="1e531-124">Al detectar la excepción cuando se llama al método `VisitLink`, el código siguiente garantiza que, si se produce un error en el compilador JIT, el error se administra correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e531-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

    ```vb
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _
       Handles LinkLabel1.LinkClicked
       Try
          VisitLink()
       Catch ex As Exception
          ' The error message
          MessageBox.Show("Unable to open link that was clicked.")
       End Try
    End Sub

    Sub VisitLink()
       ' Change the color of the link text by setting LinkVisited
       ' to True.
       LinkLabel1.LinkVisited = True
       ' Call the Process.Start method to open the default browser
       ' with a URL:
       System.Diagnostics.Process.Start("http://www.microsoft.com")
    End Sub
    ```

    ```csharp
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
    {
       try
       {
          VisitLink();
       }
       catch (Exception ex )
       {
          MessageBox.Show("Unable to open link that was clicked.");
       }
    }

    private void VisitLink()
    {
       // Change the color of the link text by setting LinkVisited
       // to true.
       linkLabel1.LinkVisited = true;
       //Call the Process.Start method to open the default browser
       //with a URL:
       System.Diagnostics.Process.Start("http://www.microsoft.com");
    }
    ```

    ```cpp
    private:
       void linkLabel1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)
       {
          try
          {
             VisitLink();
          }
          catch (Exception ^ ex)
          {
             MessageBox::Show("Unable to open link that was clicked.");
          }
       }
    private:
       void VisitLink()
       {
          // Change the color of the link text by setting LinkVisited
          // to true.
          linkLabel1->LinkVisited = true;
          // Call the Process.Start method to open the default browser
          // with a URL:
          System::Diagnostics::Process::Start("http://www.microsoft.com");
       }
    ```

## <a name="see-also"></a><span data-ttu-id="1e531-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e531-125">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1e531-126">Información general sobre el control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="1e531-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="1e531-127">Cambiar la apariencia del control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e531-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="1e531-128">LinkLabel (control)</span><span class="sxs-lookup"><span data-stu-id="1e531-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
