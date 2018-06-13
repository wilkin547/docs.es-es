---
title: 'Cómo: Configurar la combinación automática de menús para aplicaciones MDI'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: e308ef8327fc439f52c4e3476a663f47fa00a379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533466"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="51e6d-102">Cómo: Configurar la combinación automática de menús para aplicaciones MDI</span><span class="sxs-lookup"><span data-stu-id="51e6d-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="51e6d-103">El siguiente procedimiento proporciona los pasos básicos para configurar la combinación automática en una aplicación de interfaz de múltiples documentos (MDI) con <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="51e6d-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="51e6d-104">Para configurar la combinación automática de menús</span><span class="sxs-lookup"><span data-stu-id="51e6d-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="51e6d-105">Crear el formulario MDI primario estableciendo su <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="51e6d-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="51e6d-106">Agregar un <xref:System.Windows.Forms.MenuStrip> para el formulario MDI primario, establecer su <xref:System.Windows.Forms.Form.MainMenuStrip%2A> propiedad a la que se <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="51e6d-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="51e6d-107">Crear un formulario MDI secundario y establecer su <xref:System.Windows.Forms.Form.MdiParent%2A> propiedad en el nombre del formulario primario.</span><span class="sxs-lookup"><span data-stu-id="51e6d-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="51e6d-108">Agregar un <xref:System.Windows.Forms.MenuStrip> para el formulario MDI secundario.</span><span class="sxs-lookup"><span data-stu-id="51e6d-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="51e6d-109">En el formulario secundario, establezca el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de la <xref:System.Windows.Forms.MenuStrip> a `false`.</span><span class="sxs-lookup"><span data-stu-id="51e6d-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="51e6d-110">Agregar elementos de menú para el formulario secundario <xref:System.Windows.Forms.MenuStrip> que desea combinar en el formulario principal <xref:System.Windows.Forms.MenuStrip> cuando se activa el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="51e6d-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="51e6d-111">Use la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> elementos de propiedad en el menú en el formulario secundario <xref:System.Windows.Forms.MenuStrip> para controlar cómo se combinan en el formulario principal.</span><span class="sxs-lookup"><span data-stu-id="51e6d-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e6d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e6d-112">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="51e6d-113">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="51e6d-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
