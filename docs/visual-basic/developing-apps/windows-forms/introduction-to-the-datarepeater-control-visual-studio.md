---
title: "Introducci&#243;n al control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater"
  - "DataRepeater, información general"
  - "datos de repetición"
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Introducci&#243;n al control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El control Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es un contenedor desplazable para los controles que muestran datos repetidos, por ejemplo, las filas de una tabla de base de datos.  Se puede usar como alternativa al control <xref:System.Windows.Forms.DataGridView> cuando se necesita mayor control sobre el diseño de los datos.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "repite" un grupo de controles relacionados creando varias instancias en una vista de desplazamiento.  Esto permite a los usuarios ver varios registros al mismo tiempo.  
  
## Información general  
 En tiempo de diseño, el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está compuesto de dos secciones.  La sección exterior es el *ventanilla*, donde se mostrarán los datos del desplazamiento en tiempo de ejecución.  La sección interna \(parte superior\), conocida como *plantilla de elementos*, es donde se colocan los controles que se repetirán en tiempo de ejecución, normalmente, un control para cada campo del origen de datos.  Las propiedades y controles de la plantilla de elementos se encapsulan en la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.  
  
 En tiempo de ejecución, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> se copia en un objeto <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> virtual que se utiliza para mostrar datos cuando se desplaza cada registro en la vista.  Puede personalizar la presentación de registros individuales en el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, por ejemplo, resaltando un campo basado en el valor que contiene.  Para obtener más información, vea [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 El uso más común para un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es mostrar los datos de una tabla de base de datos u otro origen de datos enlazado.  Además de objetos de datos [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)], el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> puede enlazarse a cualquier clase que implemente la interfaz <xref:System.Collections.IList> \(incluidas matrices\), cualquier clase que implemente la interfaz <xref:System.ComponentModel.IListSource>, cualquier clase que implemente la interfaz <xref:System.ComponentModel.IBindingList> o cualquier clase que implemente la interfaz <xref:System.ComponentModel.IBindingListView>.  
  
### Enlace de datos  
 En general, el enlace de datos se realiza arrastrando campos de la ventana **Orígenes de datos** al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Para obtener más información, vea [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Al trabajar con grandes cantidades de datos, puede establecer la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True` para mostrar un subconjunto de los datos disponibles.  El modo virtual requiere la implementación de una caché de datos de la que se rellena <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> y debe controlar todas las interacciones con la caché de datos en tiempo de ejecución.  Para obtener más información, vea [Modo virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 También puede mostrar controles independientes en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Por ejemplo, puede mostrar una imagen que se repite en cada elemento.  Para obtener más información, vea [Cómo: Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### Eventos  
 Los eventos más importantes para el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> son el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, que se provoca cuando se desplazan nuevos elementos en la vista, y el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>, que se provoca al seleccionar un elemento.  Puede utilizar el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> para cambiar la apariencia del elemento.  Por ejemplo, puede resaltar los valores negativos.  Utilice el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> para tener acceso a los valores de controles cuando hay un elemento seleccionado.  
  
 El control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> expone todos los eventos de control estándar en el Editor de código.  Sin embargo, no se deben utilizar algunos de los eventos.  Los eventos de teclado y mouse, como `KeyDown`, `Click` y `MouseDown`, no se provocarán en tiempo de ejecución porque el propio control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> nunca tiene el foco.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no expone eventos en tiempo de diseño porque solo se crea en tiempo de ejecución.  Si desea administrar eventos de teclado y mouse, puede agregar un control <xref:System.Windows.Forms.Panel> a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en tiempo de diseño y, a continuación, administrar los eventos para <xref:System.Windows.Forms.Panel>.  Para obtener más información, vea [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### Personalizaciones  
 Hay muchas maneras de personalizar la apariencia y el comportamiento del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, tanto en tiempo de ejecución como en tiempo de diseño.  Se pueden establecer propiedades para cambiar colores, ocultar o modificar encabezados de elemento, cambiar la orientación de vertical a horizontal y mucho más.  Para obtener más información, vea [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Cómo: Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) y [Cómo: Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Observe que algunas propiedades se aplican al propio control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> mientras que otras solo se aplican a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.  Asegúrese de que tiene seleccionada la sección del control correcta antes de establecer las propiedades.  Para obtener más información, vea [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Entre otras personalizaciones se incluyen controlar la capacidad de agregar o eliminar registros, agregar capacidades de búsqueda, y mostrar datos relacionados en un formato principal y de detalle.  Para obtener más información, vea [Cómo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [Cómo: Buscar datos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) y [Cómo: Crear un formulario principal\-detalle mediante dos controles DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## Vea también  
 [DataRepeater, control](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Tutorial: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)