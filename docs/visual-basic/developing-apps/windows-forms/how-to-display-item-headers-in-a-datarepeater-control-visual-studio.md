---
title: 'Cómo: Mostrar los encabezados de los elementos en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: 07f6a7e06c5b1e91597ab6b6d816407a2c172278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Cómo: Mostrar los encabezados de los elementos en un control DataRepeater (Visual Studio)
El encabezado de elemento en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control proporciona un indicador visual cuando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> está seleccionada. Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (valor predeterminado), se muestra el encabezado de elemento a la izquierda de cada elemento. Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, el encabezado de elemento se muestra en la parte superior de cada elemento.  
  
 Cuando se selecciona por primera vez, el encabezado de elemento se muestra en el color que se especifica mediante el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> se muestra la propiedad y un icono de flecha blanca.  
  
> [!NOTE]
>  Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando se selecciona el elemento por primera vez.  
  
 Cuando un campo en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> tiene el foco, el color de los cambios de elemento de encabezado para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> color del fondo y los cambios de icono de flecha en negro. Si se cambian los datos, se muestra un símbolo de lápiz en el encabezado de elemento.  
  
 El ancho predeterminado (o alto cuando los <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) del elemento de encabezado es 15 píxeles. Puede cambiar el ancho estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad.  
  
> [!NOTE]
>  Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos de indicador en el encabezado de elemento.  
  
 Puede ocultar los encabezados de elemento estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> propiedad **False**. Cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> está establecido en **False**, la única indicación de que se selecciona un elemento es una línea de puntos alrededor del perímetro de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  También puede proporcionar su propio indicador de selección mediante la supervisión de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> propiedad de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulta <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Para cambiar la apariencia de los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control. Si selecciona la sección de la plantilla de elemento, aparecerá un conjunto diferente de propiedades en la ventana Propiedades.  
  
2.  En la ventana Propiedades, use el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> propiedad para cambiar el color de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando se selecciona el elemento por primera vez.  
  
3.  Use la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad para cambiar el ancho (o el alto) de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos de indicador en el encabezado de elemento.  
  
### <a name="to-hide-item-headers"></a>Para ocultar los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control. Si selecciona la sección de la plantilla de elemento, aparecerá un conjunto diferente de propiedades en la ventana Propiedades.  
  
2.  En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> propiedad **False**.  
  
     Cuando un elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está seleccionada, la única indicación será una línea de puntos alrededor del perímetro de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
