---
title: 'Cómo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589872"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Cómo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)
El uso más común de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control consiste en Mostrar datos enlazados desde una base de datos u otro origen de datos.  
  
 Además de los controles enlazados, puede que desee agregar otros controles, como una etiqueta estática o una imagen que se repite en cada elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulte [Cómo: mostrar controles no enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 También puede enlazar a un origen de datos en tiempo de ejecución estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad `True` y la asignación de un origen de datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> propiedad. En este caso, deberá administrar todas las interacciones con el origen de datos. Para obtener más información, consulte [modo Virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Para crear un DataRepeater enlazado a datos  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  Arrastre las asas de ajuste de tamaño y posición a tamaño y colocar el control.  
  
     Tenga en cuenta que el control tiene dos regiones rectangulares. La región superior es el *plantilla de elemento*; los controles agregados a la plantilla se repetirá en cada elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de ejecución. La región inferior es el *ventanilla*, donde se mostrarán los elementos.  
  
     También puede cambiar el tamaño y colocar el control o la plantilla de elemento cambiando el **tamaño** y **posición** propiedades en la ventana Propiedades.  
  
3.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él. Para obtener más información, vea [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).  
  
4.  En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla que contiene los datos que desea enlazar.  
  
5.  Cambie el tipo drop de la tabla a `Details` haciendo clic en `Details` en la lista desplegable en el nodo de tabla.  
  
6.  Seleccione el nodo de tabla y arrástrelo a la región de la plantilla de elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
     Puede especificar qué tipos de controles que se muestran para cada campo. Para obtener más información, consulte [establecer el control que se creará al arrastrar desde la ventana de orígenes de datos](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
