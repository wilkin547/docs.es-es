---
title: Opciones de ajuste de tamaño en el control DataGrid
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4219dc88a263b73aa89812a2f841a920c804796b
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2018
---
# <a name="sizing-options-in-the-datagrid-control"></a>Opciones de ajuste de tamaño en el control DataGrid
Existen diversas opciones para controlar cómo el <xref:System.Windows.Controls.DataGrid> ajusta su tamaño. El <xref:System.Windows.Controls.DataGrid>y filas y columnas individuales en el <xref:System.Windows.Controls.DataGrid>, se puede establecer para cambiar el tamaño automáticamente a su contenido o se puede establecer en valores concretos. De forma predeterminada, la <xref:System.Windows.Controls.DataGrid> aumentará y reducir su tamaño para ajustarse al tamaño de su contenido.  
  
## <a name="sizing-the-datagrid"></a>Ajustar el tamaño de la cuadrícula de datos  
  
### <a name="cautions-when-using-automatic-sizing"></a>Precauciones cuando se utiliza el ajuste automático de tamaño  
 De forma predeterminada, el <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> propiedades de la <xref:System.Windows.Controls.DataGrid> se establecen en <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" en XAML) y el <xref:System.Windows.Controls.DataGrid> se ajustará al tamaño de su contenido.  
  
 Cuando se coloca dentro de un contenedor que no limita el tamaño de sus elementos secundarios, como un <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.StackPanel>, el <xref:System.Windows.Controls.DataGrid> se estirará más allá de los límites visibles del contenedor y no se mostrarán las barras de desplazamiento. Esta condición tiene implicaciones de facilidad de uso y rendimiento.  
  
 Cuando se enlaza a un conjunto de datos, si la <xref:System.Windows.FrameworkElement.Height%2A> de la <xref:System.Windows.Controls.DataGrid> no es restringido, continuará agregar una fila para cada elemento de datos en el conjunto de datos enlazado. Esto puede causar la <xref:System.Windows.Controls.DataGrid> crezca fuera de los límites visibles de la aplicación cuando se agregan filas. El <xref:System.Windows.Controls.DataGrid> no mostrará las barras de desplazamiento en este caso porque su <xref:System.Windows.FrameworkElement.Height%2A> continuará creciendo para dar cabida a las nuevas filas.  
  
 Se crea un objeto para cada fila de la <xref:System.Windows.Controls.DataGrid>. Si está trabajando con un conjunto de datos grande y permite que el <xref:System.Windows.Controls.DataGrid> para cambiar automáticamente de tamaño, la creación de un gran número de objetos puede afectar al rendimiento de la aplicación.  
  
 Para evitar estos problemas cuando se trabaja con grandes conjuntos de datos, se recomienda que se establezcan específicamente el <xref:System.Windows.FrameworkElement.Height%2A> de la <xref:System.Windows.Controls.DataGrid> o colocarlo en un contenedor que restrinja su <xref:System.Windows.FrameworkElement.Height%2A>, como un <xref:System.Windows.Controls.Grid>. Cuando el <xref:System.Windows.FrameworkElement.Height%2A> está restringido, el <xref:System.Windows.Controls.DataGrid> creará solo las filas que se ajusten a sus especificado <xref:System.Windows.FrameworkElement.Height%2A>y se reciclará las filas según sea necesario para mostrar los datos nuevos.  
  
### <a name="setting-the-datagrid-size"></a>Establecer el tamaño del control DataGrid  
 El <xref:System.Windows.Controls.DataGrid> se puede establecer en automáticamente el tamaño de los límites especificados, o el <xref:System.Windows.Controls.DataGrid> se puede establecer en un tamaño específico. La siguiente tabla muestra las propiedades que pueden establecerse para controlar la <xref:System.Windows.Controls.DataGrid> tamaño.  
  
|Property|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Establece un alto específico para el <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Establece el límite superior para el alto de la <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Controls.DataGrid> crecerá verticalmente hasta que alcanza este alto.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Establece el límite inferior para el alto de la <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Controls.DataGrid> se reducirá verticalmente hasta que alcanza este alto.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Establece un ancho específico para el <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Establece el límite superior para el ancho de la <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Controls.DataGrid> crece horizontalmente hasta que llega a este ancho.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Establece el límite inferior para el ancho de la <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Controls.DataGrid> se reducirá horizontalmente hasta alcanzar este ancho.|  
  
## <a name="sizing-rows-and-row-headers"></a>Ajustar el tamaño de filas y encabezados de fila  
  
### <a name="datagrid-rows"></a>Filas de DataGrid  
 De forma predeterminada, un <xref:System.Windows.Controls.DataGrid> la fila <xref:System.Windows.FrameworkElement.Height%2A> propiedad está establecida en <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" en XAML), y el alto de fila se expandirá al tamaño de su contenido. El alto de todas las filas de la <xref:System.Windows.Controls.DataGrid> se puede especificar estableciendo la <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> propiedad. Los usuarios pueden cambiar el alto de fila arrastrando los divisores de encabezado de fila.  
  
