---
title: Información general sobre el uso del diseño automático
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: a9f04f6da4dc4024f4c9ece19f045eb8e3775e6a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620880"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="f1027-102">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="f1027-102">Use Automatic Layout Overview</span></span>
<span data-ttu-id="f1027-103">Este tema presentan las directrices para desarrolladores sobre cómo escribir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones con localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1027-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="f1027-104">En el pasado, la localización de una interfaz de usuario era un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="f1027-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="f1027-105">Todos los idiomas que se adaptaba la interfaz de usuario requiere un ajuste píxel a píxel.</span><span class="sxs-lookup"><span data-stu-id="f1027-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="f1027-106">Hoy en día con el diseño correcto y derecha estándares de codificación, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] puede crearse para que los localizadores deban realizar menos el cambio de tamaño y posición.</span><span class="sxs-lookup"><span data-stu-id="f1027-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="f1027-107">El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y la posición se denomina diseño automático y se puede lograr mediante el uso de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1027-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="f1027-108">Ventajas de usar el diseño automático</span><span class="sxs-lookup"><span data-stu-id="f1027-108">Advantages of Using Automatic Layout</span></span>  
 <span data-ttu-id="f1027-109">Dado que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de presentación es eficaz y flexible, proporciona la capacidad de diseñar elementos en una aplicación que se pueden ajustar para ajustarse a los requisitos de idiomas diferentes.</span><span class="sxs-lookup"><span data-stu-id="f1027-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="f1027-110">En la lista siguiente se indican algunas de las ventajas del diseño automático.</span><span class="sxs-lookup"><span data-stu-id="f1027-110">The following list points out some of the advantages of automatic layout.</span></span>  

- <span data-ttu-id="f1027-111">Interfaz de usuario se muestra correctamente en cualquier idioma.</span><span class="sxs-lookup"><span data-stu-id="f1027-111">UI displays well  in any language.</span></span>  

- <span data-ttu-id="f1027-112">Reduce la necesidad de reajustar la posición y el tamaño de los controles una vez traducido el texto.</span><span class="sxs-lookup"><span data-stu-id="f1027-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>  
  
- <span data-ttu-id="f1027-113">Reduce la necesidad de reajustar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="f1027-113">Reduces the need to readjust window size.</span></span>  

- <span data-ttu-id="f1027-114">Diseño de interfaz de usuario se representa correctamente en cualquier lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f1027-114">UI layout renders properly in any language.</span></span>  

