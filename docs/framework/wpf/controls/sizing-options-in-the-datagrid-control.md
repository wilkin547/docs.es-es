---
title: Opciones de ajuste de tamaño en el control DataGrid
description: Obtenga información sobre cómo establecer filas y columnas individuales en el Windows Presentation Foundation control DataGrid para ajustar su contenido o a valores específicos.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164748"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Opciones de ajuste de tamaño en el control DataGrid
Hay varias opciones disponibles para controlar cómo se <xref:System.Windows.Controls.DataGrid> ajustan los tamaños. <xref:System.Windows.Controls.DataGrid>, Y las filas y columnas individuales de <xref:System.Windows.Controls.DataGrid> , se pueden establecer para que el tamaño se ajuste automáticamente a su contenido o se puede establecer en valores específicos. De forma predeterminada, <xref:System.Windows.Controls.DataGrid> crecerá y se reducirá para ajustarse al tamaño de su contenido.  
  
## <a name="sizing-the-datagrid"></a>Ajustar el tamaño del control DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Precauciones al usar el ajuste de tamaño automático  
 De forma predeterminada, <xref:System.Windows.FrameworkElement.Height%2A> las <xref:System.Windows.FrameworkElement.Width%2A> propiedades y de <xref:System.Windows.Controls.DataGrid> se establecen en <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " en XAML) y <xref:System.Windows.Controls.DataGrid> se ajustará al tamaño de su contenido.  
  
 Cuando se coloca dentro de un contenedor que no restringe el tamaño de sus elementos secundarios, como <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.DataGrid> se ajustará más allá de los límites visibles del contenedor y no se mostrarán las barras de desplazamiento. Esta condición tiene implicaciones de facilidad de uso y rendimiento.  
  
 Cuando se enlaza a un conjunto de datos, si el <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.DataGrid> no está restringido, seguirá agregando una fila para cada elemento de datos en el conjunto de datos enlazado. Esto puede hacer que el <xref:System.Windows.Controls.DataGrid> crezca fuera de los límites visibles de la aplicación a medida que se agregan filas. <xref:System.Windows.Controls.DataGrid>En este caso, no mostrará barras de desplazamiento porque su seguirá <xref:System.Windows.FrameworkElement.Height%2A> creciendo para alojar las nuevas filas.  
  
 Se crea un objeto para cada fila de <xref:System.Windows.Controls.DataGrid> . Si está trabajando con un conjunto de datos grande y permite que se <xref:System.Windows.Controls.DataGrid> ajuste automáticamente al tamaño, la creación de un gran número de objetos puede afectar al rendimiento de la aplicación.  
  
 Para evitar estos problemas cuando se trabaja con grandes conjuntos de datos, se recomienda establecer específicamente el <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.DataGrid> o colocarlo en un contenedor que restrinja su <xref:System.Windows.FrameworkElement.Height%2A> , como <xref:System.Windows.Controls.Grid> . Cuando el <xref:System.Windows.FrameworkElement.Height%2A> está restringido, <xref:System.Windows.Controls.DataGrid> solo creará las filas que se ajustarán a su especificado <xref:System.Windows.FrameworkElement.Height%2A> y reciclará esas filas según sea necesario para mostrar los datos nuevos.  
  
### <a name="setting-the-datagrid-size"></a>Establecer el tamaño del control DataGrid  
 <xref:System.Windows.Controls.DataGrid>Se puede establecer para que se ajuste automáticamente al tamaño dentro de los límites especificados, o bien <xref:System.Windows.Controls.DataGrid> se puede establecer en un tamaño específico. En la tabla siguiente se muestran las propiedades que se pueden establecer para controlar el <xref:System.Windows.Controls.DataGrid> tamaño.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Establece un alto específico para <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Establece el límite superior para el alto de <xref:System.Windows.Controls.DataGrid> . El <xref:System.Windows.Controls.DataGrid> crecimiento se hará verticalmente hasta que alcance este alto.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Establece el límite inferior para el alto de <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Se reducirá verticalmente hasta que alcance este alto.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Establece un ancho específico para <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Establece el límite superior para el ancho de <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Aumentará horizontalmente hasta que alcance este ancho.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Establece el límite inferior para el ancho de <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Se reducirá horizontalmente hasta que alcance este ancho.|  
  
## <a name="sizing-rows-and-row-headers"></a>Cambiar el tamaño de filas y encabezados de fila  
  
### <a name="datagrid-rows"></a>Filas de DataGrid  
 De forma predeterminada, <xref:System.Windows.Controls.DataGrid> la propiedad de una fila <xref:System.Windows.FrameworkElement.Height%2A> se establece en <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " en XAML) y el alto de la fila se expande hasta el tamaño de su contenido. El alto de todas las filas de <xref:System.Windows.Controls.DataGrid> se puede especificar estableciendo la <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> propiedad. Los usuarios pueden cambiar el alto de las filas arrastrando los divisores de encabezado de fila.  
  
