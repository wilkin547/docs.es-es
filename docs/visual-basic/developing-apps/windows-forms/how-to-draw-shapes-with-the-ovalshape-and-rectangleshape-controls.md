---
title: "Cómo: Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53d91d10cc4735bbae521d17d05045cc7ea75fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="90062-102">Cómo: Dibujar formas con los controles OvalShape y RectangleShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="90062-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="90062-103">Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> para dibujar círculos u óvalos en un formulario o contenedor, tanto en tiempo de diseño como en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="90062-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="90062-104">Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> para dibujar cuadrados, rectángulos o rectángulos con esquinas redondeadas en un formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="90062-105">También puede utilizar este control para dibujar formas en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="90062-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="90062-106">Puede personalizar la apariencia de una forma cambiando el ancho, el color y el estilo del borde.</span><span class="sxs-lookup"><span data-stu-id="90062-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="90062-107">El fondo de una forma es transparente de manera predeterminada. Puede personalizar el fondo para mostrar un color sólido, una trama, un relleno de degradado (transición de un color a otro) o una imagen.</span><span class="sxs-lookup"><span data-stu-id="90062-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="90062-108">Dibujar una forma simple en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="90062-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="90062-109">Arrastre el <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> o <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controlar desde la **Visual Basic PowerPacks** ficha (para instalar, consulte [controles Power Packs de Visual Basic](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) en el **cuadro de herramientas** para un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-110">Arrastre los controladores de tamaño y movimiento para cambiar el tamaño y la posición de la forma.</span><span class="sxs-lookup"><span data-stu-id="90062-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="90062-111">También puede cambiar el tamaño y posición de la forma cambiando el `Size` y `Position` propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="90062-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="90062-112">Para crear un rectángulo con esquinas redondeadas, seleccione la `CornerRadius` propiedad en el **propiedades** ventana y establézcalo en un valor que es mayor que 0.</span><span class="sxs-lookup"><span data-stu-id="90062-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="90062-113">En el **propiedades** ventana, puede configurar otras propiedades para cambiar la apariencia de la forma.</span><span class="sxs-lookup"><span data-stu-id="90062-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="90062-114">Dibujar una forma simple en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="90062-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="90062-115">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="90062-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="90062-116">En el **Agregar referencia** cuadro de diálogo, seleccione **Microsoft.VisualBasic.PowerPacks.VS**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90062-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="90062-117">En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:</span><span class="sxs-lookup"><span data-stu-id="90062-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="90062-118">Agregue el código siguiente en un procedimiento `Event`:</span><span class="sxs-lookup"><span data-stu-id="90062-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="90062-119">Personalizar las formas</span><span class="sxs-lookup"><span data-stu-id="90062-119">Customizing Shapes</span></span>  
 <span data-ttu-id="90062-120">Cuando se utiliza la configuración predeterminada, los controles <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> y <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> se muestran con un borde negro sólido de un píxel de ancho y con un fondo transparente.</span><span class="sxs-lookup"><span data-stu-id="90062-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="90062-121">Puede cambiar el ancho, el estilo y el color del borde estableciendo las propiedades.</span><span class="sxs-lookup"><span data-stu-id="90062-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="90062-122">Las propiedades adicionales le permiten cambiar el fondo de una forma a un color sólido, una trama, un relleno de degradado o una imagen.</span><span class="sxs-lookup"><span data-stu-id="90062-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="90062-123">Antes de cambiar el fondo de una forma, debe saber cómo interactúan algunas de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="90062-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="90062-124">El valor de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> no tiene ningún efecto a menos que la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="90062-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="90062-125">Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> reemplaza a <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="90062-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="90062-126">Si la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> se establece en un valor de trama como <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> o <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, la trama se mostrará en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="90062-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="90062-127">El fondo se mostrarán en el <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, siempre y cuando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> se haya establecido en <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="90062-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="90062-128">Para mostrar un relleno de degradado, la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> debe establecerse en <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> y la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> debe establecerse en un valor distinto de <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="90062-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="90062-129">La configuración de la propiedad <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> en una imagen reemplaza todas las demás opciones de fondo.</span><span class="sxs-lookup"><span data-stu-id="90062-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="90062-130">Dibujar un círculo con un borde personalizado</span><span class="sxs-lookup"><span data-stu-id="90062-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="90062-131">Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-132">En el **propiedades** ventana, en la `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="90062-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="90062-133">Establezca la propiedad `BorderColor` en el color que desee.</span><span class="sxs-lookup"><span data-stu-id="90062-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="90062-134">Establezca la propiedad `BorderStyle` en cualquier valor distinto de `Solid`.</span><span class="sxs-lookup"><span data-stu-id="90062-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="90062-135">Establezca el `BorderWidth` en el tamaño que desee, en píxeles.</span><span class="sxs-lookup"><span data-stu-id="90062-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="90062-136">Dibujar un círculo con un relleno sólido</span><span class="sxs-lookup"><span data-stu-id="90062-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="90062-137">Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-138">En el **propiedades** ventana, en la `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="90062-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="90062-139">Establezca la propiedad `BackColor` en el color que desee.</span><span class="sxs-lookup"><span data-stu-id="90062-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="90062-140">Establezca la propiedad `BackStyle` en `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="90062-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="90062-141">Dibujar un círculo con un relleno de trama</span><span class="sxs-lookup"><span data-stu-id="90062-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="90062-142">Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-143">En el **propiedades** ventana, en la `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="90062-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="90062-144">Establezca la propiedad `BackColor` en el color que desee para el fondo.</span><span class="sxs-lookup"><span data-stu-id="90062-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="90062-145">Establezca la propiedad `BackStyle` en `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="90062-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="90062-146">Establezca la propiedad `FillColor` en el color que desee para la trama.</span><span class="sxs-lookup"><span data-stu-id="90062-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="90062-147">Establezca la propiedad `FillStyle` en un valor distinto de `Transparent` o `Solid`.</span><span class="sxs-lookup"><span data-stu-id="90062-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="90062-148">Dibujar un círculo con un relleno de degradado</span><span class="sxs-lookup"><span data-stu-id="90062-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="90062-149">Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-150">En el **propiedades** ventana, en la `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="90062-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="90062-151">Establezca la propiedad `FillColor` en el color que desee para el color inicial.</span><span class="sxs-lookup"><span data-stu-id="90062-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="90062-152">Establezca la propiedad `FillGradientColor` en el color que desee para el color final.</span><span class="sxs-lookup"><span data-stu-id="90062-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="90062-153">Establezca la propiedad `FillGradientStyle` en un valor distinto de `None`.</span><span class="sxs-lookup"><span data-stu-id="90062-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="90062-154">Dibujar un círculo que se rellena con una imagen</span><span class="sxs-lookup"><span data-stu-id="90062-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="90062-155">Arrastre el `OvalShape` controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="90062-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="90062-156">En el **propiedades** ventana, en la `Size` establecer la propiedad, `Height` y `Width` en los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="90062-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="90062-157">Seleccione el `BackgroundImage` propiedad y haga clic en el **puntos suspensivos** botón (…).</span><span class="sxs-lookup"><span data-stu-id="90062-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="90062-158">En el **Seleccionar recurso** cuadro de diálogo, seleccione una imagen para mostrar.</span><span class="sxs-lookup"><span data-stu-id="90062-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="90062-159">Si no aparece ningún recurso de imagen, haga clic en **importación** para ir a la ubicación de una imagen.</span><span class="sxs-lookup"><span data-stu-id="90062-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="90062-160">Haga clic en **Aceptar** para insertar la imagen.</span><span class="sxs-lookup"><span data-stu-id="90062-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90062-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="90062-161">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [<span data-ttu-id="90062-162">Introducción a los controles de líneas y formas</span><span class="sxs-lookup"><span data-stu-id="90062-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="90062-163">Dibujar líneas con el control LineShape</span><span class="sxs-lookup"><span data-stu-id="90062-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
