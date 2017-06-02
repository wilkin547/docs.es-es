---
title: "How to: Create Standard Windows Forms Print Jobs | Microsoft Docs"
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
  - "printing [Windows Forms]"
  - "printing [Windows Forms], creating print jobs"
  - "printing [Visual Basic], in Windows applications"
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Create Standard Windows Forms Print Jobs
La base de la impresión en formularios Windows Forms es el componente <xref:System.Drawing.Printing.PrintDocument> y, más específicamente, el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  Al escribir código de control para el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>, puede especificar qué se va a imprimir y cómo.  
  
### Para crear un trabajo de impresión  
  
1.  Agregue un componente <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2.  Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     Tendrá que codificar su propia lógica de impresión.  Además, deberá especificar qué material se va a imprimir.  
  
     En el ejemplo siguiente, se crea un gráfico de ejemplo con forma de rectángulo rojo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage> para que actúe como material para ser impreso.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Es posible que también desee escribir código para los eventos <xref:System.Drawing.Printing.PrintDocument.BeginPrint> y <xref:System.Drawing.Printing.PrintDocument.EndPrint>, quizá para incluir un entero que represente el número total de páginas que se van a imprimir y que se reduzca a medida que se impriman las páginas.  
  
    > [!NOTE]
    >  Puede agregar un componente <xref:System.Windows.Forms.PrintDialog> al formulario para proporcionar a los usuarios una interfaz limpia y eficaz.  Al establecer la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A> del componente <xref:System.Windows.Forms.PrintDialog>, se podrán establecer propiedades relacionadas con el documento de impresión con el que está trabajando.  Para obtener más información acerca del componente <xref:System.Windows.Forms.PrintDialog>, vea [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Para obtener más información específica acerca de los trabajos de impresión en formularios Windows Forms, incluido cómo crear un trabajo de impresión mediante programación, vea <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## Vea también  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)