### <a name="datagrid-row-headers"></a>Encabezados de fila de DataGrid  
 Para mostrar los encabezados de fila, la <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> propiedad debe establecerse en <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> . De forma predeterminada, se muestran los encabezados de fila y se ajusta su tamaño automáticamente para ajustarse a su contenido. A los encabezados de fila se les puede asignar un ancho específico estableciendo la <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="sizing-columns-and-column-headers"></a>Cambiar el tamaño de columnas y encabezados de columna  
  
### <a name="datagrid-columns"></a>Columnas DataGrid  
 <xref:System.Windows.Controls.DataGrid>Usa los valores de <xref:System.Windows.Controls.DataGridLength> y la <xref:System.Windows.Controls.DataGridLengthUnitType> estructura para especificar los modos de ajuste de tamaño absolutos o automáticos.  
  
 En la tabla siguiente se muestran los valores proporcionados por la <xref:System.Windows.Controls.DataGridLengthUnitType> estructura.  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|El modo de ajuste automático de tamaño predeterminado cambia el tamaño <xref:System.Windows.Controls.DataGrid> de las columnas según el contenido de las celdas y de los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|El modo de ajuste de tamaño automático basado en celdas cambia el tamaño <xref:System.Windows.Controls.DataGrid> de las columnas según el contenido de las celdas de la columna, sin incluir los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|El modo de ajuste de tamaño automático basado en el encabezado cambia <xref:System.Windows.Controls.DataGrid> el tamaño de las columnas en función del contenido de los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|El modo de ajuste de tamaño basado en píxeles cambia el tamaño <xref:System.Windows.Controls.DataGrid> de las columnas según el valor numérico proporcionado.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|El modo de ajuste de tamaño de estrella se usa para distribuir el espacio disponible mediante proporciones ponderadas.<br /><br /> En XAML, los valores de estrella se expresan como n *, donde n representa un valor numérico. 1 \* es equivalente a \* . Por ejemplo, si dos columnas de una <xref:System.Windows.Controls.DataGrid> tenían anchos de \* y 2 \* , la primera columna recibiría una parte del espacio disponible y la segunda columna recibiría dos partes del espacio disponible.|  
  
 La <xref:System.Windows.Controls.DataGridLengthConverter> clase se puede utilizar para convertir datos entre valores numéricos o de cadena y <xref:System.Windows.Controls.DataGridLength> valores.  
  
 De forma predeterminada, la <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> propiedad se establece en <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> y la <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> propiedad se establece en <xref:System.Windows.Controls.DataGridLength.Auto%2A> . Cuando el modo de ajuste de tamaño está establecido en <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> , las columnas crecerán hasta el ancho de su contenido visible más amplio. Al desplazarse, estos modos de ajuste de tamaño harán que las columnas se expandan si el contenido que es mayor que el tamaño de la columna actual se desplaza a la vista. La columna no se reducirá después de que el contenido se desplace fuera de la vista.  
  
 Las columnas de <xref:System.Windows.Controls.DataGrid> también pueden establecerse de forma que se ajuste automáticamente al tamaño de los límites especificados, o bien las columnas pueden establecerse en un tamaño específico. En la tabla siguiente se muestran las propiedades que se pueden establecer para controlar los tamaños de las columnas.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Establece el límite superior para todas las columnas de <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Establece el límite superior de una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Establece el límite inferior para todas las columnas de <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Establece el límite inferior de una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Establece un ancho específico para todas las columnas de <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Establece un ancho específico para una columna individual. Invalida <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Encabezados de columna DataGrid  
 De forma predeterminada, <xref:System.Windows.Controls.DataGrid> se muestran los encabezados de columna. Para ocultar los encabezados de columna, la <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> propiedad debe establecerse en <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> . De forma predeterminada, cuando se muestran los encabezados de columna, se ajusta su tamaño automáticamente para ajustarse a su contenido. A los encabezados de columna se les puede asignar un alto determinado estableciendo la <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> propiedad.  
  
### <a name="resizing-with-the-mouse"></a>Cambiar el tamaño con el mouse  
 Los usuarios pueden cambiar el tamaño de las <xref:System.Windows.Controls.DataGrid> filas y las columnas arrastrando los divisores de los encabezados de fila o de columna. <xref:System.Windows.Controls.DataGrid>También admite el cambio de tamaño automático de filas y columnas haciendo doble clic en el divisor de encabezado de fila o de columna. Para evitar que un usuario cambie el tamaño de las columnas determinadas, establezca la <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> propiedad en `false` para las columnas individuales. Para evitar que los usuarios cambien el tamaño de todas las columnas, establezca la <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> propiedad en `false` . Para evitar que los usuarios cambien el tamaño de todas las filas, establezca la <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> propiedad en `false` .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
