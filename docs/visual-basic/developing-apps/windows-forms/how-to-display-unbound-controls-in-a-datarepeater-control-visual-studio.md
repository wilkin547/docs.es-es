---
title: "C&#243;mo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, agregar controles independientes"
  - "mostrar datos sin enlazar"
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# C&#243;mo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Además de los controles enlazados, es posible que desee agregar otros controles a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, como una etiqueta estática o una imagen que se repite en cada elemento en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
> [!NOTE]
>  También debe tener al menos un control enlazado en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o no se mostrará nada en tiempo de ejecución.  
  
### Para agregar controles independientes a DataRepeater  
  
1.  Arrastre un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> desde la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** hasta un control de formulario o un control contenedor.  
  
2.  Arrastre los controladores de tamaño y posición para ajustar el tamaño del control y colocarlo.  
  
     También puede ajustar el tamaño del control y colocarlo cambiando las propiedades **Size** y **Position** en la ventana Propiedades.  
  
3.  Agregue al menos un control enlazado a datos al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Para obtener más información, vea [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Arrastre un control desde el **Cuadro de herramientas** a la región de plantilla de elementos del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
     Observe que el control tiene dos regiones rectangulares.  La región interna es la *plantilla de elementos*; los controles agregados a la plantilla se repetirán en cada elemento en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> en tiempo de ejecución.  La región exterior es el *ventanilla*, donde se mostrarán los elementos; los controles que se agregan a esta región no se mostrarán en tiempo de ejecución.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Crear un formulario principal\-detalle mediante dos controles DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)