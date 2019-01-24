---
title: Procedimiento Imprimir un formulario mediante el componente PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 0a1a62627390c8839625862b9d43d61fc07ebf12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521574"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a>Procedimiento Imprimir un formulario mediante el componente PrintForm (Visual Basic)
El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario, tal y como aparece en pantalla sin usar un componente <xref:System.Drawing.Printing.PrintDocument> . Los procedimientos siguientes muestran cómo imprimir un formulario en una impresora, una ventana de vista previa de impresión y un archivo PostScript encapsulado.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-a-form-to-the-default-printer"></a>Para imprimir un formulario en la impresora predeterminada  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a>Para visualizar un formulario en una ventana de vista previa de impresión  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a>Para imprimir un formulario en un archivo  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToFile>.  
  
3.  Opcionalmente, seleccione la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> y escriba la ruta de acceso completa y nombre del archivo de destino.  
  
     Si omite este paso, se pedirá al usuario un nombre de archivo en tiempo de ejecución.  
  
4.  Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>
- [Cómo: Imprimir el área de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [Cómo: Imprimir áreas de cliente y áreas que no son de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [Cómo: Imprimir un formulario desplazable](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
- [PrintForm (componente)](../../../visual-basic/developing-apps/printing/printform-component.md)
