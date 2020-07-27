---
title: 'Cómo: Cambiar el tipo de cursor'
description: Cambiar el cursor del puntero del mouse para un elemento y para una aplicación en Windows Presentation Foundation. Este ejemplo consta de XAML y un archivo de código subyacente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165962"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="eef64-104">Cómo: Cambiar el tipo de cursor</span><span class="sxs-lookup"><span data-stu-id="eef64-104">How to: Change the Cursor Type</span></span>
<span data-ttu-id="eef64-105">En este ejemplo se muestra cómo cambiar el <xref:System.Windows.Input.Cursor> del puntero del mouse para un elemento específico y para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eef64-105">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="eef64-106">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="eef64-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eef64-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eef64-107">Example</span></span>  
 <span data-ttu-id="eef64-108">Se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.ComboBox> para seleccionar el <xref:System.Windows.Input.Cursor> objeto deseado, un par de <xref:System.Windows.Controls.RadioButton> objetos para determinar si el cambio de cursor se aplica solo a un único elemento o se aplica a toda la aplicación, y, <xref:System.Windows.Controls.Border> que es el elemento al que se aplica el nuevo cursor.</span><span class="sxs-lookup"><span data-stu-id="eef64-108">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="eef64-109">En el código subyacente siguiente se crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> controlador de eventos al que se llama cuando se cambia el tipo de cursor en <xref:System.Windows.Controls.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="eef64-109">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="eef64-110">Una instrucción switch filtra por el nombre del cursor y establece la <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad en <xref:System.Windows.Controls.Border> que se denomina *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="eef64-110">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="eef64-111">Si el cambio del cursor se establece en "toda la aplicación", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> propiedad se establece en la <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad del <xref:System.Windows.Controls.Border> control.</span><span class="sxs-lookup"><span data-stu-id="eef64-111">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="eef64-112">Esto obliga al cursor a cambiar para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eef64-112">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="eef64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eef64-113">See also</span></span>

- [<span data-ttu-id="eef64-114">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="eef64-114">Input Overview</span></span>](input-overview.md)
