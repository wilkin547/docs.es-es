---
title: Procedimiento para definir un icono para un botón de la barra de herramientas mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 5de7645ecbf2123df849046a152643cd629b4898
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038235"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Procedimiento para definir un icono para un botón de la barra de herramientas mediante el diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.

<xref:System.Windows.Forms.ToolBar>los botones pueden mostrar iconos dentro de ellos para facilitar su identificación por parte de los usuarios. Esto se consigue mediante la adición de imágenes <xref:System.Windows.Forms.ImageList> al componente y su asociación con el <xref:System.Windows.Forms.ToolBar> control.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ToolBar> contenga un <xref:System.Windows.Forms.ImageList> control y un componente. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Para establecer un icono para un botón de la barra de herramientas en tiempo de diseño

1. Agregue imágenes al <xref:System.Windows.Forms.ImageList> componente. Para obtener más información, vea [Cómo: Agregue o quite imágenes de ImageList con el diseñador](how-to-add-or-remove-imagelist-images-with-the-designer.md).

2. Seleccione el <xref:System.Windows.Forms.ToolBar> control en el formulario.

3. En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.ToolBar> propiedad del <xref:System.Windows.Forms.ToolBar.ImageList%2A> control en el <xref:System.Windows.Forms.ImageList> componente.

4. Haga clic <xref:System.Windows.Forms.ToolBar> en la <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad del control para seleccionarla y haga clic en![los puntos suspensivos (el botón de puntos suspensivos (...) en](./media/visual-studio-ellipsis-button.png)el botón ventana Propiedades de Visual Studio.) para abrir el editor de la **colección ToolBarButton**.

5. Use el botón **Agregar** para agregar botones al <xref:System.Windows.Forms.ToolBar> control.

6. En la ventana **propiedades** que aparece en el panel de la derecha del editor de la **colección ToolBarButton**, establezca la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de cada botón de la barra de herramientas en uno de los valores de la lista, que se obtiene a partir de las imágenes que agregó al <xref:System.Windows.Forms.ImageList> componente.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolBar>
- [Cómo: Desencadenar eventos de menú para botones de barra de herramientas](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar (control)](toolbar-control-windows-forms.md)
- [ImageList (componente)](imagelist-component-windows-forms.md)
