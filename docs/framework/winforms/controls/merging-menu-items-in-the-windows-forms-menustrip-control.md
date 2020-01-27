---
title: Combinar elementos de menú en el control MenuStrip
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739043"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Combinar elementos de menú en el control MenuStrip de Windows Forms
Si tiene una aplicación de interfaz de múltiples documentos (MDI), puede combinar los elementos de menú o los menús completos del formulario secundario en los menús del formulario primario.  
  
 En este tema se describen los conceptos básicos asociados a la combinación de elementos de menú en una aplicación MDI.  
  
## <a name="general-concepts"></a>Conceptos generales  
 Los procedimientos de combinación implican tanto un destino como un control de código fuente:  
  
- El destino es el control de <xref:System.Windows.Forms.MenuStrip> en el formulario principal o MDI primario en el que se van a combinar los elementos de menú.  
  
- El origen es el control de <xref:System.Windows.Forms.MenuStrip> en el formulario MDI secundario que contiene los elementos de menú que desea combinar en el menú de destino.  
  
 La propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> identifica el elemento de menú cuya lista desplegable se rellenará con los títulos de los elementos secundarios MDI del formulario MDI primario actual. Por ejemplo, normalmente se enumeran los elementos secundarios MDI que están abiertos actualmente en el menú **ventana** .  
  
 La propiedad <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> identifica los elementos de menú procedentes de un <xref:System.Windows.Forms.MenuStrip> en un formulario MDI secundario.  
  
 Puede combinar elementos de menú de forma manual o automática. Los elementos de menú se combinan de la misma manera para ambos métodos, pero la combinación se activa de manera diferente, como se describe en las secciones "combinación manual" y "combinación automática" más adelante en este tema. En la combinación manual y automática, cada acción de combinación afecta a la siguiente acción de fusión mediante combinación.  
  
 <xref:System.Windows.Forms.MenuStrip> la combinación mueve los elementos de menú de un <xref:System.Windows.Forms.ToolStrip> a otro en lugar de clonarlos, como era el caso con <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valores de MergeAction  
 Establezca la acción de combinación en los elementos de menú del <xref:System.Windows.Forms.MenuStrip> de origen mediante la propiedad <xref:System.Windows.Forms.MergeAction>.  
  
 En la tabla siguiente se describe el significado y el uso típico de las acciones de combinación disponibles.  
  
|Valor MergeAction|Descripción|Uso típico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|Predeterminada Agrega el elemento de origen al final de la colección del elemento de destino.|Agregar elementos de menú al final del menú cuando se activa una parte del programa.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Agrega el elemento de origen a la colección del elemento de destino, en la ubicación especificada por la propiedad <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> establecida en el elemento de origen.|Agregar elementos de menú al centro o al principio del menú cuando se activa una parte del programa.<br /><br /> Si el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> es el mismo para ambos elementos de menú, se agregan en orden inverso. Establezca <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> adecuadamente para conservar el orden original.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Busca una coincidencia de texto o usa el valor <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no se encuentra ninguna coincidencia de texto y, a continuación, reemplaza el elemento de menú de destino coincidente con el elemento de menú de origen.|Reemplazar un elemento de menú de destino por un elemento de menú de origen con el mismo nombre que hace algo diferente.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Busca una coincidencia de texto o usa el valor <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no se encuentra ninguna coincidencia de texto y, a continuación, agrega todos los elementos desplegables del origen al destino.|Compilar una estructura de menú que inserta o agrega elementos de menú en un submenú o quita elementos de menú de un submenú. Por ejemplo, puede Agregar un elemento de menú de un elemento secundario MDI a un menú principal <xref:System.Windows.Forms.MenuStrip>**Guardar como** .<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> le permite navegar por la estructura de menú sin realizar ninguna acción. Proporciona una manera de evaluar los elementos subsiguientes.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Busca una coincidencia de texto o usa el valor <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no se encuentra ninguna coincidencia de texto y, a continuación, quita el elemento del destino.|Quitar un elemento de menú de la <xref:System.Windows.Forms.MenuStrip>de destino.|  
  
## <a name="manual-merging"></a>Combinación manual  
 Solo los controles <xref:System.Windows.Forms.MenuStrip> participan en la combinación automática. Para combinar los elementos de otros controles, como <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip> controles, debe combinarlos manualmente, llamando a los métodos <xref:System.Windows.Forms.ToolStripManager.Merge%2A> y <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> en el código según sea necesario.  
  
## <a name="automatic-merging"></a>Combinación automática  
 Puede usar la combinación automática para las aplicaciones MDI activando el formulario de origen. Para usar un <xref:System.Windows.Forms.MenuStrip> en una aplicación MDI, establezca la propiedad <xref:System.Windows.Forms.Form.MainMenuStrip%2A> en el <xref:System.Windows.Forms.MenuStrip> de destino de modo que las acciones de combinación realizadas en el <xref:System.Windows.Forms.MenuStrip> de origen se reflejen en la <xref:System.Windows.Forms.MenuStrip>de destino.  
  
 Puede desencadenar la combinación automática activando el <xref:System.Windows.Forms.MenuStrip> en el origen MDI. Tras la activación, el <xref:System.Windows.Forms.MenuStrip> de origen se combina en el destino MDI. Cuando se activa un formulario nuevo, la combinación se revierte en el último formulario y se desencadena en el nuevo formulario. Puede controlar este comportamiento estableciendo la propiedad <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> según sea necesario en cada <xref:System.Windows.Forms.ToolStripItem>y estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> en cada <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Control MenuStrip](menustrip-control-windows-forms.md)
- [Crear una lista de ventanas MDI con MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Configurar la combinación automática de menús para aplicaciones MDI](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