- <span data-ttu-id="f1027-115">La localización se puede reducir hasta el punto de que es poco más que la traducción de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f1027-115">Localization can be reduced to the point that it is little more than string translation.</span></span>  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a><span data-ttu-id="f1027-116">Diseño automático y controles</span><span class="sxs-lookup"><span data-stu-id="f1027-116">Automatic Layout and Controls</span></span>  
 <span data-ttu-id="f1027-117">El diseño automático permite que una aplicación ajuste automáticamente el tamaño de un control.</span><span class="sxs-lookup"><span data-stu-id="f1027-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="f1027-118">Por ejemplo, un control puede cambiar para adaptarse a la longitud de una cadena.</span><span class="sxs-lookup"><span data-stu-id="f1027-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="f1027-119">Esta capacidad permite a los localizadores traducir la cadena sin necesidad de cambiar el tamaño del control para que se ajuste al texto traducido.</span><span class="sxs-lookup"><span data-stu-id="f1027-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="f1027-120">En el ejemplo siguiente se crea un botón con contenido en inglés.</span><span class="sxs-lookup"><span data-stu-id="f1027-120">The following example creates a button with English content.</span></span>  
  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="f1027-121">En el ejemplo, lo único que debe hacer para crear un botón en español es cambiar el texto.</span><span class="sxs-lookup"><span data-stu-id="f1027-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="f1027-122">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f1027-122">For example,</span></span>  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="f1027-123">El gráfico siguiente muestra la salida de los ejemplos de código:</span><span class="sxs-lookup"><span data-stu-id="f1027-123">The following graphic shows the output of the code samples:</span></span>  
  
 ![El mismo botón con texto en diferentes idiomas](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="f1027-125">Diseño automático y estándares de codificación</span><span class="sxs-lookup"><span data-stu-id="f1027-125">Automatic Layout and Coding Standards</span></span>  
 <span data-ttu-id="f1027-126">Con el enfoque de diseño automático requiere un conjunto de código y los estándares de diseño y las reglas para generar una interfaz de usuario totalmente localizable.</span><span class="sxs-lookup"><span data-stu-id="f1027-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="f1027-127">Las instrucciones siguientes le ayudarán en la codificación del diseño automático.</span><span class="sxs-lookup"><span data-stu-id="f1027-127">The following guidelines will aid your automatic layout coding.</span></span>  

<span data-ttu-id="f1027-128">**No use posiciones absolutas**</span><span class="sxs-lookup"><span data-stu-id="f1027-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="f1027-129">No utilice <xref:System.Windows.Controls.Canvas> porque absolutamente coloca los elementos.</span><span class="sxs-lookup"><span data-stu-id="f1027-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="f1027-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, y <xref:System.Windows.Controls.Grid> para colocar los controles.</span><span class="sxs-lookup"><span data-stu-id="f1027-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="f1027-131">Para obtener información sobre los distintos tipos de paneles, consulte [información general sobre](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f1027-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="f1027-132">**No establezca un tamaño fijo para una ventana**</span><span class="sxs-lookup"><span data-stu-id="f1027-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="f1027-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1027-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f1027-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f1027-134">For example:</span></span>

   [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="f1027-135">**Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="f1027-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="f1027-136">Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A> al elemento raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1027-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

   <span data-ttu-id="f1027-137">WPF proporciona una manera cómoda de admitir horizontales, bidireccionales y diseños verticales.</span><span class="sxs-lookup"><span data-stu-id="f1027-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="f1027-138">En el marco de presentación, el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad puede usarse para definir el diseño.</span><span class="sxs-lookup"><span data-stu-id="f1027-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="f1027-139">Los patrones de dirección de flujo son:</span><span class="sxs-lookup"><span data-stu-id="f1027-139">The flow-direction patterns are:</span></span>
   
     - <span data-ttu-id="f1027-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb): diseño horizontal para latín, Asia oriental y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f1027-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>
     
     - <span data-ttu-id="f1027-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb): bidireccional para árabe, hebreo y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f1027-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="f1027-142">**Use fuentes compuestas en lugar de fuentes físicas**</span><span class="sxs-lookup"><span data-stu-id="f1027-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="f1027-143">Con las fuentes compuestas, el <xref:System.Windows.Controls.Control.FontFamily%2A> propiedad no deben localizarse.</span><span class="sxs-lookup"><span data-stu-id="f1027-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="f1027-144">Los desarrolladores pueden usar una de las fuentes siguientes o crear sus propias fuentes.</span><span class="sxs-lookup"><span data-stu-id="f1027-144">Developers can use one of the following fonts or create their own.</span></span>

   - <span data-ttu-id="f1027-145">Interfaz de usuario global</span><span class="sxs-lookup"><span data-stu-id="f1027-145">Global User Interface</span></span>
   - <span data-ttu-id="f1027-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="f1027-146">Global San Serif</span></span>
   - <span data-ttu-id="f1027-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="f1027-147">Global Serif</span></span>

<span data-ttu-id="f1027-148">**Agregue XML: lang**</span><span class="sxs-lookup"><span data-stu-id="f1027-148">**Add xml:lang**</span></span>

- <span data-ttu-id="f1027-149">Agregar el `xml:lang` atributo en el elemento raíz de la interfaz de usuario, como `xml:lang="en-US"` para una aplicación en inglés.</span><span class="sxs-lookup"><span data-stu-id="f1027-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="f1027-150">Dado que las fuentes compuestas usan `xml:lang` para determinar qué fuente quiere usar, establezca esta propiedad para admitir escenarios multilingües.</span><span class="sxs-lookup"><span data-stu-id="f1027-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a><span data-ttu-id="f1027-151">Diseño automático y cuadrículas</span><span class="sxs-lookup"><span data-stu-id="f1027-151">Automatic Layout and Grids</span></span>  
 <span data-ttu-id="f1027-152">El <xref:System.Windows.Controls.Grid> elemento, es útil para el diseño automático porque permite al programador colocar los elementos.</span><span class="sxs-lookup"><span data-stu-id="f1027-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="f1027-153">Un <xref:System.Windows.Controls.Grid> control es capaz de distribuir el espacio disponible entre sus elementos secundarios, en una disposición de columna y fila.</span><span class="sxs-lookup"><span data-stu-id="f1027-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="f1027-154">Los elementos de interfaz de usuario pueden abarcar varias celdas, y es posible que haya cuadrículas dentro de cuadrículas.</span><span class="sxs-lookup"><span data-stu-id="f1027-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="f1027-155">Las cuadrículas son útiles porque permiten crear y colocar la IU es compleja.</span><span class="sxs-lookup"><span data-stu-id="f1027-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="f1027-156">En el ejemplo siguiente se muestra cómo se usa una cuadrícula para colocar algunos botones y texto.</span><span class="sxs-lookup"><span data-stu-id="f1027-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="f1027-157">Tenga en cuenta que el alto y ancho de las celdas están establecidos en <xref:System.Windows.GridUnitType.Auto>; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen.</span><span class="sxs-lookup"><span data-stu-id="f1027-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>  

 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="f1027-158">En el gráfico siguiente se muestra la cuadrícula que ha producido el código anterior.</span><span class="sxs-lookup"><span data-stu-id="f1027-158">The following graphic shows the grid produced by the previous code.</span></span>  
  
 <span data-ttu-id="f1027-159">![Ejemplo de cuadrícula](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="f1027-159">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="f1027-160">Cuadrícula</span><span class="sxs-lookup"><span data-stu-id="f1027-160">Grid</span></span>  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="f1027-161">Diseño automático y cuadrículas mediante el uso de la propiedad IsSharedSizeScope</span><span class="sxs-lookup"><span data-stu-id="f1027-161">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>  
 <span data-ttu-id="f1027-162">Un <xref:System.Windows.Controls.Grid> elemento es útil en aplicaciones localizables para crear controles que se ajustan al contenido.</span><span class="sxs-lookup"><span data-stu-id="f1027-162">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="f1027-163">Pero en ocasiones le interesará que los controles conserven un tamaño determinado independientemente del contenido.</span><span class="sxs-lookup"><span data-stu-id="f1027-163">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="f1027-164">Por ejemplo, si tiene los botones "Aceptar", "Cancelar" y "Examinar", probablemente no le interesará que su tamaño se ajuste el contenido.</span><span class="sxs-lookup"><span data-stu-id="f1027-164">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="f1027-165">En este caso el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> propiedad adjunta es útil para compartir el mismo tamaño entre varios elementos de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f1027-165">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="f1027-166">En el ejemplo siguiente se muestra cómo compartir datos entre varias de tamaño de fila y columna <xref:System.Windows.Controls.Grid> elementos.</span><span class="sxs-lookup"><span data-stu-id="f1027-166">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="f1027-167">**Tenga en cuenta** para el ejemplo de código completo, vea [recurso compartido de las propiedades de ajuste de tamaño entre cuadrículas](../controls/how-to-share-sizing-properties-between-grids.md)</span><span class="sxs-lookup"><span data-stu-id="f1027-167">**Note** For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1027-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1027-168">See also</span></span>

- [<span data-ttu-id="f1027-169">Globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="f1027-169">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="f1027-170">Usar el diseño automático para crear un botón</span><span class="sxs-lookup"><span data-stu-id="f1027-170">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="f1027-171">Usar una cuadrícula para el diseño automático</span><span class="sxs-lookup"><span data-stu-id="f1027-171">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
