---
title: "How to: Complete Windows Forms Print Jobs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "print jobs, completing in Windows Forms"
  - "printing [Windows Forms], print jobs"
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# How to: Complete Windows Forms Print Jobs
Con frecuencia, los procesadores de texto y otras aplicaciones relacionadas con trabajos de impresión ofrecen la opción de mostrar un mensaje cuando se completa un trabajo de impresión.  Se puede proporcionar esta funcionalidad en los formularios Windows Forms mediante el control del evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 El procedimiento siguiente requiere que se haya creado una aplicación basada en Windows con un componente <xref:System.Drawing.Printing.PrintDocument> en ella, que es la forma estándar de permitir la impresión desde una aplicación basada en Windows.  Para obtener más información sobre el uso de la impresión desde formularios Windows Forms mediante el componente <xref:System.Drawing.Printing.PrintDocument>, vea [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### Para completar un trabajo de impresión  
  
1.  Establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.EndPrint>.  
  
     En el ejemplo siguiente se muestra un cuadro de mensaje, que indica que la impresión del documento ha terminado.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## Vea también  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)