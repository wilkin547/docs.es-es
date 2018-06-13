---
title: 'Cómo: Usar el diseño automático para crear un botón'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 34b372e886b31e801b5598da90299f9815c47620
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545219"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="57139-102">Cómo: Usar el diseño automático para crear un botón</span><span class="sxs-lookup"><span data-stu-id="57139-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="57139-103">En este ejemplo se describe cómo usar el enfoque de diseño automático para crear un botón en una aplicación localizable.</span><span class="sxs-lookup"><span data-stu-id="57139-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="57139-104">Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="57139-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="57139-105">A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto.</span><span class="sxs-lookup"><span data-stu-id="57139-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="57139-106">En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="57139-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="57139-107">Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste.</span><span class="sxs-lookup"><span data-stu-id="57139-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="57139-108">El enfoque para escribir aplicaciones que pueden resultar más fácilmente cuyo tamaño ha cambiado y cambia de posición se denomina `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="57139-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="57139-109">Las dos siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos crean aplicaciones que crean instancias de un botón: uno con texto en inglés y otro con texto en español.</span><span class="sxs-lookup"><span data-stu-id="57139-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="57139-110">Observe que el código es el mismo, salvo para el texto; el botón se ajusta para adaptarse al texto.</span><span class="sxs-lookup"><span data-stu-id="57139-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57139-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57139-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="57139-112">En el gráfico siguiente se muestra la salida de los ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="57139-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="57139-113">![El mismo botón con texto en diferentes idiomas](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="57139-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="57139-114">Botón ajustable automáticamente</span><span class="sxs-lookup"><span data-stu-id="57139-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57139-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="57139-115">See Also</span></span>  
 [<span data-ttu-id="57139-116">Información general sobre el uso del diseño automático</span><span class="sxs-lookup"><span data-stu-id="57139-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="57139-117">Usar una cuadrícula para el diseño automático</span><span class="sxs-lookup"><span data-stu-id="57139-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
