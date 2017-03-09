---
title: "Soluci&#243;n de problemas del control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, solucionar problemas"
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Soluci&#243;n de problemas del control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este tema se enumeran los problemas comunes que pueden producirse al trabajar con el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
## No se provocan eventos de teclado y mouse de DataRepeater  
 No se provocan algunos eventos del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, como eventos de teclado y mouse.  Esto es intencionado.  El propio control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es un contenedor para objetos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> y no se puede obtener acceso a él en tiempo de ejecución.  El objeto <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no expone eventos en tiempo de diseño.  Por consiguiente, al hacer clic en un elemento o al presionar una tecla cuando el elemento tiene el foco no se inicia ningún evento.  
  
 La excepción a esto es cuando la propiedad <xref:System.Windows.Forms.Control.Padding%2A> está establecida en un valor lo suficientemente grande para exponer los bordes del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  En este caso, al hacer clic en el margen expuesto, se provocarán eventos de mouse.  
  
 Para resolver este problema, agregue un control <xref:System.Windows.Forms.Panel> a la sección <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> y, a continuación, agregue el resto de los controles a <xref:System.Windows.Forms.Panel>.  A continuación, puede agregar código a los controladores de eventos del control <xref:System.Windows.Forms.Panel> para eventos de teclado y mouse.  
  
## DataRepeater se oculta parcialmente detrás del examinador de enlaces  
 Al agregar por primera vez un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> a un formulario y, a continuación, agregar controles enlazados a datos desde la ventana **Orígenes de datos**, el control <xref:System.Windows.Forms.BindingNavigator> puede aparecer encima del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Es una limitación conocida de la ventana **Orígenes de datos**, en la que otros controles, como el control <xref:System.Windows.Forms.DataGridView>, se comportan de igual manera.  
  
 Puede colocar el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> debajo del control <xref:System.Windows.Forms.BindingNavigator> en tiempo de diseño o agregar un código similar al siguiente en el controlador de eventos `Load`.  
  
```vb#  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```c#  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## Los controles no se muestran correctamente en tiempo de ejecución  
 Algunos controles en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> no se pueden mostrar en tiempo de ejecución tal como se espera.  El proceso utilizado para clonar controles de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no siempre puede determinar todas las propiedades de todos los controles.  Por ejemplo, si agrega un control <xref:System.Windows.Forms.ListBox> independiente a un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> en tiempo de diseño y rellena su colección <xref:System.Windows.Forms.ListBox.Items%2A> con una lista de cadenas, el control <xref:System.Windows.Forms.ListBox> estará vacío en tiempo de ejecución.  Esto es así porque el proceso de clonación no puede tener en cuenta la propiedad <xref:System.Windows.Forms.ListBox.Items%2A>.  
  
 Puede corregir este tipo de problemas restableciendo las propiedades perdidas en el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>, lo que sucede una vez completada la clonación predeterminada.  En el ejemplo siguiente se muestra cómo reparar la colección <xref:System.Windows.Forms.ListBox.Items%2A> de un control <xref:System.Windows.Forms.ListBox> en el controlador de eventos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>.  
  
 [!code-cs[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/DataRepeaterItemClonedCS/ItemCloned.cs#1)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/DataRepeaterItemCloned/ItemCloned.vb#1)]  
  
## Falta el símbolo de selección en el encabezado del elemento  
 Al cambiar la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> del encabezado de elemento en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, algunas opciones de color pueden hacer que el símbolo de selección desaparezca.  Al modificar la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>, el símbolo de selección también puede desaparecer.  
  
 No se pueden cambiar ni color ni el tamaño del símbolo de selección.  
  
-   Si establece la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> en <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible al seleccionar por primera vez un elemento.  
  
-   Si establece la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> en <xref:System.Drawing.Color.Black%2A>, el símbolo de selección no estará visible cuando esté seleccionado un control y el símbolo de lápiz no estará visible cuando un control esté en modo de edición.  
  
-   Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> está establecida en un valor menor que 11, no se mostrarán los símbolos de indicador en el encabezado del elemento.  
  
 Puede proporcionar su propio encabezado de elemento y símbolo de selección utilizando un control <xref:System.Windows.Forms.PictureBox> y supervisando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Para obtener más información, vea <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## Vea también  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [Cómo: Buscar datos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Crear un formulario principal\-detalle mediante dos controles DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)