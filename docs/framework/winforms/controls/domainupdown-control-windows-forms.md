---
title: DomainUpDown (Control, formularios Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37cec82876edadfed5cda338ca12775ad19ae732
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="eb653-102">DomainUpDown (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="eb653-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="eb653-103">Los formularios Windows Forms <xref:System.Windows.Forms.DomainUpDown> control es similar a una combinación de un cuadro de texto y un par de botones para moverse hacia arriba o hacia abajo por una lista.</span><span class="sxs-lookup"><span data-stu-id="eb653-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="eb653-104">El control muestra y establece una cadena de texto en una lista de opciones.</span><span class="sxs-lookup"><span data-stu-id="eb653-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="eb653-105">El usuario puede seleccionar la cadena, haga clic en Subir y Bajar botones para desplazarse a través de una lista, presionando las teclas de dirección arriba y abajo o escribiendo una cadena que coincide con un elemento en la lista.</span><span class="sxs-lookup"><span data-stu-id="eb653-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="eb653-106">Un uso posible para este control es para seleccionar elementos de una lista ordenada alfabéticamente de nombres.</span><span class="sxs-lookup"><span data-stu-id="eb653-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="eb653-107">(Para ordenar la lista, establezca la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> propiedad `true`.) La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa muy poco espacio.</span><span class="sxs-lookup"><span data-stu-id="eb653-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="eb653-108">Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb653-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="eb653-109">El <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad contiene la lista de objetos cuyos valores de texto se muestran en el control.</span><span class="sxs-lookup"><span data-stu-id="eb653-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="eb653-110">Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que escribe el usuario y lo hace coincidir con un valor en la lista.</span><span class="sxs-lookup"><span data-stu-id="eb653-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="eb653-111">Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, al desplazarse más allá del último elemento irá al primer elemento en la lista y viceversa.</span><span class="sxs-lookup"><span data-stu-id="eb653-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="eb653-112">Los métodos principales del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb653-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="eb653-113">Este control muestra solo las cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="eb653-113">This control displays only text strings.</span></span> <span data-ttu-id="eb653-114">Si desea un control que muestra valores numéricos, utilice el <xref:System.Windows.Forms.NumericUpDown> control.</span><span class="sxs-lookup"><span data-stu-id="eb653-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="eb653-115">Para obtener más información, consulte [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="eb653-115">For more information, see [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb653-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eb653-116">In This Section</span></span>  
 [<span data-ttu-id="eb653-117">Información general sobre el control DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="eb653-117">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="eb653-118">Presenta los conceptos generales de la <xref:System.Windows.Forms.DomainUpDown> control, lo que permite a los usuarios examinar y seleccionar de una lista de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="eb653-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="eb653-119">Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="eb653-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="eb653-120">Describe cómo especificar las cadenas de texto el <xref:System.Windows.Forms.DomainUpDown> control debe mostrar.</span><span class="sxs-lookup"><span data-stu-id="eb653-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="eb653-121">Quitar elementos de los controles DomainUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb653-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="eb653-122">Describe cómo eliminar elementos de la <xref:System.Windows.Forms.DomainUpDown> control en el código.</span><span class="sxs-lookup"><span data-stu-id="eb653-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eb653-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="eb653-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="eb653-124">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="eb653-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="eb653-125">Describe esta clase y contiene vínculos a todos sus miembros...</span><span class="sxs-lookup"><span data-stu-id="eb653-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eb653-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="eb653-126">Related Sections</span></span>  
 [<span data-ttu-id="eb653-127">Controles que puede utilizar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb653-127">Controls You Can Use On Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="eb653-128">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="eb653-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
