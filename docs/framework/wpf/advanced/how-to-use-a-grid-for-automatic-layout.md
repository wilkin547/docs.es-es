---
title: Procedimiento Usar una cuadrícula para el diseño automático
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227137"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="a6e28-102">Procedimiento Usar una cuadrícula para el diseño automático</span><span class="sxs-lookup"><span data-stu-id="a6e28-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="a6e28-103">En este ejemplo se describe cómo usar una cuadrícula en el enfoque de diseño automático para crear una aplicación localizable.</span><span class="sxs-lookup"><span data-stu-id="a6e28-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="a6e28-104">Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="a6e28-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="a6e28-105">A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto.</span><span class="sxs-lookup"><span data-stu-id="a6e28-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="a6e28-106">En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="a6e28-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="a6e28-107">Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste.</span><span class="sxs-lookup"><span data-stu-id="a6e28-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="a6e28-108">El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y posición se denomina `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="a6e28-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="a6e28-109">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto.</span><span class="sxs-lookup"><span data-stu-id="a6e28-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="a6e28-110">Tenga en cuenta que el alto y ancho de las celdas están establecidos en `Auto`; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen.</span><span class="sxs-lookup"><span data-stu-id="a6e28-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="a6e28-111">Dado que el <xref:System.Windows.Controls.Grid> elemento puede ajustarse a su contenido puede ser útil al tomar el enfoque de diseño automático para diseñar aplicaciones que se pueden localizar.</span><span class="sxs-lookup"><span data-stu-id="a6e28-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6e28-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6e28-112">Example</span></span>  
 <span data-ttu-id="a6e28-113">En el ejemplo siguiente se muestra cómo usar una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a6e28-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="a6e28-114">En el gráfico siguiente se muestra la salida del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="a6e28-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="a6e28-115">![Ejemplo de cuadrícula](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="a6e28-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="a6e28-116">Cuadrícula</span><span class="sxs-lookup"><span data-stu-id="a6e28-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e28-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6e28-117">See also</span></span>

- [<span data-ttu-id="a6e28-118">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="a6e28-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="a6e28-119">Usar el diseño automático para crear un botón</span><span class="sxs-lookup"><span data-stu-id="a6e28-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
