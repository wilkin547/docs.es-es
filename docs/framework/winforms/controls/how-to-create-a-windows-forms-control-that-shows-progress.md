---
title: Crear control que muestra el progreso
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731176"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="ecafe-102">Cómo: Crear un control de formularios Windows Forms que muestre el progreso</span><span class="sxs-lookup"><span data-stu-id="ecafe-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="ecafe-103">En el ejemplo de código siguiente se muestra un control personalizado denominado `FlashTrackBar` que se puede utilizar para mostrar al usuario el nivel o el progreso de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ecafe-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="ecafe-104">Utiliza un degradado para representar visualmente el progreso.</span><span class="sxs-lookup"><span data-stu-id="ecafe-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="ecafe-105">El control `FlashTrackBar` ilustra los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecafe-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="ecafe-106">Definición de propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ecafe-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="ecafe-107">Definición de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ecafe-107">Defining custom events.</span></span> <span data-ttu-id="ecafe-108">(`FlashTrackBar` define el evento `ValueChanged`).</span><span class="sxs-lookup"><span data-stu-id="ecafe-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="ecafe-109">Reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A> para proporcionar la lógica para dibujar el control.</span><span class="sxs-lookup"><span data-stu-id="ecafe-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="ecafe-110">Calcular el área disponible para dibujar el control mediante su <xref:System.Windows.Forms.Control.ClientRectangle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ecafe-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="ecafe-111">`FlashTrackBar` hace esto en el método `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="ecafe-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="ecafe-112">Implementación de la serialización o persistencia de una propiedad cuando se cambia en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecafe-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="ecafe-113">`FlashTrackBar` define los métodos `ShouldSerializeStartColor` y `ShouldSerializeEndColor` para la serialización de las propiedades `StartColor` y `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="ecafe-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="ecafe-114">En la tabla siguiente se muestran las propiedades personalizadas definidas por `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="ecafe-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="ecafe-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ecafe-115">Property</span></span>|<span data-ttu-id="ecafe-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecafe-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="ecafe-117">Indica si el usuario puede cambiar el valor de la barra de seguimiento flash haciendo clic y arrastrando.</span><span class="sxs-lookup"><span data-stu-id="ecafe-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="ecafe-118">Especifica el color final de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecafe-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="ecafe-119">Especifica cuánto oscurecer el fondo en relación con el degradado de primer plano.</span><span class="sxs-lookup"><span data-stu-id="ecafe-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="ecafe-120">Especifica el valor máximo de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecafe-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="ecafe-121">Especifica el valor mínimo de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecafe-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="ecafe-122">Especifica el color inicial del degradado.</span><span class="sxs-lookup"><span data-stu-id="ecafe-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="ecafe-123">Indica si mostrar un porcentaje sobre el degradado.</span><span class="sxs-lookup"><span data-stu-id="ecafe-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="ecafe-124">Indica si mostrar el valor actual sobre el degradado.</span><span class="sxs-lookup"><span data-stu-id="ecafe-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="ecafe-125">Indica si la barra de seguimiento debe mostrar un degradado de color con el valor actual.</span><span class="sxs-lookup"><span data-stu-id="ecafe-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="ecafe-126">Especifica el valor actual de la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecafe-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="ecafe-127">La siguiente tabla muestra los miembros adicionales definidos por el evento de cambio de propiedad `FlashTrackBar:` y el método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="ecafe-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="ecafe-128">Member</span><span class="sxs-lookup"><span data-stu-id="ecafe-128">Member</span></span>|<span data-ttu-id="ecafe-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecafe-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="ecafe-130">El evento que se genera cuando la propiedad `Value` la barra de seguimiento cambia.</span><span class="sxs-lookup"><span data-stu-id="ecafe-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="ecafe-131">El método que genera el evento `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="ecafe-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="ecafe-132">`FlashTrackBar` usa la clase <xref:System.EventArgs> para los datos de evento y <xref:System.EventHandler> para el delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="ecafe-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="ecafe-133">Para controlar los eventos *eventName* correspondientes, `FlashTrackBar` reemplaza los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="ecafe-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="ecafe-134">Para controlar los eventos de cambio de propiedad correspondientes, `FlashTrackBar` reemplaza los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="ecafe-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="ecafe-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecafe-135">Example</span></span>  
 <span data-ttu-id="ecafe-136">El control `FlashTrackBar` define dos editores de tipos de interfaz de usuario, `FlashTrackBarValueEditor` y `FlashTrackBarDarkenByEditor`, que se muestran en los listados de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ecafe-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="ecafe-137">La clase `HostApp` utiliza el control `FlashTrackBar` en un formulario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecafe-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="ecafe-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ecafe-138">See also</span></span>

- <span data-ttu-id="ecafe-139">[Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ecafe-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="ecafe-140">Fundamentos de desarrollo de controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecafe-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