### <a name="datagrid-row-headers"></a>Encabezados de fila de DataGrid  
 Para mostrar encabezados de fila, el <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> propiedad debe establecerse en <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. De forma predeterminada, se muestran los encabezados de fila y se dimensionan para ajustar su contenido automáticamente. Los encabezados de fila pueden indicarse un ancho específico estableciendo la <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="sizing-columns-and-column-headers"></a>Ajustar el tamaño de las columnas y encabezados de columna  
  
### <a name="datagrid-columns"></a>Columnas de DataGrid  
 El <xref:System.Windows.Controls.DataGrid> usa valores de la <xref:System.Windows.Controls.DataGridLength> y <xref:System.Windows.Controls.DataGridLengthUnitType> estructura para especificar los modos de ajuste de tamaño automático o absoluto.  
  
 En la tabla siguiente se muestra los valores proporcionados por el <xref:System.Windows.Controls.DataGridLengthUnitType> estructura.  
  
|nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|El valor predeterminado de tamaños de modo de ajuste de tamaño automático <xref:System.Windows.Controls.DataGrid> columnas en función del contenido de las celdas y encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Automático basado en celdas tamaños de modo de ajuste de tamaño <xref:System.Windows.Controls.DataGrid> columnas en función del contenido de las celdas de la columna, sin incluir encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Automático basado en encabezados tamaños de modo de ajuste de tamaño <xref:System.Windows.Controls.DataGrid> columnas en función del contenido de sólo los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Basado en el píxel tamaños de modo de ajuste de tamaño <xref:System.Windows.Controls.DataGrid> columnas según el valor numérico proporcionado.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|El modo de ajuste de estrella se utiliza para distribuir el espacio disponible en proporciones ponderadas.<br /><br /> En XAML, los valores de estrella se expresan como n *, donde n representa un valor numérico. 1\* es equivalente a \*. Por ejemplo, si dos columnas de una <xref:System.Windows.Controls.DataGrid> tenía anchos de \* y 2\*, la primera columna recibiría una parte del espacio disponible y la segunda columna recibiría dos partes del espacio disponible.|  
  
 El <xref:System.Windows.Controls.DataGridLengthConverter> clase puede usarse para convertir datos entre valores numéricos o de cadena y <xref:System.Windows.Controls.DataGridLength> valores.  
  
 De forma predeterminada, el <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> propiedad está establecida en <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>y el <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> propiedad está establecida en <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Cuando se establece el modo de ajuste en <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, columnas aumentará de tamaño hasta el ancho de su contenido visible más ancho. Al desplazarse, estos modos de ajuste de tamaño hará que las columnas se expandan si el contenido que es mayor que el tamaño de columna actual se desplaza en la vista. La columna no se reducirá cuando el contenido se desplaza fuera de la vista.  
  
 Las columnas de la <xref:System.Windows.Controls.DataGrid> también se puede establecer en automáticamente el tamaño solo dentro de los límites especificados, o las columnas se pueden establecer en un tamaño específico. En la tabla siguiente muestra las propiedades que se pueden establecer para controlar el tamaño de las columnas.  
  
|Property|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Establece el límite superior para todas las columnas de la <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Establece el límite superior para una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Establece el límite inferior para todas las columnas de la <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Establece el límite inferior para una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Establece un ancho específico para todas las columnas de la <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Establece un ancho específico para una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Encabezados de columna de DataGrid  
 De forma predeterminada, <xref:System.Windows.Controls.DataGrid> se muestran los encabezados de columna. Para ocultar los encabezados de columna, el <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> propiedad debe establecerse en <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. De forma predeterminada, cuando se muestran los encabezados de columna, se dimensionan para ajustar su contenido automáticamente. Los encabezados de columna se pueden dar un alto concreto estableciendo la <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> propiedad.  
  
### <a name="resizing-with-the-mouse"></a>Cambio de tamaño con el Mouse  
 Pueden cambiar el tamaño de los usuarios <xref:System.Windows.Controls.DataGrid> filas y columnas arrastrando los divisores de encabezado de fila o columna. El <xref:System.Windows.Controls.DataGrid> también admite el cambio de tamaño automático de filas y columnas haciendo doble clic en el divisor de encabezado de fila o columna. Para evitar que un usuario cambiar el tamaño de columnas en particular, establezca la <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> propiedad `false` para las columnas individuales. Para evitar que los usuarios cambien el tamaño de todas las columnas, establezca la <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> propiedad `false`. Para evitar que los usuarios cambien el tamaño de todas las filas, establezca la <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> propiedad `false`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGridColumn>  
 <xref:System.Windows.Controls.DataGridLength>  
 <xref:System.Windows.Controls.DataGridLengthConverter>
