---
title: "Cómo: Crear un control de formularios Windows Forms que muestre el progreso"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76ce5cd67b66dea47f5bd12e78bb27179b391257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="f2399-102">Cómo: Crear un control de formularios Windows Forms que muestre el progreso</span><span class="sxs-lookup"><span data-stu-id="f2399-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="f2399-103">En el ejemplo de código siguiente se muestra un control personalizado denominado `FlashTrackBar` que se puede utilizar para mostrar al usuario el nivel o el progreso de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2399-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="f2399-104">Utiliza un degradado para representar visualmente el progreso.</span><span class="sxs-lookup"><span data-stu-id="f2399-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="f2399-105">El control `FlashTrackBar` ilustra los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2399-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
-   <span data-ttu-id="f2399-106">Definición de propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2399-106">Defining custom properties.</span></span>  
  
-   <span data-ttu-id="f2399-107">Definición de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f2399-107">Defining custom events.</span></span> <span data-ttu-id="f2399-108">(`FlashTrackBar` define el evento `ValueChanged`).</span><span class="sxs-lookup"><span data-stu-id="f2399-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
-   <span data-ttu-id="f2399-109">Reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método para proporcionar lógica para dibujar el control.</span><span class="sxs-lookup"><span data-stu-id="f2399-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
-   <span data-ttu-id="f2399-110">Calcular el área disponible para dibujar el control mediante su <xref:System.Windows.Forms.Control.ClientRectangle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f2399-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="f2399-111">`FlashTrackBar` hace esto en el método `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="f2399-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
-   <span data-ttu-id="f2399-112">Implementación de la serialización o persistencia de una propiedad cuando se cambia en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f2399-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="f2399-113">`FlashTrackBar` define los métodos `ShouldSerializeStartColor` y `ShouldSerializeEndColor` para la serialización de las propiedades `StartColor` y `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="f2399-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="f2399-114">En la tabla siguiente se muestran las propiedades personalizadas definidas por `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="f2399-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="f2399-115">Property</span><span class="sxs-lookup"><span data-stu-id="f2399-115">Property</span></span>|<span data-ttu-id="f2399-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2399-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="f2399-117">Indica si el usuario puede cambiar el valor de la barra de seguimiento flash haciendo clic y arrastrando.</span><span class="sxs-lookup"><span data-stu-id="f2399-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="f2399-118">Especifica el color final de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2399-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="f2399-119">Especifica cuánto oscurecer el fondo en relación con el degradado de primer plano.</span><span class="sxs-lookup"><span data-stu-id="f2399-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="f2399-120">Especifica el valor máximo de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2399-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="f2399-121">Especifica el valor mínimo de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2399-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="f2399-122">Especifica el color inicial del degradado.</span><span class="sxs-lookup"><span data-stu-id="f2399-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="f2399-123">Indica si mostrar un porcentaje sobre el degradado.</span><span class="sxs-lookup"><span data-stu-id="f2399-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="f2399-124">Indica si mostrar el valor actual sobre el degradado.</span><span class="sxs-lookup"><span data-stu-id="f2399-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="f2399-125">Indica si la barra de seguimiento debe mostrar un degradado de color con el valor actual.</span><span class="sxs-lookup"><span data-stu-id="f2399-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="f2399-126">Especifica el valor actual de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2399-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="f2399-127">La siguiente tabla muestra los miembros adicionales definidos por el evento de cambio de propiedad `FlashTrackBar:` y el método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="f2399-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="f2399-128">Miembro</span><span class="sxs-lookup"><span data-stu-id="f2399-128">Member</span></span>|<span data-ttu-id="f2399-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2399-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="f2399-130">El evento que se genera cuando la propiedad `Value` la barra de seguimiento cambia.</span><span class="sxs-lookup"><span data-stu-id="f2399-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="f2399-131">El método que genera el evento `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="f2399-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f2399-132">`FlashTrackBar`usa el <xref:System.EventArgs> clase para datos de evento y <xref:System.EventHandler> como delegado del evento.</span><span class="sxs-lookup"><span data-stu-id="f2399-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="f2399-133">Para controlar la correspondiente *EventName* eventos, `FlashTrackBar` invalida los métodos siguientes que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f2399-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="f2399-134">Para controlar los eventos de cambio de propiedad correspondientes, `FlashTrackBar` invalida los métodos siguientes que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f2399-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="f2399-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2399-135">Example</span></span>  
 <span data-ttu-id="f2399-136">El control `FlashTrackBar` define dos editores de tipos de interfaz de usuario, `FlashTrackBarValueEditor` y `FlashTrackBarDarkenByEditor`, que se muestran en los listados de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2399-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="f2399-137">La clase `HostApp` utiliza el control `FlashTrackBar` en un formulario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f2399-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="f2399-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2399-138">See Also</span></span>  
 [<span data-ttu-id="f2399-139">Ampliar compatibilidad en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="f2399-139">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="f2399-140">Fundamentos de desarrollo de controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2399-140">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)
