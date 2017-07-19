---
title: "Opciones de ajuste de tama&#241;o en el control DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ajustar automáticamente el tamaño de DataGrid"
  - "DataGrid (control) [WPF], ajustar el tamaño"
  - "tamaño [WPF], DataGrid"
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Opciones de ajuste de tama&#241;o en el control DataGrid
Hay varias opciones disponibles para controlar los tamaños de <xref:System.Windows.Controls.DataGrid>.  Se puede establecer <xref:System.Windows.Controls.DataGrid>, así como las filas y las columnas de <xref:System.Windows.Controls.DataGrid>, para dimensionar automáticamente el contenido, o se puede establecer en valores concretos.  De manera predeterminada, <xref:System.Windows.Controls.DataGrid> aumentará y disminuirá de tamaño para ajustarse al tamaño del contenido.  
  
## Dimensionar DataGrid  
  
### Precauciones cuando se utiliza el tamaño automático  
 De forma predeterminada, las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.DataGrid> se establecen en <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" en XAML\) y <xref:System.Windows.Controls.DataGrid> se ajustará al tamaño de su contenido.  
  
 Cuando se coloca dentro de un contenedor que no restringe el tamaño de sus elementos secundarios, como <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.DataGrid> se expandirá más allá de los límites visibles del contenedor y las barras de desplazamiento no se mostrarán.  Esta condición tiene implicaciones de utilidad y rendimiento.  
  
 Cuando se enlaza un conjunto de datos, si <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.DataGrid> no se restringe, continuará agregando una fila para cada elemento de datos en el conjunto de datos enlazado.  Esto puede hacer que <xref:System.Windows.Controls.DataGrid> crezca fuera de los límites visibles de la aplicación cuando se agreguen filas.  <xref:System.Windows.Controls.DataGrid> no mostrará las barras de desplazamiento en este caso porque <xref:System.Windows.FrameworkElement.Height%2A> continuará creciendo para alojar las nuevas filas.  
  
 Se crea un objeto para cada fila de <xref:System.Windows.Controls.DataGrid>.  Si está trabajando con un conjunto de datos grande y permite que <xref:System.Windows.Controls.DataGrid> se dimensione automáticamente, la creación de un número grande de objetos puede afectar al rendimiento de la aplicación.  
  
 Para evitar estos problemas al trabajar con conjuntos de datos grandes, se recomienda que establezca <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.DataGrid> específicamente o que lo coloque en un contenedor que restrinja su <xref:System.Windows.FrameworkElement.Height%2A>, por ejemplo, <xref:System.Windows.Controls.Grid>.  Cuando <xref:System.Windows.FrameworkElement.Height%2A> se restringe, <xref:System.Windows.Controls.DataGrid> creará solo las filas que se ajusten a su <xref:System.Windows.FrameworkElement.Height%2A> especificado y reciclará según sea necesario esas filas para mostrar los nuevos datos.  
  
### Establecer el tamaño de DataGrid  
 <xref:System.Windows.Controls.DataGrid> se puede establecer para que se dimensione dentro de los límites especificados automáticamente o <xref:System.Windows.Controls.DataGrid> se puede establecer en un tamaño concreto.  En la siguiente lista se muestran las propiedades que pueden establecerse para controlar el tamaño de <xref:System.Windows.Controls.DataGrid>.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Establece un alto concreto para <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Establece el límite superior del alto de <xref:System.Windows.Controls.DataGrid>.  <xref:System.Windows.Controls.DataGrid> crecerá verticalmente hasta alcanzar este alto.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Establece el límite inferior del alto de <xref:System.Windows.Controls.DataGrid>.  <xref:System.Windows.Controls.DataGrid> se reducirá verticalmente hasta alcanzar este alto.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Establece un ancho concreto para <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Establece el límite superior del ancho de <xref:System.Windows.Controls.DataGrid>.  <xref:System.Windows.Controls.DataGrid> crecerá horizontalmente hasta alcanzar este ancho.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Establece el límite inferior del ancho de <xref:System.Windows.Controls.DataGrid>.  <xref:System.Windows.Controls.DataGrid> se reducirá horizontalmente hasta alcanzar este ancho.|  
  
## Dimensionar filas y encabezados de fila  
  
### Filas de DataGrid  
 De forma predeterminada, una propiedad <xref:System.Windows.FrameworkElement.Height%2A> de fila <xref:System.Windows.Controls.DataGrid> se establece en <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" en XAML\) y el alto de fila se expandirá hasta el tamaño de su contenido.  El alto de todas las filas de <xref:System.Windows.Controls.DataGrid> se puede especificar estableciendo la propiedad <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=fullName>.  Los usuarios pueden cambiar el alto de fila arrastrando los divisores del encabezado de fila.  
  
