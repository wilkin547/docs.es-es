---
title: Procedimiento para ocultar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 968d34a5f79d469ef62beaa8ac96742d73391b22
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039747"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Procedimiento para ocultar ToolStripMenuItems mediante el diseñador
Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario. A menudo, querrá ocultar un menú completo cuando no estén disponibles todos los elementos de menú que hay en él. Esto supone menos distracciones para el usuario. Además, es posible que desee ocultar y deshabilitar el menú o el elemento de menú, ya que ocultar solo no impide que el usuario tenga acceso a un comando de menú mediante una tecla de método abreviado. Para obtener más información acerca de cómo deshabilitar elementos [de menú, consulte Cómo: Deshabilite ToolStripMenuItems mediante el](how-to-disable-toolstripmenuitems-using-the-designer.md)diseñador.

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Para ocultar un menú de nivel superior y sus elementos de submenú

1. Seleccione el elemento de menú de nivel superior y establezca <xref:System.Windows.Forms.ToolStripItem.Visible%2A> su <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad o `false`en.

     Cuando se oculta el elemento de menú de nivel superior, todos los elementos de menú de ese menú también se ocultan. Si hace clic en algún lugar distinto de <xref:System.Windows.Forms.MenuStrip> en el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`valor de después de, el elemento de menú de nivel superior completo y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto en tiempo de ejecución de la acción. Para mostrar el elemento de menú de nivel superior oculto en tiempo de diseño, haga <xref:System.Windows.Forms.MenuStrip> clic en en la **bandeja de componentes**, en **esquema de documento**o en la parte superior de la cuadrícula de propiedades.

> [!NOTE]
>  Rara vez ocultará un menú completo, excepto los menús secundarios de la interfaz de múltiples documentos (MDI) en un escenario de combinación.

## <a name="to-hide-a-submenu-item"></a>Para ocultar un elemento de submenú

1. Seleccione el elemento de submenú y establezca <xref:System.Windows.Forms.ToolStripItem.Visible%2A> su propiedad `false`en.

     Al ocultar un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que pueda seleccionarlo fácilmente para seguir trabajando. Realmente se ocultará en tiempo de ejecución.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
- [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](how-to-disable-toolstripmenuitems-using-the-designer.md)
