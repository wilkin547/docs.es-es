---
title: Filtrar Usar el diseño automático para crear un botón
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 8eb1e93dd87c210812c9b7758c744a616ef2d862
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409788"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="58eb5-102">Filtrar Usar el diseño automático para crear un botón</span><span class="sxs-lookup"><span data-stu-id="58eb5-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="58eb5-103">En este ejemplo se describe cómo usar el enfoque de diseño automático para crear un botón en una aplicación localizable.</span><span class="sxs-lookup"><span data-stu-id="58eb5-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="58eb5-104">Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="58eb5-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="58eb5-105">A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto.</span><span class="sxs-lookup"><span data-stu-id="58eb5-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="58eb5-106">En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="58eb5-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="58eb5-107">Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste.</span><span class="sxs-lookup"><span data-stu-id="58eb5-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="58eb5-108">El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y la posición se denomina `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="58eb5-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58eb5-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58eb5-109">Example</span></span>  

<span data-ttu-id="58eb5-110">Las dos siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos crean aplicaciones que crean instancias de un botón; una con texto en inglés y otra con texto en español.</span><span class="sxs-lookup"><span data-stu-id="58eb5-110">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="58eb5-111">Observe que el código es el mismo, salvo para el texto; el botón se ajusta para adaptarse al texto.</span><span class="sxs-lookup"><span data-stu-id="58eb5-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="58eb5-112">El gráfico siguiente muestra la salida de los ejemplos de código con los botones de tamaño variable automática:</span><span class="sxs-lookup"><span data-stu-id="58eb5-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![El mismo botón con texto en diferentes idiomas](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="58eb5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="58eb5-114">See also</span></span>

- [<span data-ttu-id="58eb5-115">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="58eb5-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="58eb5-116">Usar una cuadrícula para el diseño automático</span><span class="sxs-lookup"><span data-stu-id="58eb5-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
