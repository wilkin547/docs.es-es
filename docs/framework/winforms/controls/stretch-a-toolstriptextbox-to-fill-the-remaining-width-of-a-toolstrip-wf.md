---
title: "C&#243;mo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms) | Microsoft Docs"
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
  - "cuadros de texto, ajustar en control ToolStrip [Windows Forms]"
  - "ToolStrip (control) [Windows Forms], ajustar un cuadro de texto"
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms)
Al establecer la propiedad <xref:System.Windows.Forms.ToolStrip.Stretch%2A> de un control <xref:System.Windows.Forms.ToolStrip> en `true`, el control rellena su contenedor de principio a fin y cambia de tamaño cuando lo hace su contenedor.  En esta configuración, puede resultarle útil ajustar un elemento del control, como <xref:System.Windows.Forms.ToolStripTextBox>, para que llene el espacio disponible y para que cambie de tamaño cuando lo haga el control.  Por ejemplo, este ajuste es útil si desea obtener una apariencia y un comportamiento similares a los de la barra de direcciones de Microsoft® Internet Explorer.  
  
## Ejemplo  
 El ejemplo de código siguiente proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> denominada `ToolStripSpringTextBox`.  Esta clase reemplaza el método <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> para calcular el ancho disponible del control primario <xref:System.Windows.Forms.ToolStrip> una vez restado el ancho combinado de todos los demás elementos.  Este ejemplo de código también proporciona una clase <xref:System.Windows.Forms.Form> y una clase `Program` para mostrar el nuevo comportamiento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripTextBox>   
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=fullName>   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)