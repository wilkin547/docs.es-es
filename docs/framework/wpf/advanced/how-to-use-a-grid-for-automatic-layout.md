---
title: "Cómo: Usar una cuadrícula para el diseño automático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d18563c44381a276d15996dff3f9552c46833b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="e22b5-102">Cómo: Usar una cuadrícula para el diseño automático</span><span class="sxs-lookup"><span data-stu-id="e22b5-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="e22b5-103">En este ejemplo se describe cómo usar una cuadrícula en el enfoque de diseño automático para crear una aplicación localizable.</span><span class="sxs-lookup"><span data-stu-id="e22b5-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="e22b5-104">Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="e22b5-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="e22b5-105">A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto.</span><span class="sxs-lookup"><span data-stu-id="e22b5-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="e22b5-106">En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="e22b5-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="e22b5-107">Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste.</span><span class="sxs-lookup"><span data-stu-id="e22b5-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="e22b5-108">El enfoque para escribir aplicaciones que pueden resultar más fácil volver a tamaño y cambia de posición se denomina `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="e22b5-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="e22b5-109">El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto.</span><span class="sxs-lookup"><span data-stu-id="e22b5-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="e22b5-110">Observe que el alto y ancho de las celdas se establecen en `Auto`; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen.</span><span class="sxs-lookup"><span data-stu-id="e22b5-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="e22b5-111">Dado que el <xref:System.Windows.Controls.Grid> elemento puede ajustar a su contenido puede ser útil cuando se toma el enfoque de diseño automático al diseño de aplicaciones que se pueden localizar.</span><span class="sxs-lookup"><span data-stu-id="e22b5-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e22b5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e22b5-112">Example</span></span>  
 <span data-ttu-id="e22b5-113">En el ejemplo siguiente se muestra cómo usar una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e22b5-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="e22b5-114">En el gráfico siguiente se muestra la salida del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="e22b5-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="e22b5-115">![Ejemplo de cuadrícula](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="e22b5-115">![Grid example](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="e22b5-116">Cuadrícula</span><span class="sxs-lookup"><span data-stu-id="e22b5-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22b5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e22b5-117">See Also</span></span>  
 [<span data-ttu-id="e22b5-118">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="e22b5-118">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="e22b5-119">Usar el diseño automático para crear un botón</span><span class="sxs-lookup"><span data-stu-id="e22b5-119">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
