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
ms.openlocfilehash: c5d88e4942d96ee12e8b9f40156090c874386668
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046265"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Procedimiento para guardar archivos con el control RichTextBox de formularios Windows Forms

El control <xref:System.Windows.Forms.RichTextBox> Windows Forms puede escribir la información que se muestra en uno de varios formatos:

- Texto sin formato

- Texto sin formato Unicode

- Formato de texto enriquecido (RTF)

- RTF con espacios en lugar de objetos OLE

- Texto sin formato con una representación textual de objetos OLE

Para guardar un archivo, llame al <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método. También puede utilizar el método **SaveFile** para guardar los datos en una secuencia. Para obtener más información, consulta <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Para guardar el contenido del control en un archivo

1. Determine la ruta de acceso del archivo que se va a guardar.

    Para hacer esto en una aplicación real, normalmente usaría el <xref:System.Windows.Forms.SaveFileDialog> componente. Para obtener información general, consulte [información general sobre el componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).

2. Llame al <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> método <xref:System.Windows.Forms.RichTextBox> del control, especificando el archivo que se va a guardar y, opcionalmente, un tipo de archivo. Si llama al método con un nombre de archivo como su único argumento, el archivo se guardará como RTF. Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.

    En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto enriquecido es la carpeta **Mis documentos** . Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura. En el ejemplo siguiente se supone que ya <xref:System.Windows.Forms.RichTextBox> se ha agregado un formulario con un control.

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
    > En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación necesita crear un archivo, la aplicación necesita acceso de creación para la carpeta. Los permisos se establecen usando listas de control de acceso. Si el archivo ya existe, la aplicación solo necesita acceso de escritura, un privilegio menor. Siempre que sea posible, es más seguro crear el archivo durante la implementación y conceder solo acceso de lectura a un solo archivo, en lugar de crear acceso para una carpeta. Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
