---
title: "C&#243;mo: Imprimir en Windows Forms a trav&#233;s de la vista previa de impresi&#243;n | Microsoft Docs"
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
  - "imprimir [Windows Forms], usar vista previa de impresión"
  - "imprimir, con vista previa de impresión"
  - "vista previa de impresión"
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Imprimir en Windows Forms a trav&#233;s de la vista previa de impresi&#243;n
Es muy habitual en la programación de Windows Forms ofrecer una vista previa de impresión además de los servicios de impresión. Una forma sencilla de agregar servicios de vista previa de impresión a la aplicación es usar un control <xref:System.Windows.Forms.PrintPreviewDialog> en combinación con la lógica de control de eventos de <xref:System.Drawing.Printing.PrintDocument.PrintPage> para imprimir un archivo.  
  
### Para mostrar una vista previa de un documento de texto con un control PrintPreviewDialog  
  
1.  Agregue un <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, y dos cadenas al formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2.  Establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> en el documento que quiere imprimir y abra y lea el contenido del documento en la cadena que agregó previamente.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3.  Igual que haría para imprimir el documento, en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>, use la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> y el contenido del archivo para calcular las líneas por página y representar el contenido del documento. Una vez dibujada cada página, compruebe si es la última página y establezca la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> de <xref:System.Drawing.Printing.PrintPageEventArgs> como corresponda. El evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> se produce hasta que <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> es `false`. Cuando el documento haya terminado de representarse, restablezca la cadena que se va a representar. Además, asegúrese de que el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> está asociado con su método de control de eventos.  
  
    > [!NOTE]
    >  Puede que ya haya completado los pasos 2 y 3 si ha implementado la impresión en la aplicación.  
  
     En el ejemplo de código siguiente, se usa el controlador de eventos para imprimir el archivo "testPage.txt" con la misma fuente que se usa en el formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> del control <xref:System.Windows.Forms.PrintPreviewDialog> en el componente <xref:System.Drawing.Printing.PrintDocument> del formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5.  Llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> en el control <xref:System.Windows.Forms.PrintPreviewDialog>. Normalmente se llamaría a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> desde el método de control de eventos <xref:System.Windows.Forms.Control.Click> de un botón. Al llamar a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> se genera el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se representa en el control <xref:System.Windows.Forms.PrintPreviewDialog>. Cuando el usuario hace clic en el icono de impresión del cuadro de diálogo, se vuelve a generar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se envía a la impresora en lugar de al cuadro de diálogo de vista previa. Este es el motivo por el que la cadena se restablece al final del proceso de representación en el paso 3.  
  
     En el siguiente ejemplo de código se muestra el método de control de eventos <xref:System.Windows.Forms.Control.Click> para un botón del formulario. Este método de control de eventos llama a los métodos para leer el documento y mostrar el cuadro de diálogo de vista previa de impresión.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## Ejemplo  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Windows.Forms, System.Drawing.  
  
-   Para obtener más información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [More Secure Printing in Windows Forms](../../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)