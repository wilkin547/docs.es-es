---
title: Procedimiento Proporcionar un fondo transparente a un Control
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 20815518c2a683878e0d3adf6a4bdc9261b614d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644618"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="9e5cf-102">Procedimiento Proporcionar un fondo transparente a un Control</span><span class="sxs-lookup"><span data-stu-id="9e5cf-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="9e5cf-103">En versiones anteriores de .NET Framework, los controles no admitían la opción de establecer fondos transparentes sin establecer primero el método <xref:System.Windows.Forms.Control.SetStyle%2A> en el constructor de formularios.</span><span class="sxs-lookup"><span data-stu-id="9e5cf-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="9e5cf-104">En la versión actual de .NET Framework, el color de fondo de la mayoría de los controles se puede establecer como <xref:System.Drawing.Color.Transparent%2A> en la ventana **Propiedades** durante el tiempo de diseño o como código en el constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="9e5cf-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e5cf-105">Los controles de Windows Forms no admiten una transparencia real.</span><span class="sxs-lookup"><span data-stu-id="9e5cf-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="9e5cf-106">El fondo de un control de Windows Forms transparente lo pinta su control primario.</span><span class="sxs-lookup"><span data-stu-id="9e5cf-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e5cf-107">El control <xref:System.Windows.Controls.Button> no admite un color de fondo transparente incluso si la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> se estableció como <xref:System.Drawing.Color.Transparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e5cf-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="9e5cf-108">Proporcionar un fondo transparente a un control</span><span class="sxs-lookup"><span data-stu-id="9e5cf-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="9e5cf-109">En la ventana Propiedades, elija la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> y establézcala como <xref:System.Drawing.Color.Transparent%2A></span><span class="sxs-lookup"><span data-stu-id="9e5cf-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5cf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e5cf-110">See also</span></span>
- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="9e5cf-111">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e5cf-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- <span data-ttu-id="9e5cf-112">[Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)</span><span class="sxs-lookup"><span data-stu-id="9e5cf-112">[Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)</span></span>
- [<span data-ttu-id="9e5cf-113">Cómo: Dibujar líneas opacas y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="9e5cf-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
