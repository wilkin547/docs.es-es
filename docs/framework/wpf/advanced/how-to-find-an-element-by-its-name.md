---
title: 'Cómo: Buscar un elemento por su nombre'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: e2d176c9334c0a1d4c10819e0dc9f2c408e41d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543581"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="a5f46-102">Cómo: Buscar un elemento por su nombre</span><span class="sxs-lookup"><span data-stu-id="a5f46-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="a5f46-103">En este ejemplo se describe cómo utilizar el <xref:System.Windows.FrameworkElement.FindName%2A> método para buscar un elemento por su <xref:System.Windows.FrameworkElement.Name%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="a5f46-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5f46-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5f46-104">Example</span></span>  
 <span data-ttu-id="a5f46-105">En este ejemplo, el método para buscar un elemento determinado por su nombre se escribe como el controlador de eventos de un botón.</span><span class="sxs-lookup"><span data-stu-id="a5f46-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="a5f46-106">`stackPanel` es el <xref:System.Windows.FrameworkElement.Name%2A> de la raíz de <xref:System.Windows.FrameworkElement> que se va a buscar, y el método de ejemplo, a continuación, indica visualmente el elemento encontrado convirtiendo como <xref:System.Windows.Controls.TextBlock> y cambiar uno de los <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] propiedades.</span><span class="sxs-lookup"><span data-stu-id="a5f46-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
