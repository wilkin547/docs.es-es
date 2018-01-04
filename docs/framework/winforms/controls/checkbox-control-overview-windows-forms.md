---
title: "Información general sobre el control CheckBox (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39645a02cd66d37d61df72028ab129677edb757e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="11cb1-102">Información general sobre el control CheckBox (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="11cb1-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="11cb1-103">El control de Windows Forms <xref:System.Windows.Forms.CheckBox> indica si una condición determinada está activada o desactivada.</span><span class="sxs-lookup"><span data-stu-id="11cb1-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="11cb1-104">Normalmente se utiliza para presentar una selección Sí/No o Verdadero/Falso al usuario.</span><span class="sxs-lookup"><span data-stu-id="11cb1-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="11cb1-105">Puede utilizar de controles de casilla en grupos para mostrar múltiples opciones de entre las que el usuario puede seleccionar una o más.</span><span class="sxs-lookup"><span data-stu-id="11cb1-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="11cb1-106">El control de casilla de verificación es similar al control de botón de radio en que cada uno se utiliza para indicar una selección realizada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="11cb1-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="11cb1-107">Se diferencian en que se puede seleccionar solo un botón en un grupo de a la vez.</span><span class="sxs-lookup"><span data-stu-id="11cb1-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="11cb1-108">Sin embargo, con el control de casilla de verificación, cualquier número de casillas de verificación puede ser seleccionado.</span><span class="sxs-lookup"><span data-stu-id="11cb1-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="11cb1-109">Una casilla de verificación puede estar conectada a los elementos de una base de datos mediante el enlace de datos simple.</span><span class="sxs-lookup"><span data-stu-id="11cb1-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="11cb1-110">También puede agrupar varias casillas de verificación medio el <xref:System.Windows.Forms.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="11cb1-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="11cb1-111">Esto es útil para la apariencia visual y también para el diseño de la interfaz de usuario, ya que los controles agrupados pueden usarse conjuntamente en el Diseñador de formularios.</span><span class="sxs-lookup"><span data-stu-id="11cb1-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="11cb1-112">Para obtener más información, consulte [enlace de datos en formularios Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) y [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="11cb1-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="11cb1-113">El <xref:System.Windows.Forms.CheckBox> control tiene dos propiedades importantes, <xref:System.Windows.Forms.CheckBox.Checked%2A> y <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span><span class="sxs-lookup"><span data-stu-id="11cb1-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="11cb1-114">El <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="11cb1-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="11cb1-115">El <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad devuelve <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; o bien, si la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> también pueden devolver <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="11cb1-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="11cb1-116">En el estado indeterminado, el cuadro se muestra con un aspecto atenuado para indicar que la opción está disponible.</span><span class="sxs-lookup"><span data-stu-id="11cb1-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cb1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="11cb1-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="11cb1-118">Establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11cb1-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="11cb1-119">Responder a clics en casillas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11cb1-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="11cb1-120">CheckBox (control)</span><span class="sxs-lookup"><span data-stu-id="11cb1-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
