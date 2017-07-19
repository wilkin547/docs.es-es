---
title: "C&#243;mo: Cambiar el tama&#241;o de un control Label de formularios Windows Forms para ajustar su contenido | Microsoft Docs"
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
  - "títulos, ajustar el tamaño"
  - "Label (control) [Windows Forms], ajustar tamaño al contenido"
  - "etiquetas, ajustar tamaño al contenido"
  - "tamaño, controles"
  - "ajustar tamaño de los controles"
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Cambiar el tama&#241;o de un control Label de formularios Windows Forms para ajustar su contenido
El control <xref:System.Windows.Forms.Label> de formularios Windows Forms puede tener una sola línea o varias líneas, y tener tamaño fijo o cambiar automáticamente de tamaño para adaptarse a la leyenda.  La propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> permite cambiar el tamaño de los controles para que se ajuste leyendas mayores o menores, lo que resulta especialmente útil si la leyenda cambia en tiempo de ejecución.  
  
### Para hacer que un control cambie dinámicamente de tamaño a fin de ajustarse a su contenido  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> en `true`.  
  
 Si <xref:System.Windows.Forms.Label.AutoSize%2A> se establece en `false`, se pasarán, si es posible, las palabras especificadas en la propiedad <xref:System.Windows.Forms.Label.Text%2A> a la línea siguiente, pero no aumentará el tamaño del control.  
  
## Vea también  
 [Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)   
 [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label \(Control\)](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)