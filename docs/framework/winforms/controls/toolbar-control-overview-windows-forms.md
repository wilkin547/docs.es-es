---
title: Información general del control ToolBar (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: c7c19783963bb315a0356979797c6f4d4e3b9e08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929595"
---
# <a name="toolbar-control-overview-windows-forms"></a>Información general del control ToolBar (formularios Windows Forms)
> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El control <xref:System.Windows.Forms.ToolBar> de Windows Forms se usa en los formularios como una barra de controles que muestra una fila de menús desplegables y botones de mapa de bits que activan comandos. Por lo tanto, hacer clic en un botón de la barra de herramientas puede equivaler a elegir un comando de menú. Los botones pueden configurarse para que aparezcan y se comporten como botones de comando, menús desplegables o separadores. Normalmente, una barra de herramientas contiene botones y menús que se corresponden con los elementos de la estructura de menús de una aplicación y proporciona acceso rápido a las funciones y los comandos de una aplicación que se usan con más frecuencia.  
  
## <a name="working-with-the-toolbar-control"></a>Trabajo con el control ToolBar  
 Un <xref:System.Windows.Forms.ToolBar> control suele estar "acoplado" a lo largo de la parte superior de su ventana primaria, pero también se puede acoplar a cualquier lado de la ventana. Una barra de herramientas puede mostrar información sobre herramientas cuando el usuario sitúa el puntero del mouse sobre un botón de la barra de herramientas. La información sobre herramientas es una pequeña ventana emergente en la que se describe brevemente la función del botón o menú. Para mostrar información sobre herramientas, <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> la propiedad debe establecerse `true`en.  
  
> [!NOTE]
> Algunas aplicaciones tienen controles muy similares a la barra de herramientas, que tienen la capacidad de "flotar" sobre la ventana de la aplicación y se pueden cambiar de posición. El control ToolBar de Windows Forms no es capaz de realizar estas acciones.  
  
 Cuando la <xref:System.Windows.Forms.ToolBar.Appearance%2A> propiedad está establecida en <xref:System.Windows.Forms.ToolBarAppearance>, los botones de la barra de herramientas aparecen como elevados y tridimensionales. Puede establecer la <xref:System.Windows.Forms.ToolBar.Appearance%2A> propiedad de la barra de herramientas <xref:System.Windows.Forms.ToolBarAppearance> en para dar una apariencia plana a la barra de herramientas y sus botones. Cuando el puntero del mouse se mueve sobre un botón plano, el aspecto del botón cambia a tridimensional. Los botones de la barra de herramientas pueden dividirse en grupos lógicos mediante separadores. Un separador es un botón de la <xref:System.Windows.Forms.ToolBarButton.Style%2A> barra de herramientas <xref:System.Windows.Forms.ToolBarButtonStyle>con la propiedad establecida en. Aparece como un espacio vacío en la barra de herramientas. Cuando la barra de herramientas tiene un aspecto plano, los separadores de botones aparecen como líneas en lugar de como espacios entre los botones.  
  
 El <xref:System.Windows.Forms.ToolBar> control permite crear barras de herramientas agregando <xref:System.Windows.Forms.Button> objetos a una <xref:System.Windows.Forms.ToolBar.Buttons%2A> colección. Puede usar el editor de la colección para agregar botones a <xref:System.Windows.Forms.ToolBar> un control; <xref:System.Windows.Forms.Button> cada objeto debe tener un texto o una imagen asignados, aunque puede asignar ambos. Un componente [ImageList](imagelist-component-windows-forms.md) asociado proporciona la imagen. En tiempo de ejecución, puede Agregar o quitar botones de <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> mediante los <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> métodos y <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> . Para programar los botones de un <xref:System.Windows.Forms.ToolBar>, agregue código a los <xref:System.Windows.Forms.ToolBar.ButtonClick> eventos de <xref:System.Windows.Forms.ToolBar>, utilizando la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> propiedad de la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase para determinar en qué botón se hizo clic.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolBar>
- [ToolBar (control)](toolbar-control-windows-forms.md)
- [Procedimientos: Agregar botones a un control ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Cómo: Definir un icono para un botón de la barra de herramientas](how-to-define-an-icon-for-a-toolbar-button.md)
- [Cómo: Desencadenar eventos de menú para botones de barra de herramientas](how-to-trigger-menu-events-for-toolbar-buttons.md)
