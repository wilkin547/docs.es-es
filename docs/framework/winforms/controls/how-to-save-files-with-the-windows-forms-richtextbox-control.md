---
title: "C&#243;mo: Guardar archivos con el control RichTextBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - ".rtf (archivos), guardar en el control RichTextBox"
  - "ejemplos [Windows Forms], cuadros de texto"
  - "archivos, guardar con el control RichTextBox"
  - "RichTextBox (control) [Windows Forms], guardar archivos"
  - "RTF (archivos), guardar en el control RichTextBox"
  - "guardar archivos"
  - "guardar archivos, RichTextBox (control)"
  - "archivos de texto, guardar desde el control RichTextBox"
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Guardar archivos con el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms puede escribir la información que muestra en uno de los siguientes formatos:  
  
-   Texto sin formato  
  
-   Texto sin formato Unicode  
  
-   Formato de texto enriquecido \(RTF\)  
  
-   RTF con espacios en lugar de objetos OLE  
  
-   Texto sin formato con una representación textual de objetos OLE  
  
 Para guardar un archivo, llame al método <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>.  También puede utilizar el método **SaveFile** para guardar datos en una secuencia.  Para obtener más información, vea <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### Para guardar el contenido del control en un archivo  
  
1.  Determina la ruta de acceso del archivo que se va a guardar.  
  
     Para hacer esto en una aplicación real, lo habitual es utilizar el componente <xref:System.Windows.Forms.SaveFileDialog>.  Para obtener información general, vea [Información general sobre el componente SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Llame al método <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> del control <xref:System.Windows.Forms.RichTextBox>, y especifique el archivo que se guardará y, opcionalmente, un tipo de archivo.  Si llama al método con un nombre de archivo como único argumento, el archivo se guardará como RTF.  Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del archivo de texto enriquecido es la carpeta **Mis documentos**.  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán esta carpeta.  Al elegir esta ubicación, también se permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  En el ejemplo siguiente suponemos que ya se ha agregado un control <xref:System.Windows.Forms.RichTextBox> al formulario.  
  
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
    >  En este ejemplo se crea un nuevo archivo, si es que aún no existe.  Si una aplicación necesita crear un archivo, precisará acceso de creación para la carpeta correspondiente.  Los permisos se establecen usando listas de control de acceso.  Sin embargo, si el archivo ya existe, la aplicación sólo precisará acceso de escritura, un privilegio menor.  Por tanto, siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder sólo acceso de lectura para un único archivo, en lugar de acceso de creación para una carpeta.  También es más seguro escribir datos en carpetas de usuario en lugar de en la carpeta raíz o en la carpeta Archivos de programa.  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)