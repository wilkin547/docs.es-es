---
title: "Informaci&#243;n general del control ToolBar (formularios Windows Forms) | Microsoft Docs"
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
  - "ToolBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolBar (control) [Windows Forms], acerca de los controles ToolBar"
  - "barras de herramientas [Windows Forms], acerca de las barras de herramientas"
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general del control ToolBar (formularios Windows Forms)
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>, este control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 El control <xref:System.Windows.Forms.ToolBar> de formularios Windows Forms se utiliza en los formularios como una barra de controles que muestra una fila de menús desplegables y botones de mapas de bits que activan comandos.  Por lo tanto, hacer clic en un botón de una barra de herramientas puede ser un equivalente a elegir un comando de menú.  Puede configurar los botones para que aparezcan y se comporten como botones de comando, menús desplegables o separadores.  Habitualmente, una barra de herramientas contiene botones y menús que corresponden a los elementos de la estructura de menús de una aplicación y proporciona acceso rápido a las funciones y comandos de la aplicación de uso más frecuente.  
  
## Trabajar con el control ToolBar  
 Un control <xref:System.Windows.Forms.ToolBar> suele estar "acoplado" en la parte superior de su ventana primaria, pero también se puede acoplar a cualquier lado de la ventana.  Una barra de herramientas puede mostrar información sobre herramientas cuando el usuario sitúa el puntero del mouse en un botón de la barra.  La información sobre herramientas es una pequeña ventana emergente que describe de forma breve el propósito del botón o del menú.  Para mostrar información sobre herramientas, debe establecerse la propiedad <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> en `true`.  
  
> [!NOTE]
>  Algunas aplicaciones tienen controles muy similares a la barra de herramientas que tienen la capacidad de "flotar" sobre la ventana de la aplicación y cuya posición se puede cambiar.  El control ToolBar de formularios Windows Forms no puede realizar estas acciones.  
  
 Cuando la propiedad <xref:System.Windows.Forms.ToolBar.Appearance%2A> se establece en [Normal](frlrfSystemWindowsFormsToolBarAppearanceClassTopic), los botones de la barra de herramientas aparecen realzados en tres dimensiones.  Puede establecer la propiedad <xref:System.Windows.Forms.ToolBar.Appearance%2A> de la barra de herramientas en <xref:System.Windows.Forms.ToolBarAppearance> para proporcionar a la barra de herramientas y a sus botones una apariencia plana.  Cuando el puntero del mouse se mueve sobre un botón plano, la apariencia del botón cambia a tridimensional.  Los botones de las barras de herramientas pueden dividirse en grupos lógicos por medio de separadores.  Un separador es un botón de barra de herramientas con la propiedad <xref:System.Windows.Forms.ToolBarButton.Style%2A> establecida en [Separator](frlrfSystemWindowsFormsToolBarButtonStyleClassTopic).  Aparece como un espacio vacío en la barra de herramientas.  Cuando la barra de herramientas tiene una apariencia plana, los separadores de botones aparecen como líneas, en lugar de cómo espacios entre los botones.  
  
 El control <xref:System.Windows.Forms.ToolBar> le permite crear barras de herramientas si agrega objetos <xref:System.Windows.Forms.Button> a una colección <xref:System.Windows.Forms.ToolBar.Buttons%2A>.  Puede utilizar el Editor de la colección para agregar botones a un control <xref:System.Windows.Forms.ToolBar>; cada objeto <xref:System.Windows.Forms.Button> debe tener asignado texto o una imagen, aunque puede asignar ambos.  La imagen la proporciona un componente [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) asociado.  En tiempo de ejecución, puede agregar o quitar botones de <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> mediante los métodos <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> y <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A>.  Para programar los botones de un <xref:System.Windows.Forms.ToolBar>, agregue código a los eventos <xref:System.Windows.Forms.ToolBar.ButtonClick> del control <xref:System.Windows.Forms.ToolBar> usando la propiedad <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> de la clase <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> para determinar en qué botón se hizo clic.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolBar>   
 [Barra de herramientas \(Control\)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [Cómo: Agregar botones a un control ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Cómo: Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)