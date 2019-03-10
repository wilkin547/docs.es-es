---
title: Filtrar Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 4c00e853299c6eea2c97adb7f94cd7753ffa3d93
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705277"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="c709c-102">Filtrar Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="c709c-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="c709c-103">Controles de formularios Windows Forms no se ordenan cuando están enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="c709c-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="c709c-104">Para mostrar datos ordenados, utilice un origen de datos que admite la ordenación y, a continuación, tiene el origen de datos ordenarlo.</span><span class="sxs-lookup"><span data-stu-id="c709c-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="c709c-105">Orígenes de datos que admiten la ordenación son vistas de datos, ver administradores de datos y ordenan las matrices.</span><span class="sxs-lookup"><span data-stu-id="c709c-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="c709c-106">Si el control no está enlazado a datos, se puede ordenar.</span><span class="sxs-lookup"><span data-stu-id="c709c-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="c709c-107">Para ordenar la lista</span><span class="sxs-lookup"><span data-stu-id="c709c-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="c709c-108">Establezca la propiedad `Sorted` en `true`.</span><span class="sxs-lookup"><span data-stu-id="c709c-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="c709c-109">Esta configuración ordenarán en todos los elementos de lista existente.</span><span class="sxs-lookup"><span data-stu-id="c709c-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c709c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c709c-110">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="c709c-111">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c709c-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="c709c-112">Cómo: Agregar y quitar elementos de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="c709c-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="c709c-113">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="c709c-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="c709c-114">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="c709c-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
