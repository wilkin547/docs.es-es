---
title: "Tutoriales: Crear un botón animado personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bce1140ed11332b5bf30d487b2acacc644687d26
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="4596c-102">Tutoriales: Crear un botón animado personalizado</span><span class="sxs-lookup"><span data-stu-id="4596c-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="4596c-103">Como sugiere su nombre, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] es magnífico para crear experiencias de presentación enriquecidas para los clientes.</span><span class="sxs-lookup"><span data-stu-id="4596c-103">As its name suggests, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="4596c-104">Estos tutoriales muestra cómo personalizar la apariencia y el comportamiento de un botón (incluyendo animaciones).</span><span class="sxs-lookup"><span data-stu-id="4596c-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="4596c-105">Esta personalización se realiza mediante un estilo y una plantilla para que pueda aplicar este botón personalizado fácilmente a los botones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4596c-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="4596c-106">En la siguiente ilustración muestra el botón personalizado que va a crear.</span><span class="sxs-lookup"><span data-stu-id="4596c-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="4596c-107">![Botón personalizado que creará](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="4596c-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="4596c-108">Los gráficos vectoriales que componen el aspecto del botón se crean mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4596c-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="4596c-109">es similar a HTML pero es más eficaz y extensible.</span><span class="sxs-lookup"><span data-stu-id="4596c-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="4596c-110">pueden escribirse en forma manual mediante Microsoft Visual Studio o el Bloc de notas, o puede usar una herramienta de diseño visual como Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="4596c-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="4596c-111">Expression Blend funciona creando subyacente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código, por lo que ambos métodos crean los mismos gráficos.</span><span class="sxs-lookup"><span data-stu-id="4596c-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4596c-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4596c-112">In This Section</span></span>  
 [<span data-ttu-id="4596c-113">Crear un botón mediante Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="4596c-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="4596c-114">Muestra cómo crear botones con comportamiento personalizado mediante las características del Diseñador de Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="4596c-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="4596c-115">Crear un botón mediante el uso de XAML</span><span class="sxs-lookup"><span data-stu-id="4596c-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="4596c-116">Muestra cómo crear botones con comportamiento personalizado mediante el uso de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4596c-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4596c-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4596c-117">Related Sections</span></span>  
 [<span data-ttu-id="4596c-118">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4596c-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="4596c-119">Describe cómo pueden usarse los estilos y plantillas para determinar la apariencia y el comportamiento de los controles.</span><span class="sxs-lookup"><span data-stu-id="4596c-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="4596c-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="4596c-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="4596c-121">Describe cómo se pueden animar objetos mediante el uso de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sistema de animación y temporización.</span><span class="sxs-lookup"><span data-stu-id="4596c-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="4596c-122">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="4596c-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="4596c-123">Describe cómo usar objetos de pincel para pintar con colores sólidos, degradados lineales y degradados radiales.</span><span class="sxs-lookup"><span data-stu-id="4596c-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="4596c-124">Información general sobre efectos de imagen</span><span class="sxs-lookup"><span data-stu-id="4596c-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="4596c-125">Describe los efectos de mapa de bits compatibles con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y explica cómo aplicarlos.</span><span class="sxs-lookup"><span data-stu-id="4596c-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
