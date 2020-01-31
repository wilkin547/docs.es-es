---
title: Imprimir con la vista previa de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: 1975c902fdb56326c763f2e2fc11e381ffc7fbd3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740608"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a>Cómo: Imprimir en Windows Forms a través de la vista previa de impresión
Es muy habitual en la programación de Windows Forms ofrecer una vista previa de impresión además de los servicios de impresión. Una forma sencilla de agregar servicios de vista previa de impresión a la aplicación es usar un control <xref:System.Windows.Forms.PrintPreviewDialog> en combinación con la lógica de control de eventos de <xref:System.Drawing.Printing.PrintDocument.PrintPage> para imprimir un archivo.  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a>Para mostrar una vista previa de un documento de texto con un control PrintPreviewDialog  
  
1. Agregue un <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, y dos cadenas al formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. Establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> en el documento que quiere imprimir y abra y lea el contenido del documento en la cadena que agregó previamente.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. Igual que haría para imprimir el documento, en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage> , use la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> y el contenido del archivo para calcular las líneas por página y representar el contenido del documento. Una vez dibujada cada página, compruebe si es la última página y establezca la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> de <xref:System.Drawing.Printing.PrintPageEventArgs> como corresponda. El evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> se produce hasta que <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> es `false`. Cuando el documento haya terminado de representarse, restablezca la cadena que se va a representar. Además, asegúrese de que el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> está asociado con su método de control de eventos.  
  
    > [!NOTE]
    > Puede que ya haya completado los pasos 2 y 3 si ha implementado la impresión en la aplicación.  
  
     En el ejemplo de código siguiente, se usa el controlador de eventos para imprimir el archivo "testPage.txt" con la misma fuente que se usa en el formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. Establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> del control <xref:System.Windows.Forms.PrintPreviewDialog> en el componente <xref:System.Drawing.Printing.PrintDocument> del formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. Llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> en el control <xref:System.Windows.Forms.PrintPreviewDialog> . Normalmente se llamaría a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> desde el método de control de eventos <xref:System.Windows.Forms.Control.Click> de un botón. Al llamar a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> se genera el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se representa en el control <xref:System.Windows.Forms.PrintPreviewDialog> . Cuando el usuario hace clic en el icono de impresión del cuadro de diálogo, se vuelve a generar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se envía a la impresora en lugar de al cuadro de diálogo de vista previa. Este es el motivo por el que la cadena se restablece al final del proceso de representación en el paso 3.  
  
     En el siguiente ejemplo de código se muestra el método de control de eventos <xref:System.Windows.Forms.Control.Click> para un botón del formulario. Este método de control de eventos llama a los métodos para leer el documento y mostrar el cuadro de diálogo de vista previa de impresión.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Windows.Forms, System.Drawing.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [Impresión más segura en Windows Forms](../more-secure-printing-in-windows-forms.md)
