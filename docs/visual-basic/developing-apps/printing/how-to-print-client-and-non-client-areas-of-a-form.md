---
title: "C&#243;mo: Imprimir &#225;reas de cliente y &#225;reas que no son de cliente de un formulario (Visual Basic) | Microsoft Docs"
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
  - "barra de título, impresión"
  - "imprimir"
  - "bordes, impresión"
  - "formulario completo"
  - "área que no es de cliente, impresión"
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Imprimir &#225;reas de cliente y &#225;reas que no son de cliente de un formulario (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario, tal y como aparece en pantalla sin usar un componente <xref:System.Drawing.Printing.PrintDocument>. El siguiente procedimiento muestra cómo imprimir un formulario, incluyendo el área de cliente y el área que no es de cliente. El área que no es de cliente incluye la barra de título, los bordes y las barras de desplazamiento.  
  
 Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### Para imprimir el área de cliente y el área que no es de cliente de un formulario  
  
1.  En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.  
  
     El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction>.  
  
3.  Agregue el siguiente código en el controlador de eventos apropiado \(por ejemplo, en el controlador de un evento `Click` de un control `Button` Imprimir\).  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  En algunos sistemas operativos, es posible que el texto o los gráficos dibujados por métodos <xref:System.Drawing.Graphics> no se impriman correctamente. En este caso, use el método de impresión compatible: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)   
 [Cómo: Imprimir un formulario con desplazamiento](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)