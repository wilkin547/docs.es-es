---
title: "C&#243;mo: Mover elementos ToolStripMenuItems | Microsoft Docs"
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
  - "elementos de menú, cortar y pegar"
  - "elementos de menú, arrastrar y colocar"
  - "elementos de menú, mover"
  - "menús, organizar elementos"
  - "MenuStrip (control) [Windows Forms], organizar elementos"
  - "ToolStripMenuItems, cortar y pegar"
  - "ToolStripMenuItems, arrastrar y colocar"
  - "ToolStripMenuItems, mover"
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Mover elementos ToolStripMenuItems
En tiempo de diseño, puede mover menús de nivel superior completos y sus elementos de menú a un lugar diferente en el <xref:System.Windows.Forms.MenuStrip>.  También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para mover un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior  
  
1.  Haga clic y mantenga presionado el botón primario del mouse en el menú que desea mover.  
  
2.  Arrastre el punto de inserción al menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.  
  
     El menú seleccionado se mueve a la derecha del punto de inserción.  
  
### Para mover un menú de nivel superior y sus elementos de menú en una ubicación desplegable  
  
1.  Haga clic con el botón primario del mouse en el menú que quiere mover y presione CTRL\+X o haga clic con el botón secundario en el menú y elija **Cortar** en el menú contextual.  
  
2.  En el menú de nivel superior de destino, haga clic con el botón primario del mouse en el elemento de menú que se encuentra sobre la nueva ubicación deseada y presione CTRL\+V, o haga clic con el botón secundario del mouse en el elemento de menú de nivel superior que está sobre la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.  
  
     El menú que ha cortado se inserta a continuación del elemento de menú seleccionado.  
  
### Para mover un elemento de menú dentro de un menú mediante el Editor de la colección de elementos  
  
1.  Haga clic con el botón secundario del mouse en el menú que contiene el elemento de menú que desea mover.  
  
2.  En el menú contextual, elija **Editar DropDownItems**.  
  
3.  En el **Editor de la colección de elementos**, haga clic con el botón primario del mouse en el elemento de menú que desea mover.  
  
4.  Haga clic en las teclas de dirección ARRIBA y ABAJO para mover el elemento de menú dentro del menú.  
  
5.  Haga clic en **Aceptar**.  
  
### Para mover un elemento de menú dentro de un menú mediante el teclado  
  
1.  Presione y mantenga presionada la tecla ALT.  
  
2.  Haga clic y mantenga presionado el botón primario del mouse en el elemento de menú que desea mover.  
  
3.  Arrastre el elemento de menú hacia la nueva ubicación y libere el botón primario del mouse.  
  
### Para mover un elemento de menú a otro menú  
  
1.  Haga clic con el botón primario del mouse en el elemento de menú que desea mover y presione CTRL\+X o haga clic con el botón secundario en el elemento de menú y seleccione **Cortar** en el menú contextual.  
  
2.  Haga clic con el botón primario del mouse en el elemento de menú que contendrá el elemento de submenú que ha cortado.  
  
3.  Haga clic con el botón primario del mouse en el elemento de menú que está después de la nueva ubicación deseada y presione CTRL\+V, o haga clic con el botón secundario del mouse en el elemento de menú de nivel superior que está después de la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.  
  
     El elemento de menú que ha cortado se inserta a continuación del elemento de menú seleccionado.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)