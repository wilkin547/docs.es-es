---
title: Introducción al control DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
ms.openlocfilehash: fc0cf9c358faf3e738eb3b24ec61577b88dbce4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591955"
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Introducción al control DataRepeater (Visual Studio)
El control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> de Visual Basic PowerPacks es un contenedor desplazable para los controles que muestran datos repetidos, como, por ejemplo, las filas de una tabla de base de datos. Se puede usar como una alternativa al control <xref:System.Windows.Forms.DataGridView> cuando se necesita más control sobre el diseño de los datos. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "se repite" en un grupo de controles relacionados mediante la creación de varias instancias en una vista desplazable. Esto permite a los usuarios ver varios registros al mismo tiempo.  
  
## <a name="overview"></a>Información general  
 En tiempo de diseño, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control consta de dos secciones. La sección exterior es el *ventanilla*, donde los datos de desplazamiento se mostrará en tiempo de ejecución. La sección (superior) interna, conocida como el *plantilla de elemento*, es donde se colocan los controles que se repetirá en tiempo de ejecución, normalmente un control para cada campo del origen de datos. Las propiedades y los controles en la plantilla de elemento se encapsulan en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> propiedad.  
  
 En tiempo de ejecución, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> se copia en una máquina <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> objeto que se usa para mostrar los datos cuando se desplaza cada registro en la vista. Puede personalizar la presentación de los registros individuales en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos, por ejemplo, un campo en función del valor que contiene el resaltado. Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 El uso más común de un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control consiste en mostrar los datos de una tabla de base de datos u otro origen de datos enlazado. Además [!INCLUDE[vstecado](~/includes/vstecado-md.md)] objetos de datos, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control se puede enlazar a cualquier clase que implementa el <xref:System.Collections.IList> interfaz (incluidas matrices), cualquier clase que implemente la <xref:System.ComponentModel.IListSource> interfaz, cualquier clase que implemente la <xref:System.ComponentModel.IBindingList> interfaz o cualquier clase que implemente la <xref:System.ComponentModel.IBindingListView> interfaz.  
  
### <a name="data-binding"></a>Enlace de datos  
 Por lo general, realizar el enlace de datos arrastrando campos desde el **orígenes de datos** ventana hasta el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulte [Cómo: mostrar datos enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Cuando se trabaja con grandes cantidades de datos, puede establecer la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad `True` para mostrar un subconjunto de los datos disponibles. Modo virtual requiere la implementación de una caché de datos desde el que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está lleno, y debe controlar todas las interacciones con la caché de datos en tiempo de ejecución. Para obtener más información, consulte [modo Virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 También puede mostrar controles independientes en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Por ejemplo, puede mostrar una imagen que se repite en cada elemento. Para obtener más información, consulte [Cómo: mostrar controles no enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Eventos  
 Los eventos más importantes para la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control son el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos, que se desencadena cuando se desplazan nuevos elementos en la vista, y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> eventos, que se desencadena cuando se selecciona un elemento. Puede usar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento para cambiar la apariencia del elemento. Por ejemplo, puede resaltar los valores negativos. Use la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> eventos para obtener acceso a los valores de los controles cuando se selecciona un elemento.  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control expone todos los eventos de control estándar en el Editor de código. Sin embargo, algunos de los eventos no deben usarse. Teclado y mouse eventos como `KeyDown`, `Click`, y `MouseDown` no se producen en tiempo de ejecución porque el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> propio control nunca tiene el foco.  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no expone eventos en tiempo de diseño ya que se crea en tiempo de ejecución. Si desea controlar los eventos de teclado y mouse (ratón), puede agregar un <xref:System.Windows.Forms.Panel> el control a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en tiempo de diseño y, a continuación, controlar los eventos de la <xref:System.Windows.Forms.Panel>. Para obtener más información, consulte [solución de problemas del DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Personalizaciones  
 Hay muchas maneras de personalizar la apariencia y comportamiento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar, tanto en tiempo de ejecución y en tiempo de diseño. Propiedades se pueden establecer para cambiar los colores, ocultar o modificar los encabezados de elemento, cambia la orientación de vertical a horizontal y mucho más. Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Cómo: mostrar encabezados de elemento en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), y [Cómo: cambiar el diseño de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Tenga en cuenta que algunas propiedades se aplican a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> propio control, mientras que otras se aplican únicamente a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>. Asegúrese de que dispone de la sección correcta del control seleccionado para establecer propiedades. Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Otras personalizaciones incluyen controlar la capacidad de agregar o eliminar registros, agregar funciones de búsqueda y mostrar datos relacionados en un formato de maestro y detalles. Para obtener más información, consulte [Cómo: deshabilitar agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [Cómo: buscar datos en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), y [Cómo: crear un formulario principal-detalle mediante dos utilizando Controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Vea también  
 [Control DataRepeater ](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)  
 [Tutorial: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
