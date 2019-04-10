---
title: Filtrar para configurar la combinación automática de menús para aplicaciones MDI
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301248"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Filtrar para configurar la combinación automática de menús para aplicaciones MDI
El siguiente procedimiento proporcionan los pasos básicos para configurar la combinación automática en una aplicación de interfaz de múltiples documentos (MDI) con <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Para configurar la combinación automática de menús  
  
1. Crear formulario primario MDI estableciendo su <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad `true`.  
  
2. Agregar un <xref:System.Windows.Forms.MenuStrip> con el elemento primario MDI, establecer su <xref:System.Windows.Forms.Form.MainMenuStrip%2A> propiedad a la que <xref:System.Windows.Forms.MenuStrip>.  
  
3. Cree un formulario MDI secundario y establezca su <xref:System.Windows.Forms.Form.MdiParent%2A> propiedad en el nombre del formulario primario.  
  
4. Agregar un <xref:System.Windows.Forms.MenuStrip> al formulario secundario MDI.  
  
5. En el formulario secundario, establezca el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de la <xref:System.Windows.Forms.MenuStrip> a `false`.  
  
6. Agregar elementos de menú para el formulario secundario <xref:System.Windows.Forms.MenuStrip> que desee combinar en el formulario primario <xref:System.Windows.Forms.MenuStrip> cuando se activa el formulario secundario.  
  
7. Use la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> elementos de propiedad en el menú en el formulario secundario <xref:System.Windows.Forms.MenuStrip> para controlar cómo se combinan en el formulario principal.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
