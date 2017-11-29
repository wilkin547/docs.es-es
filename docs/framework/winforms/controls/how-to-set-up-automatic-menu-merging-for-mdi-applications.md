---
title: "Cómo: Configurar la combinación automática de menús para aplicaciones MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Cómo: Configurar la combinación automática de menús para aplicaciones MDI
El siguiente procedimiento proporciona los pasos básicos para configurar la combinación automática en una aplicación de interfaz de múltiples documentos (MDI) con <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Para configurar la combinación automática de menús  
  
1.  Crear el formulario MDI primario estableciendo su <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad `true`.  
  
2.  Agregar un <xref:System.Windows.Forms.MenuStrip> para el formulario MDI primario, establecer su <xref:System.Windows.Forms.Form.MainMenuStrip%2A> propiedad a la que se <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Crear un formulario MDI secundario y establecer su <xref:System.Windows.Forms.Form.MdiParent%2A> propiedad en el nombre del formulario primario.  
  
4.  Agregar un <xref:System.Windows.Forms.MenuStrip> para el formulario MDI secundario.  
  
5.  En el formulario secundario, establezca el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de la <xref:System.Windows.Forms.MenuStrip> a `false`.  
  
6.  Agregar elementos de menú para el formulario secundario <xref:System.Windows.Forms.MenuStrip> que desea combinar en el formulario principal <xref:System.Windows.Forms.MenuStrip> cuando se activa el formulario secundario.  
  
7.  Use la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> elementos de propiedad en el menú en el formulario secundario <xref:System.Windows.Forms.MenuStrip> para controlar cómo se combinan en el formulario principal.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
