---
title: "Cómo: recibir una notificación cuando un reloj de &#39; s cambios de estado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="a254e-102">Cómo: recibir una notificación cuando un reloj de &#39; s cambios de estado</span><span class="sxs-lookup"><span data-stu-id="a254e-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="a254e-103">Un reloj <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento tiene lugar cuando su <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> deja de ser válido, por ejemplo, cuando se inicia o detiene el reloj.</span><span class="sxs-lookup"><span data-stu-id="a254e-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="a254e-104">Puede registrarse para este evento con directamente mediante un <xref:System.Windows.Media.Animation.Clock>, o puede registrar con un <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="a254e-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="a254e-105">En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.Storyboard> y dos <xref:System.Windows.Media.Animation.DoubleAnimation> objetos se usan para animar el ancho de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="a254e-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="a254e-106">El <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> eventos se usan para realizar escuchas de los cambios de estado de reloj.</span><span class="sxs-lookup"><span data-stu-id="a254e-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a254e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a254e-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="a254e-108">En la siguiente ilustración muestra los distintos Estados en las animaciones se especifica como la escala de tiempo primaria (*guión gráfico*) progresa.</span><span class="sxs-lookup"><span data-stu-id="a254e-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="a254e-109">![Estados de reloj para guión gráfico con dos animaciones](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="a254e-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="a254e-110">La siguiente tabla muestra las horas en que *Animation1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> desencadena el evento:</span><span class="sxs-lookup"><span data-stu-id="a254e-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="a254e-111">Tiempo (segundos)</span><span class="sxs-lookup"><span data-stu-id="a254e-111">Time (Seconds)</span></span>|<span data-ttu-id="a254e-112">1</span><span class="sxs-lookup"><span data-stu-id="a254e-112">1</span></span>|<span data-ttu-id="a254e-113">10</span><span class="sxs-lookup"><span data-stu-id="a254e-113">10</span></span>|<span data-ttu-id="a254e-114">19</span><span class="sxs-lookup"><span data-stu-id="a254e-114">19</span></span>|<span data-ttu-id="a254e-115">21</span><span class="sxs-lookup"><span data-stu-id="a254e-115">21</span></span>|<span data-ttu-id="a254e-116">30</span><span class="sxs-lookup"><span data-stu-id="a254e-116">30</span></span>|<span data-ttu-id="a254e-117">39</span><span class="sxs-lookup"><span data-stu-id="a254e-117">39</span></span>|  
|<span data-ttu-id="a254e-118">Estado</span><span class="sxs-lookup"><span data-stu-id="a254e-118">State</span></span>|<span data-ttu-id="a254e-119">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-119">Active</span></span>|<span data-ttu-id="a254e-120">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-120">Active</span></span>|<span data-ttu-id="a254e-121">Detenido</span><span class="sxs-lookup"><span data-stu-id="a254e-121">Stopped</span></span>|<span data-ttu-id="a254e-122">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-122">Active</span></span>|<span data-ttu-id="a254e-123">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-123">Active</span></span>|<span data-ttu-id="a254e-124">Detenido</span><span class="sxs-lookup"><span data-stu-id="a254e-124">Stopped</span></span>|  
  
 <span data-ttu-id="a254e-125">La siguiente tabla muestra las horas en que *Animation2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> desencadena el evento:</span><span class="sxs-lookup"><span data-stu-id="a254e-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="a254e-126">Tiempo (segundos)</span><span class="sxs-lookup"><span data-stu-id="a254e-126">Time (Seconds)</span></span>|<span data-ttu-id="a254e-127">1</span><span class="sxs-lookup"><span data-stu-id="a254e-127">1</span></span>|<span data-ttu-id="a254e-128">9</span><span class="sxs-lookup"><span data-stu-id="a254e-128">9</span></span>|<span data-ttu-id="a254e-129">11</span><span class="sxs-lookup"><span data-stu-id="a254e-129">11</span></span>|<span data-ttu-id="a254e-130">19</span><span class="sxs-lookup"><span data-stu-id="a254e-130">19</span></span>|<span data-ttu-id="a254e-131">21</span><span class="sxs-lookup"><span data-stu-id="a254e-131">21</span></span>|<span data-ttu-id="a254e-132">29</span><span class="sxs-lookup"><span data-stu-id="a254e-132">29</span></span>|<span data-ttu-id="a254e-133">31</span><span class="sxs-lookup"><span data-stu-id="a254e-133">31</span></span>|<span data-ttu-id="a254e-134">39</span><span class="sxs-lookup"><span data-stu-id="a254e-134">39</span></span>|  
|<span data-ttu-id="a254e-135">Estado</span><span class="sxs-lookup"><span data-stu-id="a254e-135">State</span></span>|<span data-ttu-id="a254e-136">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-136">Active</span></span>|<span data-ttu-id="a254e-137">Rellenar</span><span class="sxs-lookup"><span data-stu-id="a254e-137">Filling</span></span>|<span data-ttu-id="a254e-138">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-138">Active</span></span>|<span data-ttu-id="a254e-139">Detenido</span><span class="sxs-lookup"><span data-stu-id="a254e-139">Stopped</span></span>|<span data-ttu-id="a254e-140">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-140">Active</span></span>|<span data-ttu-id="a254e-141">Rellenar</span><span class="sxs-lookup"><span data-stu-id="a254e-141">Filling</span></span>|<span data-ttu-id="a254e-142">Activo</span><span class="sxs-lookup"><span data-stu-id="a254e-142">Active</span></span>|<span data-ttu-id="a254e-143">Detenido</span><span class="sxs-lookup"><span data-stu-id="a254e-143">Stopped</span></span>|  
  
 <span data-ttu-id="a254e-144">Tenga en cuenta que *Animation1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento se desencadena en 10 segundos, aunque su estado sigue siendo <xref:System.Windows.Media.Animation.ClockState.Active>.</span><span class="sxs-lookup"><span data-stu-id="a254e-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="a254e-145">Eso es porque su estado cambia a 10 segundos, pero cambió de <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> y, a continuación, de nuevo a <xref:System.Windows.Media.Animation.ClockState.Active> en el mismo paso.</span><span class="sxs-lookup"><span data-stu-id="a254e-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
