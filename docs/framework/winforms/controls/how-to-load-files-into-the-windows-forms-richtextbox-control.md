---
title: Cargar archivos en el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: c31e004ea4cd0821b5f18f0ab0fe2708e6ac4b59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736285"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="05d02-102">Cómo: Cargar archivos en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="05d02-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="05d02-103">El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms puede mostrar un archivo de texto sin formato, un archivo de texto sin formato Unicode o un archivo de formato de texto enriquecido (RTF).</span><span class="sxs-lookup"><span data-stu-id="05d02-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="05d02-104">Para ello, llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> .</span><span class="sxs-lookup"><span data-stu-id="05d02-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="05d02-105">También puede usar el método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> para cargar los datos desde una secuencia.</span><span class="sxs-lookup"><span data-stu-id="05d02-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="05d02-106">Para más información, consulte <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="05d02-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="05d02-107">Para cargar un archivo en el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="05d02-107">To load a file into the RichTextBox control</span></span>

1. <span data-ttu-id="05d02-108">Determine la ruta de acceso del archivo que quiere abrir con el componente <xref:System.Windows.Forms.OpenFileDialog> .</span><span class="sxs-lookup"><span data-stu-id="05d02-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="05d02-109">Para obtener información general, vea [información general sobre el componente OpenFileDialog](openfiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="05d02-109">For an overview, see [OpenFileDialog Component Overview](openfiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="05d02-110">Llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> del control <xref:System.Windows.Forms.RichTextBox> especificando el archivo que se va a cargar y, si quiere, un tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="05d02-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="05d02-111">En el siguiente ejemplo, el archivo que se va a cargar se toma de la propiedad <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.FileDialog.FileName%2A> .</span><span class="sxs-lookup"><span data-stu-id="05d02-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="05d02-112">Si llama al método con un nombre de archivo como único argumento, se presupondrá que el tipo de archivo es RTF.</span><span class="sxs-lookup"><span data-stu-id="05d02-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="05d02-113">Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="05d02-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="05d02-114">En el siguiente ejemplo, el componente <xref:System.Windows.Forms.OpenFileDialog> aparece cuando se hace clic en un botón.</span><span class="sxs-lookup"><span data-stu-id="05d02-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="05d02-115">Después, el archivo seleccionado se abre y se muestra en el control <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="05d02-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="05d02-116">En este ejemplo se presupone que un formulario tiene un botón,`btnOpenFile`.</span><span class="sxs-lookup"><span data-stu-id="05d02-116">This example assumes a form has a button,`btnOpenFile`.</span></span>

    ```vb
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _
       ByVal e As System.EventArgs) Handles btnOpenFile.Click
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _
              RichTextBoxStreamType.RichText)
          End If
    End Sub
    ```

    ```csharp
    private void btnOpenFile_Click(object sender, System.EventArgs e)
    {
       if(openFileDialog1.ShowDialog() == DialogResult.OK)
       {
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);
       }
    }
    ```

    ```cpp
    private:
       void btnOpenFile_Click(System::Object ^  sender,
          System::EventArgs ^  e)
       {
          if(openFileDialog1->ShowDialog() == DialogResult::OK)
          {
             richTextBox1->LoadFile(openFileDialog1->FileName,
                RichTextBoxStreamType::RichText);
          }
       }
    ```

    <span data-ttu-id="05d02-117">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="05d02-117">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

    ```csharp
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);
    ```

    ```cpp
    this->btnOpenFile->Click += gcnew
       System::EventHandler(this, &Form1::btnOpenFile_Click);
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="05d02-118">Para ejecutar este proceso, es posible que el ensamblado necesite un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05d02-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="05d02-119">Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="05d02-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="05d02-120">Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="05d02-120">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05d02-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05d02-121">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="05d02-122">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="05d02-122">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="05d02-123">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="05d02-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
