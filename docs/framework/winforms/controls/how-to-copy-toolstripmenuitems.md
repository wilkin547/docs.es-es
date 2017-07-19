---
title: "C&#243;mo: Copiar ToolStripMenuItems | Microsoft Docs"
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
  - "elementos de menú, copiar y pegar"
  - "MenuStrip (control) [formularios Windows Forms], organizar elementos"
  - "ToolStripMenuItems, copiar y pegar"
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Copiar ToolStripMenuItems
Durante el diseño, puede copiar menús de nivel superior completos y sus elementos de submenú en un lugar diferente en la <xref:System.Windows.Forms.MenuStrip>. También puede copiar elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.  
  
### Para copiar un menú de nivel superior y sus elementos de submenú en otra ubicación de nivel superior  
  
1.  Haga clic en el menú que desea copiar y presione CTRL\+C o haga clic con el botón derecho en el menú y seleccione **Copiar** en el menú contextual.  
  
2.  Haga clic en el menú de nivel superior que está después de la nueva ubicación deseada y presione CTRL\+V o haga clic con el botón derecho en el elemento de menú de nivel superior anterior a la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.  
  
     El menú copiado se inserta delante del menú de nivel superior seleccionado.  
  
### Para copiar un menú de nivel superior y sus elementos de submenú en una ubicación desplegable  
  
1.  Haga clic en el menú que desea mover y presione CTRL\+C o haga clic con el botón derecho en el menú y seleccione **Copiar** en el menú contextual.  
  
2.  En el menú de nivel superior de destino, haga clic en el elemento de submenú que está encima de la nueva ubicación deseada y presione CTRL\+V o haga clic con el botón derecho en el elemento de submenú que está encima de la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.  
  
     El menú copiado se inserta delante del elemento de submenú seleccionado.  
  
### Para copiar un elemento de submenú en otro menú  
  
1.  Haga clic en el elemento de submenú que desea copiar y presione CTRL\+C o haga clic con el botón derecho en el elemento de submenú y seleccione **Copiar** en el menú contextual.  
  
2.  Haga clic en el menú que contendrá el elemento de submenú que ha cortado.  
  
3.  Haga clic en el elemento de submenú que está antes de la nueva ubicación deseada y presione CTRL\+V o haga clic con el botón derecho en el elemento de submenú anterior a la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.  
  
     El elemento de submenú copiado se inserta delante del elemento de submenú seleccionado.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)