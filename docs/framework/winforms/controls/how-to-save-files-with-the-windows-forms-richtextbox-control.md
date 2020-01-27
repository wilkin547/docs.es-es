---
title: Guardar archivos con el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744823"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a3f36-102">Cómo: Guardar archivos con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3f36-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="a3f36-103">El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms puede escribir la información que se muestra en uno de varios formatos:</span><span class="sxs-lookup"><span data-stu-id="a3f36-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="a3f36-104">Texto sin formato</span><span class="sxs-lookup"><span data-stu-id="a3f36-104">Plain text</span></span>

- <span data-ttu-id="a3f36-105">Texto sin formato Unicode</span><span class="sxs-lookup"><span data-stu-id="a3f36-105">Unicode plain text</span></span>

- <span data-ttu-id="a3f36-106">Formato de texto enriquecido (RTF)</span><span class="sxs-lookup"><span data-stu-id="a3f36-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="a3f36-107">RTF con espacios en lugar de objetos OLE</span><span class="sxs-lookup"><span data-stu-id="a3f36-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="a3f36-108">Texto sin formato con una representación textual de objetos OLE</span><span class="sxs-lookup"><span data-stu-id="a3f36-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="a3f36-109">Para guardar un archivo, llame al método <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3f36-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="a3f36-110">También puede utilizar el método **SaveFile** para guardar los datos en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a3f36-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="a3f36-111">Para obtener más información, vea <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="a3f36-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="a3f36-112">Para guardar el contenido del control en un archivo</span><span class="sxs-lookup"><span data-stu-id="a3f36-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="a3f36-113">Determine la ruta de acceso del archivo que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="a3f36-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="a3f36-114">Para hacer esto en una aplicación real, normalmente usaría el componente <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="a3f36-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="a3f36-115">Para obtener información general, consulte [información general sobre el componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a3f36-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="a3f36-116">Llame al método <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> del control <xref:System.Windows.Forms.RichTextBox>, especificando el archivo que se va a guardar y, opcionalmente, un tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="a3f36-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="a3f36-117">Si llama al método con un nombre de archivo como su único argumento, el archivo se guardará como RTF.</span><span class="sxs-lookup"><span data-stu-id="a3f36-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="a3f36-118">Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="a3f36-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="a3f36-119">En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto enriquecido es la carpeta **Mis documentos** .</span><span class="sxs-lookup"><span data-stu-id="a3f36-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="a3f36-120">Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="a3f36-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a3f36-121">La elección de esta ubicación también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="a3f36-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a3f36-122">En el ejemplo siguiente se supone que ya se ha agregado un formulario con un control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a3f36-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="a3f36-123">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="a3f36-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a3f36-124">Si una aplicación necesita crear un archivo, la aplicación necesita acceso de creación para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="a3f36-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="a3f36-125">Los permisos se establecen usando listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="a3f36-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="a3f36-126">Si el archivo ya existe, la aplicación solo necesita acceso de escritura, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="a3f36-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="a3f36-127">Siempre que sea posible, es más seguro crear el archivo durante la implementación y conceder solo acceso de lectura a un solo archivo, en lugar de crear acceso para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="a3f36-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="a3f36-128">Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="a3f36-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3f36-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3f36-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a3f36-130">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="a3f36-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a3f36-131">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3f36-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
