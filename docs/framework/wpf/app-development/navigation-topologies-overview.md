---
title: Información general sobre topologías de navegación
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 08f6342095706e5ffe9479f5236457d21474152a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174204"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="1ebde-102">Información general sobre topologías de navegación</span><span class="sxs-lookup"><span data-stu-id="1ebde-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="1ebde-103">Esta información general proporciona una introducción a las topologías de navegación en WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="1ebde-103">This overview provides an introduction to navigation topologies in WPF.</span></span> <span data-ttu-id="1ebde-104">Posteriormente, se tratan tres topologías de navegación comunes y se incluyen ejemplos de estas.</span><span class="sxs-lookup"><span data-stu-id="1ebde-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ebde-105">Antes de leer este tema, debe estar familiarizado con el concepto de navegación estructurada en WPFWPF mediante funciones de página.</span><span class="sxs-lookup"><span data-stu-id="1ebde-105">Before reading this topic, you should be familiar with the concept of structured navigation in WPF using page functions.</span></span> <span data-ttu-id="1ebde-106">Para obtener más información sobre ambos temas, vea Información general sobre [navegación estructurada](structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ebde-106">For more information on both of these topics, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="1ebde-107">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="1ebde-107">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="1ebde-108">Topologías de navegación</span><span class="sxs-lookup"><span data-stu-id="1ebde-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
- [<span data-ttu-id="1ebde-109">Topologías de navegación estructurada</span><span class="sxs-lookup"><span data-stu-id="1ebde-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
- [<span data-ttu-id="1ebde-110">Navegación mediante una topología lineal fija</span><span class="sxs-lookup"><span data-stu-id="1ebde-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [<span data-ttu-id="1ebde-111">Navegación dinámica mediante una topología jerárquica fija</span><span class="sxs-lookup"><span data-stu-id="1ebde-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [<span data-ttu-id="1ebde-112">Navegación mediante una topología generada dinámicamente</span><span class="sxs-lookup"><span data-stu-id="1ebde-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>
## <a name="navigation-topologies"></a><span data-ttu-id="1ebde-113">Topologías de navegación</span><span class="sxs-lookup"><span data-stu-id="1ebde-113">Navigation Topologies</span></span>  
 <span data-ttu-id="1ebde-114">En WPFWPF, la navegación<xref:System.Windows.Controls.Page>normalmente consta<xref:System.Windows.Documents.Hyperlink>de páginas ( ) con hipervínculos ( ) que navegan a otras páginas cuando se hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="1ebde-114">In WPF, navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="1ebde-115">Las páginas a las que se navega se identifican mediante identificadores de recursos uniformes (URI) (consulte Paquete de [URI en WPF).](pack-uris-in-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="1ebde-115">Pages that are navigated to are identified by uniform resource identifiers (URIs) (see [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="1ebde-116">Considere el siguiente ejemplo sencillo que muestra páginas, hipervínculos e identificadores uniformes de recursos (URI):</span><span class="sxs-lookup"><span data-stu-id="1ebde-116">Consider the following simple example that shows pages, hyperlinks, and uniform resource identifiers (URIs):</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="1ebde-117">Estas páginas se organizan en una topología de *navegación* cuya estructura está determinada por cómo puede navegar entre las páginas.</span><span class="sxs-lookup"><span data-stu-id="1ebde-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="1ebde-118">Esta topología de navegación concreta es adecuada en escenarios simples, aunque la navegación puede exigir topologías más complejas, algunas de las cuales solo pueden definirse cuando se ejecuta una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1ebde-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="1ebde-119">En este tema se tratan tres topologías de navegación comunes: *lineal fijo,* *jerárquico fijo*y *generado dinámicamente.*</span><span class="sxs-lookup"><span data-stu-id="1ebde-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="1ebde-120">Cada topología de navegación se muestra con [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] un ejemplo que tiene un ejemplo similar al que se muestra en la siguiente figura:</span><span class="sxs-lookup"><span data-stu-id="1ebde-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 ![Páginas de tareas con elementos de datos y botones de navegación.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>
## <a name="structured-navigation-topologies"></a><span data-ttu-id="1ebde-122">Topologías de navegación estructurada</span><span class="sxs-lookup"><span data-stu-id="1ebde-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="1ebde-123">Hay dos tipos generales de topologías de navegación:</span><span class="sxs-lookup"><span data-stu-id="1ebde-123">There are two broad types of navigation topologies:</span></span>  
  
- <span data-ttu-id="1ebde-124">**Topología fija**: se define en tiempo de compilación y no cambia en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ebde-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="1ebde-125">Las topologías fijas son útiles para la navegación a través de una secuencia fija de páginas en un orden lineal o jerárquico.</span><span class="sxs-lookup"><span data-stu-id="1ebde-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
- <span data-ttu-id="1ebde-126">**Topología dinámica**: se define en tiempo de ejecución en función de la entrada que se recopila del usuario, la aplicación o el sistema.</span><span class="sxs-lookup"><span data-stu-id="1ebde-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="1ebde-127">Las topologías dinámicas son útiles cuando las páginas pueden navegarse en secuencias diferentes.</span><span class="sxs-lookup"><span data-stu-id="1ebde-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="1ebde-128">Aunque es posible crear topologías de navegación mediante páginas, los ejemplos usan funciones de página porque proporcionan compatibilidad adicional que simplifica la compatibilidad para pasar y devolver los datos a través de las páginas de una topología.</span><span class="sxs-lookup"><span data-stu-id="1ebde-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="1ebde-129">Navegación mediante una topología lineal fija</span><span class="sxs-lookup"><span data-stu-id="1ebde-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="1ebde-130">Una topología lineal fija se parece a la estructura de un asistente que tiene una o más páginas por las que se navega en una secuencia fija.</span><span class="sxs-lookup"><span data-stu-id="1ebde-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="1ebde-131">La figura siguiente muestra la estructura de alto nivel y el flujo de un asistente con una topología lineal fija:</span><span class="sxs-lookup"><span data-stu-id="1ebde-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology:</span></span>  
  
 ![Diagrama que muestra una topología lineal fija.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 <span data-ttu-id="1ebde-133">Los comportamientos típicos de la navegación mediante una topología lineal fija son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ebde-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
- <span data-ttu-id="1ebde-134">Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="1ebde-135">No se requiere [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]una <xref:System.Windows.Navigation.PageFunction%601>página de iniciador (un -less ), ya que una página de llamada puede llamar directamente a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="1ebde-136">Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.</span><span class="sxs-lookup"><span data-stu-id="1ebde-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="1ebde-137">Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).</span><span class="sxs-lookup"><span data-stu-id="1ebde-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="1ebde-138">Los usuarios pueden navegar entre páginas mediante el diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-138">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="1ebde-139">Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="1ebde-140">Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="1ebde-141">Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.</span><span class="sxs-lookup"><span data-stu-id="1ebde-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="1ebde-142">Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.</span><span class="sxs-lookup"><span data-stu-id="1ebde-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="1ebde-143">Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="1ebde-144">Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.</span><span class="sxs-lookup"><span data-stu-id="1ebde-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="1ebde-145">Navegación dinámica mediante una topología jerárquica fija</span><span class="sxs-lookup"><span data-stu-id="1ebde-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="1ebde-146">En algunas aplicaciones, las páginas permiten la navegación a dos o más páginas, como se muestra en la siguiente figura:</span><span class="sxs-lookup"><span data-stu-id="1ebde-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure:</span></span>
  
 ![Diagrama que muestra una página que puede navegar a varias páginas.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 <span data-ttu-id="1ebde-148">Esta estructura se conoce como topología jerárquica fija, y la secuencia en la que se recorre la jerarquía a menudo la determinan en tiempo de ejecución la aplicación o el usuario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="1ebde-149">En tiempo de ejecución, cada página de la jerarquía que permite la navegación a dos o más páginas recopila los datos necesarios para determinar a qué página se debe navegar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="1ebde-150">La figura siguiente ilustra una de varias secuencias de navegación posibles basadas en la figura anterior:</span><span class="sxs-lookup"><span data-stu-id="1ebde-150">The following figure illustrates one of several possible navigation sequences based on the previous figure:</span></span>  
  
 ![Diagrama que muestra una posible secuencia de navegación.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 <span data-ttu-id="1ebde-152">Aunque la secuencia en la que se navega por las páginas de una estructura jerárquica fija se determina en tiempo de ejecución, la experiencia del usuario es la misma que la de una topología lineal fija:</span><span class="sxs-lookup"><span data-stu-id="1ebde-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
- <span data-ttu-id="1ebde-153">Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="1ebde-154">No se requiere [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]una <xref:System.Windows.Navigation.PageFunction%601>página de iniciador (un -less ), ya que una página de llamada puede llamar directamente a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="1ebde-155">Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.</span><span class="sxs-lookup"><span data-stu-id="1ebde-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="1ebde-156">Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).</span><span class="sxs-lookup"><span data-stu-id="1ebde-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="1ebde-157">Los usuarios pueden navegar entre páginas mediante el diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-157">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="1ebde-158">Los usuarios pueden cambiar la secuencia de exploración si navegan hacia atrás a través del diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
- <span data-ttu-id="1ebde-159">Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="1ebde-160">Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="1ebde-161">Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.</span><span class="sxs-lookup"><span data-stu-id="1ebde-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="1ebde-162">Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.</span><span class="sxs-lookup"><span data-stu-id="1ebde-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="1ebde-163">Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="1ebde-164">Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.</span><span class="sxs-lookup"><span data-stu-id="1ebde-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="1ebde-165">Navegación mediante una topología generada dinámicamente</span><span class="sxs-lookup"><span data-stu-id="1ebde-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="1ebde-166">En algunas aplicaciones, la secuencia en la que se navega por dos o más páginas solo la puede determinar en tiempo de ejecución el usuario, la aplicación o los datos externos.</span><span class="sxs-lookup"><span data-stu-id="1ebde-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="1ebde-167">La figura siguiente ilustra un conjunto de páginas con una secuencia de navegación indeterminada:</span><span class="sxs-lookup"><span data-stu-id="1ebde-167">The following figure illustrates a set of pages with an undetermined navigation sequence:</span></span>  
  
 ![Conjunto de páginas con una secuencia de navegación indeterminada.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 <span data-ttu-id="1ebde-169">La siguiente figura ilustra una secuencia de navegación elegida por el usuario en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="1ebde-169">The next figure illustrates a navigation sequence that was chosen by the user at run time:</span></span>  
  
 ![Diagrama que muestra una secuencia de navegación elegida en tiempo de ejecución.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 <span data-ttu-id="1ebde-171">La secuencia de navegación se conoce como topología generada dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="1ebde-172">Para el usuario, al igual que con las otras topologías de navegación, la experiencia del usuario es la misma que en las topologías anteriores:</span><span class="sxs-lookup"><span data-stu-id="1ebde-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
- <span data-ttu-id="1ebde-173">Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="1ebde-174">No se requiere [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]una <xref:System.Windows.Navigation.PageFunction%601>página de iniciador (un -less ), ya que una página de llamada puede llamar directamente a la primera página del asistente.</span><span class="sxs-lookup"><span data-stu-id="1ebde-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="1ebde-175">Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.</span><span class="sxs-lookup"><span data-stu-id="1ebde-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="1ebde-176">Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).</span><span class="sxs-lookup"><span data-stu-id="1ebde-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="1ebde-177">Los usuarios pueden navegar entre páginas mediante el diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-177">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="1ebde-178">Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="1ebde-179">Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.</span><span class="sxs-lookup"><span data-stu-id="1ebde-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="1ebde-180">Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.</span><span class="sxs-lookup"><span data-stu-id="1ebde-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="1ebde-181">Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.</span><span class="sxs-lookup"><span data-stu-id="1ebde-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="1ebde-182">Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario.</span><span class="sxs-lookup"><span data-stu-id="1ebde-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="1ebde-183">Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.</span><span class="sxs-lookup"><span data-stu-id="1ebde-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebde-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ebde-184">See also</span></span>

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="1ebde-185">Información general sobre la navegación estructurada</span><span class="sxs-lookup"><span data-stu-id="1ebde-185">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