### Encabezados de fila de DataGrid  
 Para mostrar los encabezados de fila, la propiedad <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> debe estar establecida en <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> o en <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>.  De forma predeterminada, se muestran los encabezados de fila y se dimensionan para ajustar su contenido automáticamente.  A los encabezados de fila se les puede proporcionar un ancho específico estableciendo la propiedad <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=fullName>.  
  
## Dimensionar columnas y encabezados de columna  
  
### Columnas DataGrid  
 El control <xref:System.Windows.Controls.DataGrid> utiliza valores de las estructuras <xref:System.Windows.Controls.DataGridLength> y <xref:System.Windows.Controls.DataGridLengthUnitType> para especificar modos de ajuste de tamaño automático o absoluto.  
  
 En la tabla siguiente se muestran los valores proporcionados por la estructura <xref:System.Windows.Controls.DataGridLengthUnitType>.  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|El modo de ajuste de tamaño automático predeterminado ajusta el tamaño de las columnas de <xref:System.Windows.Controls.DataGrid> en función del contenido de los encabezados de celda y columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|El modo de ajuste de tamaño automático basado en celdas ajusta el tamaño de las columnas de <xref:System.Windows.Controls.DataGrid> en función del contenido de las celdas en la columna, sin incluir los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|El modo de ajuste de tamaño automático basado en encabezados ajusta el tamaño de las columnas de <xref:System.Windows.Controls.DataGrid> en función solamente del contenido de los encabezados de columna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|El modo de ajuste de tamaño basado en píxeles dimensiona las columnas de <xref:System.Windows.Controls.DataGrid> basándose en el valor numérico proporcionado.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|El modo de ajuste de tamaño mediante asterisco se usa para distribuir el espacio disponible en proporciones ponderadas.<br /><br /> En XAML, los valores de asterisco se expresan como n\*, donde n representa un valor numérico.  1\* equivale a \*.  Por ejemplo, si el ancho de dos columnas de un control <xref:System.Windows.Controls.DataGrid> fuese \* y 2\*, respectivamente, la primera columna recibiría una parte del espacio disponible y la segunda columna recibiría dos partes del espacio disponible.|  
  
 La clase <xref:System.Windows.Controls.DataGridLengthConverter> se puede utilizar para convertir datos entre valores numéricos o de cadena y valores <xref:System.Windows.Controls.DataGridLength>.  
  
 De manera predeterminada, la propiedad <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName> se establece en <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> y la propiedad <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName> se establece en <xref:System.Windows.Controls.DataGridLength.Auto%2A>.  Cuando el modo de tamaño se establece en <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, las columnas crecerán hasta el tamaño de su contenido visible más ancho.  Al desplazarse, estos modos de tamaño harán que las columnas se expandan si el contenido que es mayor que el tamaño de columna se desplaza en la vista.  La columna no se reducirá cuando el contenido se desplace fuera de la vista.  
  
 Las columnas de <xref:System.Windows.Controls.DataGrid> también se pueden establecer para dimensionarse automáticamente solo dentro de los límites especificados, o las columnas se pueden establecer en un tamaño concreto.  En la siguiente lista se muestran las propiedades que se pueden establecer para controlar el tamaño de columna.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>|Establece el límite superior de todas las columnas de <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=fullName>|Establece el límite superior de una columna individual.  Invalida <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>|Establece el límite inferior de todas las columnas de <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=fullName>|Establece el límite inferior de una columna individual.  Invalida <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>|Establece un ancho específico para todas las columnas de <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName>|Establece un ancho específico para una columna individual.  Invalida <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>.|  
  
### Encabezados de columna de DataGrid  
 De forma predeterminada, se muestran los encabezados de columna de <xref:System.Windows.Controls.DataGrid>.  Para ocultar los encabezados de fila, la propiedad <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> debe estar establecida en <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> o en <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>.  De forma predeterminada, cuando se muestran los encabezados de columna, se dimensionan para ajustar su contenido automáticamente.  A los encabezados de columna se les puede proporcionar un alto concreto estableciendo la propiedad <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=fullName>.  
  
### Cambiar el tamaño con el mouse  
 Los usuarios pueden cambiar el tamaño de las filas y columnas de <xref:System.Windows.Controls.DataGrid> arrastrando los divisores de encabezado de columna o fila.  <xref:System.Windows.Controls.DataGrid> también admite el cambio de tamaño automático de filas y columnas haciendo doble clic en el divisor de encabezado de columna o fila.  Para evitar que un usuario cambie el tamaño de las columnas en particular, establezca la propiedad <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> en `false` para las columnas individuales.  Para evitar que los usuarios cambien el tamaño de todas las columnas, establezca la propiedad <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> en `false`.  Para evitar que los usuarios cambien el tamaño de todas las filas, establezca la propiedad <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=fullName> en `false`.  
  
## Vea también  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGridColumn>   
 <xref:System.Windows.Controls.DataGridLength>   
 <xref:System.Windows.Controls.DataGridLengthConverter>