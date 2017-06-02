---
title: "Informaci&#243;n general sobre el control DomainUpDown (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DomainUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown (control) [Windows Forms], acerca del control DomainUpDown"
  - "control de botón de número, acerca del botón de número"
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre el control DomainUpDown (formularios Windows Forms)
El control <xref:System.Windows.Forms.DomainUpDown> de formularios Windows Forms se asemeja a una combinación de un cuadro de texto y un par de botones para desplazarse hacia arriba o hacia abajo por una lista.  El control muestra y establece una cadena de texto a partir de una lista de opciones.  Para seleccionar la cadena, el usuario puede hacer clic en los botones hacia arriba y hacia abajo para desplazarse por una lista, puede presionar las teclas de de dirección ARRIBA y ABAJO o escribir una cadena que coincida con un elemento de la lista.  Un posible uso para este control es la selección de elementos de una lista de nombres ordenados alfabéticamente.  
  
> [!NOTE]
>  Para ordenar la lista, establezca la propiedad <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> en `true`.  
  
 La función de este control es muy similar a la del cuadro de lista o el cuadro combinado, pero ocupa muy poco espacio.  
  
## Propiedades principales  
 Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  La propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> contiene la lista de objetos cuyos valores de texto se muestran en el control.  Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que escribe el usuario y lo hace coincidir con un valor de la lista.  Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, al desplazarse más allá del último elemento irá al primer elemento de la lista y viceversa.  Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control sólo muestra cadenas de texto.  Si desea un control que muestre valores numéricos, utilice el control <xref:System.Windows.Forms.NumericUpDown>.  Para obtener más información, vea [Información general sobre el control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DomainUpDown>   
 [DomainUpDown \(Control\)](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)