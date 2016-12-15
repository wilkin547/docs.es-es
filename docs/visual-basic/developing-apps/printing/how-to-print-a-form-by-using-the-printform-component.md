---
title: "C&#243;mo: Imprimir un formulario mediante el componente PrintForm (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Formulario, impresión"
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Imprimir un formulario mediante el componente PrintForm (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario, tal y como aparece en pantalla sin usar un componente <xref:System.Drawing.Printing.PrintDocument>. Los procedimientos siguientes muestran cómo imprimir un formulario en una impresora, una ventana de vista previa de impresión y un archivo PostScript encapsulado.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### Para imprimir un formulario en la impresora predeterminada  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado \(por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### Para visualizar un formulario en una ventana de vista previa de impresión  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Agregue el siguiente código al controlador de eventos adecuado \(por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### Para imprimir un formulario en un archivo  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Opcionalmente, seleccione la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> y escriba la ruta de acceso completa y nombre del archivo de destino.  
  
     Si omite este paso, se pedirá al usuario un nombre de archivo en tiempo de ejecución.  
  
4.  Agregue el siguiente código al controlador de eventos adecuado \(por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`\).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>   
 [Cómo: Imprimir el área de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)   
 [Cómo: Imprimir áreas de cliente y áreas que no son de cliente de un formulario](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)   
 [Cómo: Imprimir un formulario con desplazamiento](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)