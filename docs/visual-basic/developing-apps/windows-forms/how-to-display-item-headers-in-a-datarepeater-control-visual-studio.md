---
title: Procedimiento Mostrar encabezados de elemento en un Control DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: eccac1b3b02da41a34d47072be267f6c51a7d490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504566"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Procedimiento Mostrar encabezados de elemento en un Control DataRepeater (Visual Studio)
El encabezado del elemento en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control proporciona un indicador visual cuando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> está seleccionada. Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (valor predeterminado), se muestra el encabezado de elemento a la izquierda de cada elemento. Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, el encabezado de elemento se muestra en la parte superior de cada elemento.  
  
 Cuando se selecciona por primera vez, el encabezado de elemento se muestra en el color especificado por el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> se muestra la propiedad y un icono de flecha blanca.  
  
> [!NOTE]
>  Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando el elemento se selecciona por primera vez.  
  
 Cuando un campo en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> tiene el foco, el color de los cambios de encabezado de elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> color de fondo y los cambios de icono de flecha en negro. Si se modifican datos, se muestra un símbolo de lápiz en el encabezado del elemento.  
  
 El ancho predeterminado (o el alto cuando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad está establecida en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) del elemento de encabezado es 15 píxeles. Puede cambiar el ancho estableciendo el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad.  
  
> [!NOTE]
>  Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos del indicador en el encabezado del elemento.  
  
 Puede ocultar los encabezados de elemento estableciendo el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> propiedad **False**. Cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> está establecido en **False**, la única indicación de que se selecciona un elemento es una línea de puntos alrededor del perímetro de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  También puede proporcionar su propio indicador de selección mediante la supervisión de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> propiedad de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulta <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Para cambiar la apariencia de los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control. Si selecciona la sección de la plantilla de elemento, aparecerá un conjunto diferente de propiedades en la ventana Propiedades.  
  
2.  En la ventana Propiedades, use el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> propiedad para cambiar el color de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando el elemento se selecciona por primera vez.  
  
3.  Use el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad para cambiar el ancho (o alto) de los encabezados de elemento.  
  
    > [!NOTE]
    >  Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos del indicador en el encabezado del elemento.  
  
### <a name="to-hide-item-headers"></a>Para ocultar los encabezados de elemento  
  
1.  En el Diseñador de Windows Forms, seleccione la región inferior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar la región inferior del control. Si selecciona la sección de la plantilla de elemento, aparecerá un conjunto diferente de propiedades en la ventana Propiedades.  
  
2.  En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> propiedad **False**.  
  
     Cuando un elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está seleccionada, la única indicación será una línea de puntos alrededor del perímetro de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Cómo: Cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Cómo: Cambiar el diseño de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
