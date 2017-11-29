---
title: "Cómo: Cambiar el tipo de cursor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41cd8c9cd647c7efbc4e6cf13517ed638245e51c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="fd679-102">Cómo: Cambiar el tipo de cursor</span><span class="sxs-lookup"><span data-stu-id="fd679-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="fd679-103">Este ejemplo muestra cómo cambiar la <xref:System.Windows.Input.Cursor> del puntero del mouse para un elemento específico y para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd679-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="fd679-104">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="fd679-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd679-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd679-105">Example</span></span>  
 <span data-ttu-id="fd679-106">Se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.ComboBox> para seleccionar lo que se desea <xref:System.Windows.Input.Cursor>, un par de <xref:System.Windows.Controls.RadioButton> objetos para determinar si el cambio del cursor se aplica a un solo elemento o se aplica a toda la aplicación y un <xref:System.Windows.Controls.Border> que es el elemento que se aplica el nuevo cursor.</span><span class="sxs-lookup"><span data-stu-id="fd679-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="fd679-107">Crea el siguiente código detrás de un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> controlador de eventos que se llama cuando se cambia el tipo de cursor en el <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="fd679-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="fd679-108">Una instrucción switch se filtra según el nombre del cursor y establece la <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad en el <xref:System.Windows.Controls.Border> que se denomina *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="fd679-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="fd679-109">Si el cambio del cursor se establece en "Toda aplicación", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> propiedad está establecida en el <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad de la <xref:System.Windows.Controls.Border> control.</span><span class="sxs-lookup"><span data-stu-id="fd679-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="fd679-110">Esto obliga al cursor a cambiar para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd679-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="fd679-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd679-111">See Also</span></span>  
 [<span data-ttu-id="fd679-112">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="fd679-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
