---
title: "Información general del control ToolBar (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857cc04af6c619035fa2bf0a548053f57292f7bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="toolbar-control-overview-windows-forms"></a>Información general del control ToolBar (formularios Windows Forms)
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El control <xref:System.Windows.Forms.ToolBar> de Windows Forms se usa en los formularios como una barra de controles que muestra una fila de menús desplegables y botones de mapa de bits que activan comandos. Por lo tanto, hacer clic en un botón de la barra de herramientas puede equivaler a elegir un comando de menú. Los botones pueden configurarse para que aparezcan y se comporten como botones de comando, menús desplegables o separadores. Normalmente, una barra de herramientas contiene botones y menús que se corresponden con los elementos de la estructura de menús de una aplicación y proporciona acceso rápido a las funciones y los comandos de una aplicación que se usan con más frecuencia.  
  
## <a name="working-with-the-toolbar-control"></a>Trabajo con el control ToolBar  
 Un <xref:System.Windows.Forms.ToolBar> control suele estar "acoplado" a lo largo de la parte superior de su ventana primaria, pero también se puede acoplar a cualquier lado de la ventana. Una barra de herramientas puede mostrar información sobre herramientas cuando el usuario sitúa el puntero del mouse sobre un botón de la barra de herramientas. La información sobre herramientas es una pequeña ventana emergente en la que se describe brevemente la función del botón o menú. Para mostrar información sobre herramientas, el <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> propiedad debe establecerse en `true`.  
  
> [!NOTE]
>  Algunas aplicaciones tienen controles muy similares a la barra de herramientas, que tienen la capacidad de "flotar" sobre la ventana de la aplicación y se pueden cambiar de posición. El control ToolBar de Windows Forms no es capaz de realizar estas acciones.  
  
 Cuando el <xref:System.Windows.Forms.ToolBar.Appearance%2A> propiedad está establecida en <xref:System.Windows.Forms.ToolBarAppearance>, los botones de barra de herramientas aparecen tridimensional hacia arriba o hacia abajo. Puede establecer la <xref:System.Windows.Forms.ToolBar.Appearance%2A> propiedad de la barra de herramientas <xref:System.Windows.Forms.ToolBarAppearance> para conceder a la barra de herramientas y sus botones una apariencia plana. Cuando el puntero del mouse se mueve sobre un botón plano, el aspecto del botón cambia a tridimensional. Los botones de la barra de herramientas pueden dividirse en grupos lógicos mediante separadores. Un separador es un botón de barra de herramientas con el <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad establecida en <xref:System.Windows.Forms.ToolBarButtonStyle>. Aparece como un espacio vacío en la barra de herramientas. Cuando la barra de herramientas tiene un aspecto plano, los separadores de botones aparecen como líneas en lugar de como espacios entre los botones.  
  
 El <xref:System.Windows.Forms.ToolBar> control le permite crear barras de herramientas mediante la adición de <xref:System.Windows.Forms.Button> objetos a un <xref:System.Windows.Forms.ToolBar.Buttons%2A> colección. Puede usar el Editor de colecciones para agregar botones a un <xref:System.Windows.Forms.ToolBar> control; cada <xref:System.Windows.Forms.Button> el objeto debe tener texto o una imagen asignada, aunque puede asignar ambos. Un componente [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) asociado proporciona la imagen. En tiempo de ejecución, puede agregar o quitar botones, desde el <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> mediante la <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> y <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> métodos. Para programar los botones de una <xref:System.Windows.Forms.ToolBar>, agregue código a la <xref:System.Windows.Forms.ToolBar.ButtonClick> eventos de la <xref:System.Windows.Forms.ToolBar>, utilizando el <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> propiedad de la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase para determinar qué botón se hizo clic.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolBar>  
 [ToolBar (control)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [Agregar botones a un control ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 [Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)
