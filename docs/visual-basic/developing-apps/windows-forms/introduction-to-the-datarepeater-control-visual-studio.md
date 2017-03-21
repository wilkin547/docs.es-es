---
title: "Introducción al Control DataRepeater (Visual Studio) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86078426494caabefc6bbfb036037007e830e1cb
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Introducción al control DataRepeater (Visual Studio)
Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control es un contenedor desplazable para repiten de controles que muestren los datos, por ejemplo, las filas de una tabla de base de datos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Se puede utilizar como una alternativa a la <xref:System.Windows.Forms.DataGridView>controlar cuando necesite más control sobre el diseño de los datos.</xref:System.Windows.Forms.DataGridView> El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>"se repite" en un grupo de controles relacionados mediante la creación de varias instancias en una vista desplazable.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Esto permite a los usuarios ver varios registros al mismo tiempo.  
  
## <a name="overview"></a>Información general  
 En tiempo de diseño, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control consta de dos secciones.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> La sección exterior es el *ventanilla*, donde los datos de desplazamiento se mostrará en tiempo de ejecución. La sección (superior) interna, conocida como el *plantilla de elemento*, es donde se colocan los controles que se repetirán en tiempo de ejecución, normalmente un control para cada campo del origen de datos. Las propiedades y los controles en la plantilla de elementos se encapsulan en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>propiedad.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>  
  
 En tiempo de ejecución, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>se copia en un disco duro <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>objeto que se usa para mostrar los datos cuando se desplaza cada registro en la vista.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Puede personalizar la visualización de los registros individuales en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>evento, por ejemplo, resaltando un campo en función del valor que contiene.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 El uso más común de un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control consiste en Mostrar datos de una tabla de base de datos u otro origen de datos enlazados.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Además [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] objetos de datos, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control se puede enlazar a cualquier clase que implementa el <xref:System.Collections.IList>interfaz (incluidas matrices), cualquier clase que implemente la <xref:System.ComponentModel.IListSource>interfaz, cualquier clase que implemente la <xref:System.ComponentModel.IBindingList>interfaz o cualquier clase que implemente la <xref:System.ComponentModel.IBindingListView>interfaz.</xref:System.ComponentModel.IBindingListView> </xref:System.ComponentModel.IBindingList> </xref:System.ComponentModel.IListSource> </xref:System.Collections.IList> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
### <a name="data-binding"></a>Enlace de datos  
 Normalmente, se llevan a cabo el enlace de datos arrastrando campos desde el **orígenes de datos** ventana hasta el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Para obtener más información, consulte [Cómo: mostrar los datos enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 Cuando se trabaja con grandes cantidades de datos, puede establecer el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>propiedad `True` para mostrar un subconjunto de los datos disponibles.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> El modo virtual requiere la implementación de una caché de datos desde el que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>está lleno, y debe controlar todas las interacciones con la caché de datos en tiempo de ejecución.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Para obtener más información, consulte [modo Virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 También puede mostrar controles independientes en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Por ejemplo, puede mostrar una imagen que se repite en cada elemento. Para obtener más información, consulte [Cómo: mostrar controles no enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>Eventos  
 Los eventos más importantes para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control son el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>evento, que se provoca cuando se desplazan nuevos elementos en la vista, y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>eventos, que se produce cuando se selecciona un elemento.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Puede usar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>evento para cambiar la apariencia del elemento.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Por ejemplo, puede resaltar los valores negativos. Utilice la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>evento para tener acceso a los valores de los controles cuando se selecciona un elemento.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control expone todos los eventos de control estándar en el Editor de código.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Sin embargo, algunos de los eventos no deben usarse. Teclado y mouse eventos como `KeyDown`, `Click`, y `MouseDown` no se genera en tiempo de ejecución porque el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>propio control nunca tiene el foco.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>no expone eventos en tiempo de diseño porque se crea en tiempo de ejecución.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Si desea controlar los eventos de teclado y mouse, puede agregar un <xref:System.Windows.Forms.Panel>el control a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>en tiempo de diseño y, a continuación, controlar los eventos de la <xref:System.Windows.Forms.Panel>.</xref:System.Windows.Forms.Panel> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:System.Windows.Forms.Panel> Para obtener más información, consulte [solución de problemas del DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Personalizaciones  
 Hay muchas maneras de personalizar la apariencia y el comportamiento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controlar, tanto en tiempo de ejecución y en tiempo de diseño.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Propiedades se pueden establecer para cambiar los colores, ocultar o modificar los encabezados de elemento, cambiar la orientación de vertical a horizontal y mucho más. Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Cómo: mostrar los encabezados de elemento en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), y [Cómo: cambiar el diseño de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Tenga en cuenta que algunas propiedades se aplican para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>propio control, mientras que otros se aplican sólo a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Asegúrese de que tiene la sección correcta del control seleccionado antes de establecer propiedades. Para obtener más información, consulte [Cómo: cambiar la apariencia de un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Otras personalizaciones incluyen controlar la capacidad de agregar o eliminar registros, agregar funciones de búsqueda y mostrar datos relacionados en un formato de maestro y detalles. Para obtener más información, consulte [Cómo: deshabilitar agregar y eliminar elementos de DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [Cómo: buscar datos en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), y [Cómo: crear un formulario principal-detalle mediante dos controles de DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>Vea también  
 [Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Tutorial: Mostrar datos en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
