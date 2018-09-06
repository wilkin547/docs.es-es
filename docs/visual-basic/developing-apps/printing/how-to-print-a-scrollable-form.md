---
title: 'Cómo: Imprimir un formulario con desplazamiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 4a509b7c48f2bff705bc95e58fb88252cb8ca4b9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779424"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a>Cómo: Imprimir un formulario con desplazamiento (Visual Basic)
El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario sin usar un componente <xref:System.Drawing.Printing.PrintDocument> . De forma predeterminada, se imprime solo la parte visible del formulario; si un usuario cambió el tamaño del formulario en tiempo de ejecución, es posible que la imagen no se imprima según lo previsto. El siguiente procedimiento muestra cómo imprimir el área de cliente completa de un formulario con desplazamiento, aunque se haya cambiado el tamaño del formulario.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [centro de descarga de](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a>Para imprimir el área de cliente completa de un formulario con desplazamiento  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agregará a la bandeja de componentes.  
  
2.  En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  En algunos sistemas operativos, es posible que el texto o los gráficos dibujados por métodos <xref:System.Drawing.Graphics> no se impriman correctamente. En este caso, no podrá imprimir con el parámetro `Scrollable` .  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [PrintForm (componente)](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [Imprimir el área de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [Imprimir áreas de cliente y áreas que no son de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
