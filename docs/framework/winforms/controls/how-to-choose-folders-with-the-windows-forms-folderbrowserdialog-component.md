---
title: "C&#243;mo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms | Microsoft Docs"
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
  - "directorios [Windows Forms], elegir"
  - "directorios [Windows Forms], seleccionar"
  - "FolderBrowserDialog (componente) [Windows Forms], elegir directorios"
  - "carpetas [Windows Forms], elegir"
  - "carpetas [Windows Forms], seleccionar"
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms
Con frecuencia, en las aplicaciones para Windows que cree, deberá pedir a los usuarios que seleccione una carpeta; en la mayoría de los casos para guardar un conjunto de archivos.  El componente <xref:System.Windows.Forms.FolderBrowserDialog> de formularios Windows Forms permite realizar esta tarea con facilidad.  
  
### Para elegir carpetas con el componente FolderBrowserDialog  
  
1.  En un procedimiento, compruebe la propiedad <xref:System.Windows.Forms.Form.DialogResult%2A>del componente <xref:System.Windows.Forms.FolderBrowserDialog> para ver cómo se cerró el cuadro de diálogo y obtener el valor de la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> del componente <xref:System.Windows.Forms.FolderBrowserDialog>.  
  
2.  Si necesita definir la carpeta de nivel más alto que aparecerá en la vista de árbol del cuadro de diálogo, establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, que toma el miembro de la enumeración [SpecialFolder](frlrfSystemEnvironmentSpecialFolderClassTopic).  
  
3.  Asimismo, puede definir la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>, que especifica la cadena de texto que aparece en la parte superior de la vista de árbol del explorador de carpetas.  
  
     En el ejemplo siguiente se utiliza el componente <xref:System.Windows.Forms.FolderBrowserDialog> para seleccionar una carpeta, de manera similar a cuando se crea un proyecto en Visual Studio y se le pide que seleccione una carpeta para guardarlo.  En este ejemplo, el nombre de carpeta se muestra después en un control <xref:System.Windows.Forms.TextBox> del formulario.  Es recomendable colocar la ubicación en un área modificable, como un control <xref:System.Windows.Forms.TextBox>, de manera que los usuarios puedan editar su selección en caso de error u otros problemas.  Este ejemplo supone un formulario con un componente <xref:System.Windows.Forms.FolderBrowserDialog> y un control <xref:System.Windows.Forms.TextBox>.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Para utilizar esta clase, el ensamblado requiere que la propiedad [FileIOPermissionAttribute.PathDiscoveryProperty](frlrfSystemSecurityPermissionsFileIOPermissionAttributeClassPathDiscoveryTopic), que forma parte de la enumeración <xref:System.Security.Permissions.FileIOPermissionAccess>, le conceda cierto nivel de privilegios..  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Para obtener información sobre cómo guardar archivos, vea [Cómo: Guardar archivos mediante el componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## Vea también  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Información general del componente FolderBrowserDialog \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)   
 [FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)