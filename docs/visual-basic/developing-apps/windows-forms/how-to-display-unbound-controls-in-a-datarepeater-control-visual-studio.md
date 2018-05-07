---
title: 'Cómo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Cómo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio)
Además de los controles enlazados, puede que desee agregar otros controles a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, como una etiqueta estática o una imagen que se repite en cada elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
> [!NOTE]
>  También debe tener al menos un control enlazado en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o nada se mostrará en tiempo de ejecución.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Para agregar controles independientes a DataRepeater  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.  
  
2.  Arrastre las asas de ajuste de tamaño y posición a tamaño y colocar el control.  
  
     También puede cambiar el tamaño y colocar el control cambiando la **tamaño** y **posición** propiedades en la ventana Propiedades.  
  
3.  Agregue al menos un control enlazado a datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulte [Cómo: mostrar datos enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Arrastre un control desde el **cuadro de herramientas** a la región de la plantilla de elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
     Tenga en cuenta que el control tiene dos regiones rectangulares. La región interna es la *plantilla de elemento*; los controles agregados a la plantilla se repetirá en cada elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de ejecución. La región exterior es el *ventanilla*, donde los elementos se mostrarán; controles que se agregan a esta región no se mostrará en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
