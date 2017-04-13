---
title: "DomainUpDown (Control, formularios Windows Forms) | Microsoft Docs"
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
  - "DomainUpDown (control) [Windows Forms]"
  - "control de botón de número"
  - "control de botón de número, controles de flechas"
  - "controles de flechas"
  - "controles de flechas, controles de botones de número"
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# DomainUpDown (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.DomainUpDown> de formularios Windows Forms se asemeja a una combinación de un cuadro de texto y de un par de botones para moverse hacia arriba o hacia abajo por una lista.  El control muestra y establece una cadena de texto a partir de una lista de opciones.  Para seleccionar la cadena, el usuario puede hacer clic en los botones hacia arriba y hacia abajo para desplazarse por una lista, puede presionar las teclas de de dirección ARRIBA y ABAJO o escribir una cadena que coincida con un elemento de la lista.  Un posible uso para este control es la selección de elementos de una lista de nombres ordenados alfabéticamente.  \(Para ordenar la lista, establezca la propiedad <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> en `true`.\) La función de este control es muy similar a la del cuadro de lista o el cuadro combinado, pero ocupa muy poco espacio.  
  
 Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  La propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> contiene la lista de objetos cuyos valores de texto se muestran en el control.  Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que escribe el usuario y lo hace coincidir con un valor de la lista.  Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, al desplazarse más allá del último elemento irá al primer elemento de la lista y viceversa.  Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control sólo muestra cadenas de texto.  Si desea un control que muestre valores numéricos, utilice el control <xref:System.Windows.Forms.NumericUpDown>.  Para obtener más información, vea [NumericUpDown \(Control\)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md).  
  
## En esta sección  
 [Información general sobre el control DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Presenta conceptos generales acerca del control <xref:System.Windows.Forms.DomainUpDown>, que permite a los usuarios examinar una lista de cadenas de texto y seleccionar en ella.  
  
 [Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Describe cómo especificar las cadenas de texto que debe mostrar el control <xref:System.Windows.Forms.DomainUpDown>.  
  
 [Cómo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Describe cómo eliminar elementos del control <xref:System.Windows.Forms.DomainUpDown> mediante código.  
  
## Referencia  
 <xref:System.Windows.Forms.DomainUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
## Secciones relacionadas  
 [Controles que se pueden utilizar en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Proporciona una lista completa de los controles de formularios Windows Forms con vínculos a la información sobre su utilización.