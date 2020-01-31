---
title: 'Cómo: Guardar archivos mediante el componente SaveFileDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: 32de7f7e38195271e179d4fae3884b7a39f37c45
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868088"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="daddf-102">Cómo: Guardar archivos mediante el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="daddf-102">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="daddf-103">El componente <xref:System.Windows.Forms.SaveFileDialog> permite a los usuarios examinar el sistema de archivos y seleccionar los archivos que se van a guardar.</span><span class="sxs-lookup"><span data-stu-id="daddf-103">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="daddf-104">El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que el usuario seleccionó en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daddf-104">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="daddf-105">Sin embargo, debe escribir el código para escribir realmente los archivos en el disco.</span><span class="sxs-lookup"><span data-stu-id="daddf-105">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="daddf-106">Guardar un archivo mediante el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="daddf-106">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="daddf-107">Muestre el cuadro de diálogo **Guardar archivo** y llame a un método para guardar el archivo seleccionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="daddf-107">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="daddf-108">Use el método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> del componente <xref:System.Windows.Forms.SaveFileDialog> para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="daddf-108">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="daddf-109">Este método proporciona un <xref:System.IO.Stream> objeto en el que se puede escribir.</span><span class="sxs-lookup"><span data-stu-id="daddf-109">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="daddf-110">En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Forms.DialogResult> para obtener el nombre del archivo y el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="daddf-110">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="daddf-111">El método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> proporciona una secuencia para escribir el archivo.</span><span class="sxs-lookup"><span data-stu-id="daddf-111">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="daddf-112">En el ejemplo siguiente, hay un control de <xref:System.Windows.Forms.Button> con una imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="daddf-112">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="daddf-113">Al hacer clic en el botón, se crea una instancia de un componente de <xref:System.Windows.Forms.SaveFileDialog> con un filtro que permite archivos de tipo. gif,. JPEG y. bmp.</span><span class="sxs-lookup"><span data-stu-id="daddf-113">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="daddf-114">Si se selecciona un archivo de este tipo en el cuadro de diálogo Guardar archivo, se guarda la imagen del botón.</span><span class="sxs-lookup"><span data-stu-id="daddf-114">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="daddf-115">Para obtener o establecer la propiedad <xref:System.Windows.Forms.FileDialog.FileName%2A>, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="daddf-115">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="daddf-116">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="daddf-116">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="daddf-117">Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="daddf-117">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="daddf-118">En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button> con su propiedad <xref:System.Windows.Forms.ButtonBase.Image%2A> establecida en un archivo de tipo. gif,. JPEG o. bmp.</span><span class="sxs-lookup"><span data-stu-id="daddf-118">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="daddf-119">La propiedad <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> de la clase <xref:System.Windows.Forms.FileDialog> (que, debido a la herencia, forma parte de la clase <xref:System.Windows.Forms.SaveFileDialog>) utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="daddf-119">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="daddf-120">Esto es importante si escribe código para guardar datos en un formato concreto (por ejemplo, al guardar un archivo de texto sin formato frente al formato binario).</span><span class="sxs-lookup"><span data-stu-id="daddf-120">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="daddf-121">Esta propiedad se incluye en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="daddf-121">This property is featured in the example below.</span></span>

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  <span data-ttu-id="daddf-122">(Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="daddf-122">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="daddf-123">Para obtener más información sobre cómo escribir secuencias de archivos, consulte <xref:System.IO.FileStream.BeginWrite%2A> y <xref:System.IO.FileStream.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="daddf-123">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="daddf-124">Algunos controles, como el control <xref:System.Windows.Forms.RichTextBox>, tienen la capacidad de guardar archivos.</span><span class="sxs-lookup"><span data-stu-id="daddf-124">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span>

## <a name="see-also"></a><span data-ttu-id="daddf-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="daddf-125">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="daddf-126">SaveFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="daddf-126">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
