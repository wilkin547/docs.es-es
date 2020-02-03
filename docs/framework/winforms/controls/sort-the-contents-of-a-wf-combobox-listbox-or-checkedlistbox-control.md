---
title: Ordenar el contenido del control ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742956"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="991f5-102">Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="991f5-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="991f5-103">Windows Forms controles no ordenan cuando están enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="991f5-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="991f5-104">Para mostrar los datos ordenados, utilice un origen de datos que admita la ordenación y, a continuación, haga que el origen de datos lo ordene.</span><span class="sxs-lookup"><span data-stu-id="991f5-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="991f5-105">Los orígenes de datos que admiten la ordenación son vistas de datos, administradores de vistas de datos y matrices ordenadas.</span><span class="sxs-lookup"><span data-stu-id="991f5-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="991f5-106">Si el control no está enlazado a datos, puede ordenarlo.</span><span class="sxs-lookup"><span data-stu-id="991f5-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="991f5-107">Para ordenar la lista</span><span class="sxs-lookup"><span data-stu-id="991f5-107">To sort the list</span></span>  
  
1. <span data-ttu-id="991f5-108">Establezca la propiedad `Sorted` en `true`.</span><span class="sxs-lookup"><span data-stu-id="991f5-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="991f5-109">Esta configuración cambia la posición de todos los elementos de lista existentes en orden.</span><span class="sxs-lookup"><span data-stu-id="991f5-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991f5-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="991f5-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="991f5-111">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="991f5-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="991f5-112">Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="991f5-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="991f5-113">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="991f5-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="991f5-114">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="991f5-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
