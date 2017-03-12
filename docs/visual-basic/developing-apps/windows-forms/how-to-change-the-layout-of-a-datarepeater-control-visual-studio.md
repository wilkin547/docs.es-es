---
title: "C&#243;mo: Cambiar el dise&#241;o de un control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, cambiar el estilo de diseño"
  - "DataRepeater, cambiar la orientación"
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# C&#243;mo: Cambiar el dise&#241;o de un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> se puede mostrar en una orientación vertical \(los elementos se desplazan verticalmente\) u horizontal \(los elementos se desplazan horizontalmente\).  Puede cambiar en tiempo de diseño o en tiempo de ejecución la orientación modificando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>.  Si modifica la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> en tiempo de ejecución, es posible que desee cambiar también el tamaño de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y la posición de los controles secundarios.  
  
> [!NOTE]
>  Si cambia la posición de los controles en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en tiempo de ejecución, deberá llamar a los métodos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> al principio y al final del bloque de código que cambia la posición de los controles.  
  
### Para cambiar el diseño en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Debe seleccionar el borde exterior del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> haciendo clic en la región inferior del control y no en la región <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> superior.  
  
2.  En la ventana Propiedades, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>.  
  
### Para cambiar el diseño en tiempo de ejecución  
  
1.  Agregue el código siguiente al controlador de eventos `Click` de un botón o menú:  
  
     [!code-cs[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterLayoutCS/VbPowerPacksDataRepeaterLayout.cs#1)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterLayout/VbPowerPacksDataRepeaterLayout.vb#1)]  
  
2.  En la mayoría de los casos, es posible que desee agregar un código similar al mostrado en la sección de ejemplos para cambiar el tamaño de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y reorganizar los controles a fin de ajustarlos a la nueva orientación.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo responder al evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> en un controlador de eventos.  Este ejemplo requiere tener un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denominado `DataRepeater1` en un formulario y que su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contenga dos controles <xref:System.Windows.Forms.TextBox> denominados `TextBox1` y `TextBox2`.  
  
 [!code-cs[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterLayoutCS/VbPowerPacksDataRepeaterLayout.cs#2)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterLayout/VbPowerPacksDataRepeaterLayout.vb#2)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)