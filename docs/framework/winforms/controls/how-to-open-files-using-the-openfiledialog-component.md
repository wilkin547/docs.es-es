---
title: "Cómo: Abrir archivos mediante el componente OpenFileDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fabe176ade1ae94a20100162ab7ab6fadfb2999f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="99982-102">Cómo: Abrir archivos mediante el componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="99982-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="99982-103">El <xref:System.Windows.Forms.OpenFileDialog> componente permite a los usuarios examinar las carpetas de su equipo o en cualquier equipo en la red y seleccionar uno o más archivos para abrirlos.</span><span class="sxs-lookup"><span data-stu-id="99982-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="99982-104">El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que seleccionó el usuario en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99982-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="99982-105">Cuando el usuario haya seleccionado el archivo que se abrirá, hay dos enfoques para el mecanismo de apertura del archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="99982-106">Si prefiere trabajar con secuencias de archivo, puede crear una instancia de la <xref:System.IO.StreamReader> clase.</span><span class="sxs-lookup"><span data-stu-id="99982-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="99982-107">Como alternativa, puede usar el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="99982-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="99982-108">El primer ejemplo siguiente implica un <xref:System.Security.Permissions.FileIOPermission> comprobación del permiso (como se describe en la "Nota de seguridad" más abajo), pero proporciona acceso al nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="99982-109">Puede usar esta técnica desde las zonas de máquina local, intranet e Internet.</span><span class="sxs-lookup"><span data-stu-id="99982-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="99982-110">El segundo método también realiza una <xref:System.Security.Permissions.FileIOPermission> comprobación del permiso, pero es más adecuado para las aplicaciones en las zonas de Intranet o Internet.</span><span class="sxs-lookup"><span data-stu-id="99982-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="99982-111">Abrir archivos como secuencia mediante el componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="99982-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="99982-112">Muestre el cuadro de diálogo **Abrir archivo** y llame a un método para abrir el archivo seleccionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="99982-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="99982-113">Un enfoque consiste en usar la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo Abrir archivo y utilizar una instancia de la <xref:System.IO.StreamReader> clase para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="99982-114">El ejemplo siguiente utiliza la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos para abrir una instancia de la <xref:System.Windows.Forms.OpenFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="99982-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="99982-115">Cuando se elige un archivo y el usuario hace clic en **Aceptar**, se abre el archivo seleccionado en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99982-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="99982-116">En este caso, el contenido se muestra en un cuadro de mensaje para mostrar que se leyó la secuencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="99982-117">Para obtener o establecer el <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="99982-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="99982-118">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="99982-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="99982-119">Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="99982-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="99982-120">En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control y un <xref:System.Windows.Forms.OpenFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="99982-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     <span data-ttu-id="99982-121">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="99982-121">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="99982-122">Para obtener más información sobre la lectura de secuencias de archivo, consulte <xref:System.IO.FileStream.BeginRead%2A> y <xref:System.IO.FileStream.Read%2A>.</span><span class="sxs-lookup"><span data-stu-id="99982-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="99982-123">Abrir archivos como archivo mediante el componente OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="99982-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="99982-124">Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo y el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="99982-125">El <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método devuelve los bytes que componen el archivo.</span><span class="sxs-lookup"><span data-stu-id="99982-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="99982-126">Estos bytes proporcionan una secuencia de la que se puede leer.</span><span class="sxs-lookup"><span data-stu-id="99982-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="99982-127">En el ejemplo siguiente, un <xref:System.Windows.Forms.OpenFileDialog> se crea una instancia de componente con un filtro "cursor", lo que permite al usuario elegir únicamente archivos con la extensión de nombre de archivo`.cur`.</span><span class="sxs-lookup"><span data-stu-id="99982-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="99982-128">Si se elige un archivo`.cur`, el cursor del formulario se establece en el cursor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="99982-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="99982-129">Para llamar a la <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="99982-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="99982-130">Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="99982-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="99982-131">Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="99982-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="99982-132">En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="99982-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     <span data-ttu-id="99982-133">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="99982-133">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="99982-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="99982-134">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="99982-135">OpenFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="99982-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
