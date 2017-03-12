---
title: "C&#243;mo: Mostrar los encabezados de los elementos en un control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, encabezados de elementos"
  - "DataRepeater, indicadores de selección"
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# C&#243;mo: Mostrar los encabezados de los elementos en un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El encabezado de elemento en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> proporciona un indicador visual cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> está seleccionado.  Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> \(valor predeterminado\), el encabezado de elemento se muestra a la izquierda de cada elemento.  Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>, el encabezado de elemento se muestra encima de cada elemento.  
  
 Al seleccionarlo por primera vez, el encabezado de elemento se muestra en el color especificado por la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> y aparece un icono de flecha blanca.  
  
> [!NOTE]
>  Si establece <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> en <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible al seleccionar por primera vez el elemento.  
  
 Cuando un campo de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> tiene el foco, el color del encabezado de elemento cambia al color de fondo de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y el icono de flecha pasa a ser negro.  Si se modifican datos, se muestra un símbolo de lápiz en el encabezado del elemento.  
  
 El ancho predeterminado \(o el alto cuando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>\) del encabezado de elemento es de 15 píxeles.  Puede cambiar el ancho estableciendo la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>.  
  
> [!NOTE]
>  Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> está establecida en un valor menor que 11, no se mostrarán los símbolos de indicador en el encabezado del elemento.  
  
 Puede ocultar los encabezados de elemento estableciendo la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> en **False**.  Cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> está establecido en **False**, la única indicación de que un elemento está seleccionado es una línea de puntos alrededor del perímetro de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  También puede proporcionar su propio indicador de selección supervisando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Para obtener más información, vea <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### Para cambiar la apariencia de los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control.  Si selecciona la sección de plantilla de elemento, aparecerá un conjunto de propiedades distinto en la ventana Propiedades.  
  
2.  En la ventana Propiedades, utilice la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> para cambiar el color de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si establece <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> en <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible al seleccionar por primera vez el elemento.  
  
3.  Utilice la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> para cambiar el ancho \(o el alto\) de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> está establecida en un valor menor que 11, no se mostrarán los símbolos de indicador en el encabezado del elemento.  
  
### Para ocultar los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control.  Si selecciona la sección de plantilla de elemento, aparecerá un conjunto de propiedades distinto en la ventana Propiedades.  
  
2.  En la ventana Propiedades, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> en **False**.  
  
     Cuando un elemento de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está seleccionado, la única indicación será una línea de puntos alrededor del perímetro de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)