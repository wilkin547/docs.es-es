---
title: "C&#243;mo: Cambiar el retardo del componente ToolTip de formularios Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], información sobre herramientas"
  - "ToolTip (componente) [Windows Forms], valores retardados"
  - "información sobre herramientas [Windows Forms], valores retardados"
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Cambiar el retardo del componente ToolTip de formularios Windows Forms
Hay varios valores de retardo que se pueden establecer para un componente <xref:System.Windows.Forms.ToolTip> de formularios Windows Forms.  La unidad de medida para todas estas propiedades es el milisegundo.  La propiedad <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> determina durante cuánto tiempo debe señalar el usuario al control asociado para que aparezca la cadena de información sobre herramientas.  La propiedad <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> establece el número de milisegundos que tardan en aparecer las subsiguientes cadenas de información sobre herramientas cuando el mouse se desplaza desde un control asociado a información sobre herramientas hasta otro.  La propiedad <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> determina el período de tiempo durante el cual se muestra la cadena de información sobre herramientas.  Puede establecer estos valores individualmente o definiendo el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>; las demás propiedades Delay se establecen en función del valor asignado a la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>.  Por ejemplo, cuando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> se establece en un valor N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> se establece en N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> se establece en el valor de <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividido entre cinco \(o N\/5\) y <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> se establece en un valor que es cinco veces el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> \(o 5N\).  
  
### Para establecer el retardo  
  
1.  Establezca las propiedades siguientes como se muestra en este ejemplo.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## Vea también  
 [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Cómo: Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)