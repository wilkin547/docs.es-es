---
title: Filtrar para guardar archivos con el control RichTextBox de formularios Windows Forms
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
ms.openlocfilehash: 4784ddd563ccec0f7e6271700781ee1b5d3ac105
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318421"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="1a28d-102">Filtrar para guardar archivos con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a28d-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="1a28d-103">Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control puede escribir la información que se muestra en uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="1a28d-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="1a28d-104">Texto sin formato</span><span class="sxs-lookup"><span data-stu-id="1a28d-104">Plain text</span></span>  
  
-   <span data-ttu-id="1a28d-105">Texto sin formato Unicode</span><span class="sxs-lookup"><span data-stu-id="1a28d-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="1a28d-106">Formato de texto enriquecido (RTF)</span><span class="sxs-lookup"><span data-stu-id="1a28d-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="1a28d-107">RTF con espacios en lugar de objetos OLE</span><span class="sxs-lookup"><span data-stu-id="1a28d-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="1a28d-108">Texto sin formato con una representación textual de objetos OLE</span><span class="sxs-lookup"><span data-stu-id="1a28d-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="1a28d-109">Para guardar un archivo, llame a la <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1a28d-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="1a28d-110">También puede usar el **SaveFile** método para guardar los datos en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="1a28d-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="1a28d-111">Para obtener más información, consulta <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="1a28d-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="1a28d-112">Para guardar el contenido del control en un archivo</span><span class="sxs-lookup"><span data-stu-id="1a28d-112">To save the contents of the control to a file</span></span>  
  
1. <span data-ttu-id="1a28d-113">Determinar la ruta de acceso del archivo que se guardarán.</span><span class="sxs-lookup"><span data-stu-id="1a28d-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="1a28d-114">Para hacer esto en una aplicación real, normalmente usaría el <xref:System.Windows.Forms.SaveFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="1a28d-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="1a28d-115">Para obtener información general, consulte [información general del componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1a28d-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="1a28d-116">Llame a la <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método de la <xref:System.Windows.Forms.RichTextBox> control, especifique el archivo para guardar y, opcionalmente, un tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="1a28d-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="1a28d-117">Si llama al método con un nombre de archivo como único argumento, el archivo se guardará como RTF.</span><span class="sxs-lookup"><span data-stu-id="1a28d-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="1a28d-118">Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="1a28d-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="1a28d-119">En el ejemplo siguiente, establezca la ruta de acceso para la ubicación del archivo de texto enriquecido es el **Mis documentos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="1a28d-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="1a28d-120">Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecutan el sistema operativo de Windows incluirá esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="1a28d-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="1a28d-121">Al elegir esta ubicación también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="1a28d-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="1a28d-122">El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="1a28d-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
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
    >  <span data-ttu-id="1a28d-123">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="1a28d-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="1a28d-124">Si una aplicación necesita crear un archivo, precisará acceso de creación para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="1a28d-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="1a28d-125">Los permisos se establecen usando listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="1a28d-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="1a28d-126">Si el archivo ya existe, la aplicación necesitará solo acceso de escritura, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="1a28d-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="1a28d-127">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y únicamente conceda acceso de lectura a un único archivo, en lugar de acceso de creación para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="1a28d-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="1a28d-128">Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="1a28d-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a28d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a28d-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="1a28d-130">Control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="1a28d-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="1a28d-131">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a28d-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
