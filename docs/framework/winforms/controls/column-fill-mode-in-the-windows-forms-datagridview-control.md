---
title: "Modo de relleno de columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, cambiar el tamaño de las columnas automáticamente"
  - "cuadrículas de datos, columna de modo de relleno"
  - "DataGridView (control) [Windows Forms], columna de modo de relleno"
ms.assetid: b4ef7411-ebf4-4e26-bb33-aecec90de80c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Modo de relleno de columnas en el control DataGridView de formularios Windows Forms
En el modo de relleno de columna, el control <xref:System.Windows.Forms.DataGridView> cambia el tamaño de sus columnas automáticamente para que rellenen el ancho del área de visualización disponible.  El control no muestra la barra de desplazamiento horizontal excepto cuando es necesario que el ancho de cada columna sea igual o mayor que su valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>.  
  
 El comportamiento de cambio de tamaño de cada columna depende de propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>.  El valor de esta propiedad se hereda de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> de la columna o de la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> del control si el valor de la columna es <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> \(el valor predeterminado\).  
  
 Cada columna puede tener un modo de tamaño distinto, pero las columnas con un modo de tamaño de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> compartirán el ancho del área de visualización que no usen las otras columnas.  Este ancho se divide entre las columnas en modo de relleno en proporciones relativas a sus valores de propiedad <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.  Por ejemplo, si dos columnas tienen valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de 100 y 200, la primera columna será la mitad de ancha que la segunda columna.  
  
## Cambio de tamaño del usuario en modo de relleno  
 A diferencia de los modos de cambio de tamaño, que cambian el tamaño según el contenido de la celda, el modo de relleno no impide que los usuarios cambien el tamaño de las columnas cuya propiedad <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> es `true`.  Cuando un usuario cambia el tamaño de una columna en modo de relleno, las columnas en modo de relleno situadas después de la columna cuyo tamaño ha cambiado \(a la derecha si <xref:System.Windows.Forms.Control.RightToLeft%2A> es `false`; de lo contrario, a la izquierda\) también cambian de tamaño para compensar el cambio en el ancho disponible.  Si no hay ninguna columna en modo de relleno después de la columna cuyo tamaño ha cambiado, se cambia el tamaño de todas las columnas de modo de relleno del control para compensar.  Si no hay ninguna otra columna en modo de relleno en el control, se omite el cambio de tamaño.  Si se cambia el tamaño de una columna que no está en modo de relleno, todas las columnas en modo de relleno del control cambian de tamaño para compensar.  
  
 Después de cambiar el tamaño de una columna en modo de relleno, los valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de todas las columnas que han cambiado se ajustan proporcionalmente.  Por ejemplo, si cuatro columnas en modo de relleno tienen valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de 100, al cambiar el tamaño de la segunda columna a la mitad de su ancho inicial los valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> cambiarán a 100, 50, 125 y 125.  Cambiar el tamaño de una columna que no está en modo de relleno no cambiará ningún valor <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> porque las columnas en modo de relleno simplemente cambiarán de tamaño para compensar, conservando las mismas proporciones.  
  
## Ajuste de FillWeight basado en contenido  
 Puede inicializar los valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de las columnas en modo de relleno usando los métodos de cambio de tamaño automático de <xref:System.Windows.Forms.DataGridView>, como el método <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>.  Este método calcula primero el ancho que las columnas necesitan para mostrar su contenido.  Después, el control ajusta los valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> para todas las columnas en modo de relleno para que sus proporciones coincidan con las proporciones de los anchos calculados.  Por último, el control cambia el tamaño de las columnas en modo de relleno con las nuevas proporciones <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> para que todas las columnas del control rellenen el espacio horizontal disponible.  
  
## Ejemplo  
  
### Descripción  
 Puede usar los valores adecuados de las propiedades <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> y <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> para personalizar los comportamientos de cambio de tamaño de columna para muchos escenarios diferentes.  
  
 El código de demostración siguiente permite experimentar con valores diferentes para las propiedades <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> y <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de diferentes columnas.  En este ejemplo, se enlaza un control <xref:System.Windows.Forms.DataGridView> a su propia colección <xref:System.Windows.Forms.DataGridView.Columns%2A> y se enlaza una columna a cada una de las propiedades <xref:System.Windows.Forms.DataGridViewColumn.HeaderText%2A>, <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>, <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> y <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>.  Cada una de las columnas se representa también mediante una fila en el control y los valores que cambien en una fila actualizarán las propiedades de la columna correspondiente para que pueda ver cómo interactúan los valores.  
  
### Código  
 [!code-csharp[System.Windows.Forms.DataGridViewFillColumnsDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewFillColumnsDemo/CS/fillcolumns.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewFillColumnsDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewFillColumnsDemo/vb/fillcolumns.vb#00)]  
  
### Comentarios  
 Para usar esta aplicación de demostración:  
  
-   Cambie el tamaño del formulario.  Observe cómo las columnas cambian el ancho conservando las proporciones indicadas por los valores de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.  
  
-   Cambie el tamaño de las columnas arrastrando los divisores de columna con el mouse.  Observe cómo cambian los valores <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.  
  
-   Cambie el valor <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de una columna y, después, arrastre para cambiar el tamaño del formulario.  Observe cómo, al reducir el formulario lo suficiente, los valores de <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> no son inferiores a los valores <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>.  
  
-   Cambie los valores <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de todas las columnas por un número grande para que los valores combinados superen el ancho del control.  Observe cómo aparece la barra de desplazamiento horizontal.  
  
-   Cambie los valores <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> de algunas columnas.  Observe el efecto cuando se cambia el tamaño de las columnas o del formulario.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName>   
 [Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)