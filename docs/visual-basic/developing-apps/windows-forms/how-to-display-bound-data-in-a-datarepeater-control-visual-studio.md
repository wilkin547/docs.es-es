---
title: "Cómo: mostrar los datos enlazados en un Control DataRepeater (Visual Studio) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9bf8f2f5fcc4dfa2b29e368a4e26bf112e08149e
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Cómo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)
El uso más común de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control consiste en Mostrar datos de una base de datos u otro origen de datos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Además de los controles enlazados, puede agregar otros controles, como una etiqueta estática o una imagen que se repite en cada elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Para obtener más información, consulte [Cómo: mostrar controles no enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 También puede enlazar a un origen de datos en tiempo de ejecución estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>propiedad `True` y asignando un origen de datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>propiedad.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> En este caso, debe administrar toda la interacción con el origen de datos. Para obtener más información, consulte [modo Virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Para crear un DataRepeater enlazado a datos  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control desde el **Visual Basic PowerPacks** ficha en el **cuadro de herramientas** a un control de formulario o contenedor.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Arrastre los controladores de tamaño y posición tamaño y posición del control.  
  
     Tenga en cuenta que el control tiene dos regiones rectangulares. La región superior es el *plantilla de elemento*; controles agregados a la plantilla se repetirán en cada elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control en tiempo de ejecución.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> La región inferior es el *ventanilla*, donde se mostrarán los elementos.  
  
     También puede cambiar el tamaño y posición el control o la plantilla de elemento cambiando el **tamaño** y **posición** propiedades en la ventana Propiedades.  
  
3.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él. Para obtener más información, consulte [agregar nuevos orígenes de datos](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  En el **orígenes de datos** ventana, seleccione el nodo de nivel superior para la tabla que contiene los datos que desea enlazar.  
  
5.  Cambie el tipo drop de la tabla para `Details` haciendo clic en `Details` en la lista desplegable en el nodo de tabla.  
  
6.  Seleccione el nodo de tabla y arrástrelo a la región de la plantilla de elementos de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Puede especificar qué tipos de controles se muestran para cada campo. Para obtener más información, consulte [establecer el control que se creará al arrastrar desde la ventana Orígenes de datos](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar controles no enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Cómo: cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
