---
title: "Combinar elementos de menú en el control MenuStrip de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8e042b3f7b0a2a2e40b8fba33fca6c147086df6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Combinar elementos de menú en el control MenuStrip de Windows Forms
Si tiene una aplicación de interfaz de múltiples documentos (MDI), puede combinar elementos de menú o menús completos del formulario secundario en los menús del formulario primario.  
  
 En este tema se describe los conceptos básicos asociados al combinar elementos de menú en una aplicación MDI.  
  
## <a name="general-concepts"></a>Conceptos generales  
 Combinar procedimientos suponen un destino y un control de código fuente:  
  
-   El destino es el <xref:System.Windows.Forms.MenuStrip> control en la principal o formulario primario MDI en la que se mezclan los elementos de menú.  
  
-   El origen es el <xref:System.Windows.Forms.MenuStrip> control en el formulario MDI secundario que contiene los elementos de menú que desea combinar en el menú de destino.  
  
 El <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad identifica el elemento de menú cuya lista desplegable se llenará con los títulos de la actual MDI primario elementos secundarios MDI del formulario. Por ejemplo, se suelen mostrar elementos secundarios MDI abiertos actualmente en el **ventana** menú.  
  
 El <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> propiedad identifica qué elementos de menú proceden de un <xref:System.Windows.Forms.MenuStrip> en un formulario MDI secundario.  
  
 Puede combinar elementos de menú de forma manual o automática. Combinación los elementos de menú de la misma manera para ambos métodos, pero la combinación se activa de forma diferente, como se describe en las secciones "Combinación Manual" y "Combinación automática" más adelante en este tema. En la combinación manual y automática, cada acción de combinación afecta a la acción de combinación siguiente.  
  
 <xref:System.Windows.Forms.MenuStrip>combinar mueve los elementos de menú de una <xref:System.Windows.Forms.ToolStrip> a otro, en lugar de clonación, como ocurría en el caso de <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valores de MergeAction  
 Establecer la acción de combinación en elementos de menú en el origen de <xref:System.Windows.Forms.MenuStrip> mediante el <xref:System.Windows.Forms.MergeAction> propiedad.  
  
 En la tabla siguiente describe el uso típico y lo que significa que las acciones de combinación disponible.  
  
|Valor de MergeAction|Descripción|Uso típico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Valor predeterminado) Agrega el elemento de origen hasta el final de la colección del elemento de destino.|Agregar elementos de menú al final del menú cuando se activa alguna parte del programa.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Agrega el elemento de origen a la colección del elemento de destino, en la ubicación especificada por el <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedad establecida en el elemento de origen.|Agregar elementos de menú a la mitad o al principio del menú cuando se activa alguna parte del programa.<br /><br /> Si el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> es el mismo para ambos elementos de menú, se agregan en orden inverso. Establecer <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> adecuadamente para conservar el orden original.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Busca una coincidencia de texto o utiliza el <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor si se encuentra ninguna coincidencia de texto y, a continuación, reemplaza el elemento de menú de destino coincidente con el elemento de menú de origen.|Reemplazar un elemento de menú de destino con un elemento de menú de origen del mismo nombre que hace algo diferente.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Busca una coincidencia de texto o utiliza el <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor si se encuentra ninguna coincidencia de texto y, a continuación, agrega todos los elementos de lista desplegable desde el origen al destino.|Creación de una estructura de menús inserta o agrega elementos de menú en un submenú o quita elementos de menú de un submenú. Por ejemplo, puede agregar un elemento de menú de un formulario MDI secundario a un principal <xref:System.Windows.Forms.MenuStrip> **Guardar como** menú.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly>le permite navegar por la estructura de menús sin realizar ninguna acción. Proporciona una manera de evaluar los elementos siguientes.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Busca una coincidencia de texto o utiliza el <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor si se encuentra ninguna coincidencia de texto y, a continuación, quita el elemento de destino.|Quitar un elemento de menú desde el destino de <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Combinación manual  
 Solo <xref:System.Windows.Forms.MenuStrip> controles participan en la combinación automática. Para combinar los elementos de otros controles, como <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip> controles, debe combinarlos manualmente, mediante una llamada a la <xref:System.Windows.Forms.ToolStripManager.Merge%2A> y <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> métodos en el código según sea necesario.  
  
## <a name="automatic-merging"></a>Combinación automática  
 Puede utilizar la combinación automática para las aplicaciones MDI activando el formulario de origen. Para usar un <xref:System.Windows.Forms.MenuStrip> en una aplicación MDI, establezca la <xref:System.Windows.Forms.Form.MainMenuStrip%2A> propiedad al destino <xref:System.Windows.Forms.MenuStrip> para que la combinación de acciones realizadas en el origen de <xref:System.Windows.Forms.MenuStrip> se reflejan en el destino <xref:System.Windows.Forms.MenuStrip>.  
  
 Puede desencadenar la combinación automática activando el <xref:System.Windows.Forms.MenuStrip> en el origen de MDI. Tras la activación, el origen de <xref:System.Windows.Forms.MenuStrip> se combina con el destino MDI. Cuando se activa un nuevo formulario, la combinación se revierte en el último formulario y se desencadena en el nuevo formulario. Puede controlar este comportamiento estableciendo el <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> propiedad según sea necesario en cada <xref:System.Windows.Forms.ToolStripItem>y estableciendo el <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> propiedad en cada <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Crear una lista de ventanas MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [Configurar la combinación automática de menús para aplicaciones MDI](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
