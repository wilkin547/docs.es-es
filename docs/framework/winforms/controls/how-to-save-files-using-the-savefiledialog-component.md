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
ms.openlocfilehash: 4755d950da6726f007ae3333a558f3cafdcada9b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508165"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="cc7ff-102">Cómo: Guardar archivos mediante el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="cc7ff-102">How to: Save Files Using the SaveFileDialog Component</span></span>
<span data-ttu-id="cc7ff-103">El <xref:System.Windows.Forms.SaveFileDialog> componente permite a los usuarios examinar el sistema de archivos y seleccionar los archivos se guarden.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-103">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="cc7ff-104">El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que el usuario seleccionó en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-104">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="cc7ff-105">Sin embargo, debe escribir el código para escribir realmente los archivos en el disco.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-105">However, you must write the code to actually write the files to disk.</span></span>  
  
### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="cc7ff-106">Guardar un archivo mediante el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="cc7ff-106">To save a file using the SaveFileDialog component</span></span>  
  
-   <span data-ttu-id="cc7ff-107">Muestre el cuadro de diálogo **Guardar archivo** y llame a un método para guardar el archivo seleccionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-107">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>  
  
     <span data-ttu-id="cc7ff-108">Use la <xref:System.Windows.Forms.SaveFileDialog> del componente <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> método para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-108">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="cc7ff-109">Este método le proporciona un <xref:System.IO.Stream> puede escribir en el objeto.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-109">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>  
  
     <span data-ttu-id="cc7ff-110">El ejemplo siguiente usa el <xref:System.Windows.Forms.DialogResult> propiedad va a obtener el nombre del archivo y el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-110">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="cc7ff-111">El <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> método proporciona una secuencia para escribir el archivo.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-111">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>  
  
     <span data-ttu-id="cc7ff-112">En el ejemplo siguiente, hay un <xref:System.Windows.Forms.Button> control con una imagen asignada a él.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-112">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="cc7ff-113">Al hacer clic en el botón, un <xref:System.Windows.Forms.SaveFileDialog> se crea una instancia de componente con un filtro que permite que los archivos de tipo .gif, .jpeg y. bmp.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-113">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="cc7ff-114">Si se selecciona un archivo de este tipo en el cuadro de diálogo Guardar archivo, se guarda la imagen del botón.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-114">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc7ff-115">Para obtener o establecer el <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-115">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="cc7ff-116">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-116">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="cc7ff-117">Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="cc7ff-117">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="cc7ff-118">En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> controlar con su <xref:System.Windows.Forms.ButtonBase.Image%2A> propiedad establecida en un archivo de tipo .gif, .jpeg o. bmp.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-118">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc7ff-119">El <xref:System.Windows.Forms.FileDialog> la clase <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> propiedad (que, debido a la herencia, forma parte de la <xref:System.Windows.Forms.SaveFileDialog> clase) utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-119">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="cc7ff-120">Esto es importante si escribe código para guardar datos en un formato concreto (por ejemplo, al guardar un archivo de texto sin formato frente al formato binario).</span><span class="sxs-lookup"><span data-stu-id="cc7ff-120">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="cc7ff-121">Esta propiedad se incluye en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-121">This property is featured in the example below.</span></span>  
  
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
  
     <span data-ttu-id="cc7ff-122">(Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-122">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     <span data-ttu-id="cc7ff-123">Para obtener más información sobre cómo escribir secuencias de archivo, consulte <xref:System.IO.FileStream.BeginWrite%2A> y <xref:System.IO.FileStream.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-123">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc7ff-124">Ciertos controles, como el <xref:System.Windows.Forms.RichTextBox> controlar, tiene la capacidad de guardar archivos.</span><span class="sxs-lookup"><span data-stu-id="cc7ff-124">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span> <span data-ttu-id="cc7ff-125">Para obtener más información, consulte la sección "SaveFileDialog (componente)" del artículo técnico de MSDN Online Library, [Código esencial para los cuadros de diálogo de Windows Forms](https://go.microsoft.com/fwlink/?LinkID=102575).</span><span class="sxs-lookup"><span data-stu-id="cc7ff-125">For more information, see the "SaveFileDialog Component" section of the MSDN Online Library technical article, [Essential Code for Windows Forms Dialog Boxes](https://go.microsoft.com/fwlink/?LinkID=102575).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc7ff-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc7ff-126">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="cc7ff-127">SaveFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="cc7ff-127">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
