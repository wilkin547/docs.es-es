---
title: "Cómo: Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c942cb5f005177b74dd25a9725b4990553adbb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="49d4d-102">Cómo: Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="49d4d-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="49d4d-103">Aunque puede establecer opciones relacionadas con la impresión en tiempo de diseño, en ocasiones, deseará cambiar estas opciones en tiempo de ejecución, probablemente debido a las opciones elegidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="49d4d-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="49d4d-104">Puede capturar proporcionados por el usuario para imprimir un documento utilizando el <xref:System.Windows.Forms.PrintDialog> y <xref:System.Drawing.Printing.PrintDocument> componentes.</span><span class="sxs-lookup"><span data-stu-id="49d4d-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="49d4d-105">Para cambiar las opciones de impresión mediante programación</span><span class="sxs-lookup"><span data-stu-id="49d4d-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="49d4d-106">Agregar un <xref:System.Windows.Forms.PrintDialog> y un <xref:System.Drawing.Printing.PrintDocument> al formulario.</span><span class="sxs-lookup"><span data-stu-id="49d4d-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="49d4d-107">Establecer el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad de la <xref:System.Windows.Forms.PrintDialog> a la <xref:System.Drawing.Printing.PrintDocument> agrega al formulario.</span><span class="sxs-lookup"><span data-stu-id="49d4d-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="49d4d-108">Mostrar la <xref:System.Windows.Forms.PrintDialog> componente mediante el uso de la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="49d4d-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="49d4d-109">Opciones de impresión del usuario en el cuadro de diálogo se copiarán en la <xref:System.Drawing.Printing.PrinterSettings> propiedad de la <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="49d4d-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d4d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="49d4d-110">See Also</span></span>  
 [<span data-ttu-id="49d4d-111">Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49d4d-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="49d4d-112">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="49d4d-112">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)</span></span>
