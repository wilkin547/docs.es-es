---
title: Barra de herramientas (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 027c96bb49e9446244e4b08ba93c551ef043b3c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735452"
---
# <a name="toolbar-control-windows-forms"></a>Barra de herramientas (Control, formularios Windows Forms)
> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control `ToolBar`; sin embargo, el control `ToolBar` se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El control `ToolBar` de Windows Forms se usa en los formularios como una barra de controles que muestra una fila de menús desplegables y botones de mapa de bits que activan comandos. Por lo tanto, hacer clic en un botón de barra de herramientas equivale a elegir un comando de menú. Los botones pueden configurarse para que aparezcan y se comporten como botones de comando, menús desplegables o separadores. Normalmente, una barra de herramientas contiene botones y menús que se corresponden con los elementos de la estructura de menús de una aplicación y proporciona acceso rápido a las funciones y los comandos de una aplicación que se usan con más frecuencia.  
  
> [!NOTE]
> La propiedad `ToolBar` del control <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> propiedad toma una instancia de la clase <xref:System.Windows.Forms.ContextMenu> como referencia. Tenga en cuenta la referencia que pasa al implementar esta clase de botón en las barras de herramientas de su aplicación, porque la propiedad aceptará cualquier objeto que herede de la clase <xref:System.Windows.Forms.Menu>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general del control ToolBar](toolbar-control-overview-windows-forms.md)  
 Presenta los conceptos generales del control `ToolBar`, que permite diseñar barras de herramientas personalizadas con las que los usuarios pueden trabajar.  
  
 [Agregar botones a un control ToolBar](how-to-add-buttons-to-a-toolbar-control.md)  
 Describe cómo agregar botones a un control `ToolBar`.  
  
 [Definir un icono para un botón ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)  
 Describe cómo mostrar iconos dentro de los botones del control `ToolBar`.  
  
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Proporciona instrucciones sobre cómo escribir código para interpretar en que botón hace clic el usuario en un control `ToolBar`.  
  
 Consulte también [Cómo: definir un icono para un botón de la barra de herramientas mediante el diseñador](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [Cómo: agregar botones a un control Toolbar mediante el diseñador](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).  
  
## <a name="reference"></a>Referencia  
 Clase <xref:System.Windows.Forms.ToolBar>  
 Contiene información de referencia sobre la clase y sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)  
 Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.  
  
 [ToolStrip (control)](toolstrip-control-windows-forms.md)  
 Describe las barras de herramientas que pueden hospedar menús, controles y controles de usuario en aplicaciones de Windows Forms.
