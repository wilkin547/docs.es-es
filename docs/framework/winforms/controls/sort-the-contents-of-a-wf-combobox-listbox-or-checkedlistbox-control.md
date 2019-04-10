---
title: Filtrar para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: bd26d396c238bfc53858320b8f4487df84b3436a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312584"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="00ffc-102">Filtrar para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ffc-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="00ffc-103">Controles de formularios Windows Forms no se ordenan cuando están enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="00ffc-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="00ffc-104">Para mostrar datos ordenados, utilice un origen de datos que admite la ordenación y, a continuación, tiene el origen de datos ordenarlo.</span><span class="sxs-lookup"><span data-stu-id="00ffc-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="00ffc-105">Orígenes de datos que admiten la ordenación son vistas de datos, ver administradores de datos y ordenan las matrices.</span><span class="sxs-lookup"><span data-stu-id="00ffc-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="00ffc-106">Si el control no está enlazado a datos, se puede ordenar.</span><span class="sxs-lookup"><span data-stu-id="00ffc-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="00ffc-107">Para ordenar la lista</span><span class="sxs-lookup"><span data-stu-id="00ffc-107">To sort the list</span></span>  
  
1. <span data-ttu-id="00ffc-108">Establezca la propiedad `Sorted` en `true`.</span><span class="sxs-lookup"><span data-stu-id="00ffc-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="00ffc-109">Esta configuración ordenarán en todos los elementos de lista existente.</span><span class="sxs-lookup"><span data-stu-id="00ffc-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ffc-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ffc-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="00ffc-111">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ffc-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="00ffc-112">Filtrar para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ffc-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="00ffc-113">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="00ffc-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="00ffc-114">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="00ffc-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
