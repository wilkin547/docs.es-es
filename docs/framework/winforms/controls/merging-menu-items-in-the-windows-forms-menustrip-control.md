---
title: "Combinar elementos de men&#250; en el control MenuStrip de Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MenuStrip, combinar"
  - "combinar, conceptos generales"
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Combinar elementos de men&#250; en el control MenuStrip de Windows Forms
Si tiene una aplicación MDI \(interfaz de múltiples documentos\), puede combinar elementos de menú o menús completos del formulario secundario en los menús del formulario principal.  
  
 En este tema se describen los conceptos básicos relativos a la combinación de elementos de menú en una aplicación MDI.  
  
## Conceptos generales  
 En los procedimientos de combinación se utiliza un control de destino y un control de código fuente:  
  
-   El destino es el control <xref:System.Windows.Forms.MenuStrip> del formulario MDI principal en el que se van a combinar elementos de menú.  
  
-   El origen es el control <xref:System.Windows.Forms.MenuStrip> del formulario MDI secundario que contiene los elementos de menú que desea combinar en el menú de destino.  
  
 La propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> identifica el elemento de menú cuya lista desplegable se va a rellenar con los títulos de los elementos secundarios MDI del formulario MDI principal actual.  Por ejemplo, los elementos MDI secundarios actualmente abiertos se suelen mostrar en el menú **Ventana**.  
  
 La propiedad <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> identifica qué elementos de menú proceden de <xref:System.Windows.Forms.MenuStrip> en un formulario MDI secundario.  
  
 Puede combinar los elementos de menú manual o automáticamente.  Los elementos de menú se combinan de la misma manera en ambos métodos, pero la combinación se activa de forma diferente, como se explica en las secciones "Combinación manual" y "Combinación automática" más adelante en este tema.  Tanto en la combinación manual como en la automática, cada acción de combinación afecta a la acción de combinación siguiente.  
  
 La combinación de <xref:System.Windows.Forms.MenuStrip> mueve elementos de menú de un <xref:System.Windows.Forms.ToolStrip> a otro en lugar de clonarlos, como ocurre con <xref:System.Windows.Forms.MainMenu>.  
  
## Valores de MergeAction  
 La acción de combinación de los elementos de menú se define en el <xref:System.Windows.Forms.MenuStrip> de origen mediante la propiedad <xref:System.Windows.Forms.MergeAction>.  
  
 En la tabla siguiente se ofrece una descripción y se indica el uso común de las acciones de combinación disponibles.  
  
|Valor de MergeAction|Descripción|Uso típico|  
|--------------------------|-----------------|----------------|  
|<xref:System.Windows.Forms.MergeAction>|\(Valor predeterminado\) Agrega el elemento de origen al final de la colección del elemento de destino.|Agregar elementos de menú al final del menú cuando se activa alguna parte del programa.|  
|<xref:System.Windows.Forms.MergeAction>|Agrega el elemento de origen a la colección del elemento de destino, en la ubicación especificada por la propiedad <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> definida en el elemento de origen.|Agregar elementos de menú a la parte central o al principio del menú cuando se activa alguna parte del programa.<br /><br /> Si el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> es el mismo para ambos elementos de menú, se agregan en orden inverso.  Establezca correctamente <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> para mantener el orden original.|  
|<xref:System.Windows.Forms.MergeAction>|Busca una coincidencia de texto o el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no encuentra ninguna y, a continuación, reemplaza el elemento de menú de destino coincidente con el elemento de menú de origen.|Reemplazar un elemento de menú de destino con un elemento de menú de origen del mismo nombre que hace algo diferente.|  
|<xref:System.Windows.Forms.MergeAction>|Busca una coincidencia de texto o utiliza el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no encuentra ninguna, y, a continuación, agrega todos los elementos desplegables del origen al destino.|Compilar una estructura de menús que inserta o agrega elementos de menú a un submenú, o quitar elementos de menú de un submenú.  Por ejemplo, puede agregar un elemento de menú de un menú secundario MDI a un menú principal <xref:System.Windows.Forms.MenuStrip> **Guardar como**.<br /><br /> <xref:System.Windows.Forms.MergeAction> permite navegar por la estructura de menús sin realizar ninguna acción.  Proporciona un modo de evaluar los elementos siguientes.|  
|<xref:System.Windows.Forms.MergeAction>|Busca una coincidencia de texto o utiliza el valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> si no encuentra ninguna, y, a continuación, quita el elemento del destino.|Quitar un elemento de menú del <xref:System.Windows.Forms.MenuStrip> de destino.|  
  
## Combinación manual  
 Sólo se pueden utilizar los controles <xref:System.Windows.Forms.MenuStrip> en la combinación automática.  Para combinar los elementos de otros controles, como los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip>, debe combinarlos manualmente llamando a los métodos <xref:System.Windows.Forms.ToolStripManager.Merge%2A> y <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> en el código según se precise.  
  
## Combinación automática  
 Puede utilizar la combinación automática para las aplicaciones MDI activando el formulario de origen.  Para utilizar <xref:System.Windows.Forms.MenuStrip> en una aplicación MDI, establezca la propiedad <xref:System.Windows.Forms.Form.MainMenuStrip%2A> en el <xref:System.Windows.Forms.MenuStrip> de destino, de forma que las acciones de combinación realizadas en el <xref:System.Windows.Forms.MenuStrip> de origen se reflejen en el <xref:System.Windows.Forms.MenuStrip> de destino.  
  
 Puede iniciar la combinación automática activando el <xref:System.Windows.Forms.MenuStrip> en el formulario MDI de origen.  Al activarlo, el <xref:System.Windows.Forms.MenuStrip> de origen se combina con el formulario MDI de destino.  Cuando se activa un nuevo formulario, la combinación se revierte en el último formulario y se inicia en el nuevo.  Puede controlar este comportamiento estableciendo la propiedad <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> en cada <xref:System.Windows.Forms.ToolStripItem> según sea necesario y estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> en cada <xref:System.Windows.Forms.MenuStrip>.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 [MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Cómo: Crear una lista de ventanas MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)   
 [Cómo: Configurar la combinación automática de menús para aplicaciones MDI](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)