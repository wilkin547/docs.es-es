---
title: Procedimiento para guardar archivos con el control RichTextBox de formularios Windows Forms
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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318421"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Procedimiento para guardar archivos con el control RichTextBox de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control puede escribir la información que se muestra en uno de los siguientes formatos:  
  
-   Texto sin formato  
  
-   Texto sin formato Unicode  
  
-   Formato de texto enriquecido (RTF)  
  
-   RTF con espacios en lugar de objetos OLE  
  
-   Texto sin formato con una representación textual de objetos OLE  
  
 Para guardar un archivo, llame a la <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método. También puede usar el **SaveFile** método para guardar los datos en una secuencia. Para obtener más información, consulta <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Para guardar el contenido del control en un archivo  
  
1. Determinar la ruta de acceso del archivo que se guardarán.  
  
     Para hacer esto en una aplicación real, normalmente usaría el <xref:System.Windows.Forms.SaveFileDialog> componente. Para obtener información general, consulte [información general del componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).  
  
2. Llame a la <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método de la <xref:System.Windows.Forms.RichTextBox> control, especifique el archivo para guardar y, opcionalmente, un tipo de archivo. Si llama al método con un nombre de archivo como único argumento, el archivo se guardará como RTF. Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.  
  
     En el ejemplo siguiente, establezca la ruta de acceso para la ubicación del archivo de texto enriquecido es el **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecutan el sistema operativo de Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control ya se ha agregado.  
  
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
    >  En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación necesita crear un archivo, precisará acceso de creación para la carpeta. Los permisos se establecen usando listas de control de acceso. Si el archivo ya existe, la aplicación necesitará solo acceso de escritura, un privilegio menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y únicamente conceda acceso de lectura a un único archivo, en lugar de acceso de creación para una carpeta. Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
