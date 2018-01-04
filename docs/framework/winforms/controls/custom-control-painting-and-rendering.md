---
title: "Dibujo y representación personalizados de controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 355a5842348aa4395d1841d0343080ddef634456
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="e4e96-102">Dibujo y representación personalizados de controles</span><span class="sxs-lookup"><span data-stu-id="e4e96-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="e4e96-103">Dibujo personalizado de controles es una de las muchas tareas complicadas facilitan por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4e96-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="e4e96-104">Al crear un control personalizado, se tienen muchas opciones con respecto a la apariencia del control gráfica.</span><span class="sxs-lookup"><span data-stu-id="e4e96-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="e4e96-105">Si va a crear un control que hereda de la `Control`, deberá proporcionar código que permita al control crear su representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="e4e96-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="e4e96-106">Si está creando un control de usuario mediante la herencia de la `UserControl`, o está heredando de uno de los controles de formularios Windows Forms, puede reemplazar la representación gráfica estándar y proporcionar su propio código de gráficos.</span><span class="sxs-lookup"><span data-stu-id="e4e96-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="e4e96-107">Si desea proporcionar una representación personalizada para los controles constituyentes de una `UserControl` está creando, las opciones estarán mas limitadas, pero seguirá permitan a una amplia gama de posibilidades gráficas para los controles y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4e96-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4e96-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e4e96-108">In This Section</span></span>  
 [<span data-ttu-id="e4e96-109">Representar un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4e96-109">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 <span data-ttu-id="e4e96-110">Muestra cómo programar la lógica que muestra un control.</span><span class="sxs-lookup"><span data-stu-id="e4e96-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="e4e96-111">Controles dibujados por el usuario</span><span class="sxs-lookup"><span data-stu-id="e4e96-111">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 <span data-ttu-id="e4e96-112">Ofrezca una visión general de los pasos necesarios para escribir y reemplazar código de representación para el control.</span><span class="sxs-lookup"><span data-stu-id="e4e96-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="e4e96-113">Controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="e4e96-113">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 <span data-ttu-id="e4e96-114">Describe cómo implementar código de representación personalizadas para los controles constituyentes en los formularios y los controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="e4e96-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="e4e96-115">Hacer un control no visible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e4e96-115">How to: Make Your Control Invisible at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="e4e96-116">Muestra cómo utilizar el <xref:System.Windows.Forms.Control.Visible%2A> propiedad para ocultar y mostrar un control.</span><span class="sxs-lookup"><span data-stu-id="e4e96-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="e4e96-117">Proporcionar un fondo transparente a un control</span><span class="sxs-lookup"><span data-stu-id="e4e96-117">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="e4e96-118">Muestra cómo utilizar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para crear un color de fondo opaco, transparente o parcialmente transparente.</span><span class="sxs-lookup"><span data-stu-id="e4e96-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="e4e96-119">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="e4e96-119">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="e4e96-120">Muestra cómo representar controles con estilos visuales en los sistemas operativos que las admiten.</span><span class="sxs-lookup"><span data-stu-id="e4e96-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e4e96-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="e4e96-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="e4e96-122">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e4e96-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="e4e96-123">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e4e96-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="e4e96-124">Describe este método.</span><span class="sxs-lookup"><span data-stu-id="e4e96-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4e96-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e4e96-125">Related Sections</span></span>  
 [<span data-ttu-id="e4e96-126">Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="e4e96-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="e4e96-127">Presenta [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funcionalidad de gráficos de una perspectiva y proporciona vínculos a Visual Studio para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e4e96-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="e4e96-128">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="e4e96-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="e4e96-129">Describe los tipos de controles personalizados que puede crear.</span><span class="sxs-lookup"><span data-stu-id="e4e96-129">Describes the kinds of custom controls you can author.</span></span>
