---
title: "Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms | Microsoft Docs"
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
  - "acciones del diseñador"
  - "modelo de objetos DesignerAction"
  - "etiquetas inteligentes"
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms
Cuando crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que debe realizar repetidamente.  Éstas son algunas de las tareas que realiza normalmente con las que se puede encontrar:  
  
-   Agregar o quitar una ficha en un <xref:System.Windows.Forms.TabControl>.  
  
-   Acoplar un control a su elemento primario.  
  
-   Cambiar la orientación de un control <xref:System.Windows.Forms.SplitContainer>.  
  
 Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que permiten realizar tareas comunes como éstas en tiempo de diseño con un solo gesto.  Estas tareas se denominan *verbos de etiquetas inteligentes*.  
  
 Las etiquetas inteligentes permanecen asociadas a una instancia de control mientras existan en el diseñador y siempre están disponibles.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms  
  
-   Utilizar las etiquetas inteligentes  
  
-   Habilitar y deshabilitar las etiquetas inteligentes  
  
 Al finalizar, podrá entender el rol que desempeñan estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basado en Windows llamado "SmartTagsExample".  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el **Diseñador de Windows Forms**.  
  
## Utilizar las etiquetas inteligentes  
 Las etiquetas inteligentes siempre están disponibles en tiempo de diseño en los controles que las proporcionan.  
  
#### Para utilizar las etiquetas inteligentes  
  
1.  Arrastre un <xref:System.Windows.Forms.TabControl> desde el **Cuadro de herramientas** al formulario.  Observe el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) que aparece junto a <xref:System.Windows.Forms.TabControl>.  
  
2.  Haga clic en el glifo de la etiqueta inteligente.  En el menú contextual que aparece al lado del glifo, seleccione el elemento **Agregar ficha**.  Observe que se agrega una nueva página de fichas a <xref:System.Windows.Forms.TabControl>.  
  
3.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
4.  Haga clic en el glifo de la etiqueta inteligente.  En el menú contextual que aparece al lado del glifo, seleccione el elemento **Agregar columna**.  Observe que se agrega una nueva columna al control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
5.  Arrastre un control <xref:System.Windows.Forms.SplitContainer> desde el **Cuadro de herramientas** al formulario.  
  
6.  Haga clic en el glifo de la etiqueta inteligente.  En el menú contextual que aparece al lado del glifo, seleccione el elemento **Orientación del divisor horizontal**.  Observe que la barra divisora del control <xref:System.Windows.Forms.SplitContainer> está ahora orientada horizontalmente.  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 <xref:System.Windows.Forms.TabControl>   
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.ComponentModel.Design.DesignerActionList>   
 [Walkthrough: Adding Smart Tags to a Windows Forms Component](../Topic/Walkthrough:%20Adding%20Smart%20Tags%20to%20a%20Windows%20Forms%20Component.md)