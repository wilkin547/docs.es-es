---
title: Procedimiento Definir márgenes de elementos y controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052370"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="ccae0-102">Procedimiento Definir márgenes de elementos y controles</span><span class="sxs-lookup"><span data-stu-id="ccae0-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="ccae0-103">En este ejemplo se describe cómo establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad, al cambiar cualquier valor de propiedad existente para el margen en el código subyacente.</span><span class="sxs-lookup"><span data-stu-id="ccae0-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="ccae0-104">El <xref:System.Windows.FrameworkElement.Margin%2A> propiedad es una propiedad de la <xref:System.Windows.FrameworkElement> basar el elemento y, por tanto, es heredado por una variedad de controles y otros elementos.</span><span class="sxs-lookup"><span data-stu-id="ccae0-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="ccae0-105">Este ejemplo está escrito en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un código subyacente de los archivos que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia a.</span><span class="sxs-lookup"><span data-stu-id="ccae0-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="ccae0-106">El código subyacente se muestra tanto en un C# y una versión de Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ccae0-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccae0-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccae0-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
