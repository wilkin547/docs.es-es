---
title: "C&#243;mo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, enlace de datos"
  - "DataRepeater, mostrar controles enlazados"
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El uso más común del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es mostrar la información enlazada a una base de datos u otros orígenes de datos.  
  
 Además de los controles enlazados, es posible que desee agregar otros controles, como una etiqueta estática o una imagen que se repite en cada elemento en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Para obtener más información, vea [Cómo: Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 También puede enlazar con un origen de datos en tiempo de ejecución estableciendo la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True` y asignando un origen de datos a la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>.  En este caso, deberá administrar toda la interacción con el origen de datos.  Para obtener más información, vea [Modo virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear un DataRepeater enlazado a datos  
  
1.  Arrastre un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> desde la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** hasta un control de formulario o un control contenedor.  
  
2.  Arrastre los controladores de tamaño y posición para ajustar el tamaño del control y colocarlo.  
  
     Observe que el control tiene dos regiones rectangulares.  La región superior es la *plantilla de elementos*; los controles agregados a la plantilla se repetirán en cada elemento en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> en tiempo de ejecución.  La región inferior es el *ventanilla*, donde se mostrarán los elementos.  
  
     También puede ajustar el tamaño del control o la plantilla de elementos y colocarlos cambiando las propiedades **Size** y **Position** en la ventana Propiedades.  
  
3.  En el menú **Datos**, haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si la ventana **Orígenes de datos** está vacía, agréguele un origen de datos.  Para obtener más información, vea [Información general sobre orígenes de datos](/visual-studio/data-tools/add-new-data-sources).  
  
4.  En la ventana **Orígenes de datos**, seleccione el nodo de nivel superior para la tabla que contiene los datos que desea enlazar.  
  
5.  Cambie el tipo de colocación de la tabla a `Details` haciendo clic en `Details` en la lista desplegable del nodo de tabla.  
  
6.  Seleccione el nodo de tabla y arrástrelo a la región de plantilla de elementos del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
     Puede especificar qué tipos de controles se muestran para cada campo.  Para obtener más información, vea [Establecer el control que se creará al arrastrar desde la ventana Orígenes de datos](/visual-studio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Crear un formulario principal\-detalle mediante dos controles DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)