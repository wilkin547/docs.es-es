---
title: 'Cómo: Imprimir el área de cliente de un formulario (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: b2f13d1ec151a5fd1967b522a601e0e19de04cbb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528163"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a>Cómo: Imprimir el área de cliente de un formulario (Visual Basic)
El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario sin usar un componente <xref:System.Drawing.Printing.PrintDocument> . El siguiente procedimiento muestra cómo imprimir solo el área de cliente de un formulario, sin la barra de título, los bordes ni las barras de desplazamiento.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [centro de descarga de](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-the-client-area-of-a-form"></a>Para imprimir el área de cliente de un formulario  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  En algunos sistemas operativos, es posible que el texto o los gráficos dibujados por métodos <xref:System.Drawing.Graphics> no se impriman correctamente. En este caso, use el método de impresión compatible: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [PrintForm (componente)](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [Imprimir áreas de cliente y áreas que no son de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [Imprimir un formulario desplazable](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
