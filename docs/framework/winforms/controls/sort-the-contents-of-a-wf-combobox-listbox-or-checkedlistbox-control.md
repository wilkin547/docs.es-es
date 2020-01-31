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
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
Windows Forms controles no ordenan cuando están enlazados a datos. Para mostrar los datos ordenados, utilice un origen de datos que admita la ordenación y, a continuación, haga que el origen de datos lo ordene. Los orígenes de datos que admiten la ordenación son vistas de datos, administradores de vistas de datos y matrices ordenadas.  
  
 Si el control no está enlazado a datos, puede ordenarlo.  
  
### <a name="to-sort-the-list"></a>Para ordenar la lista  
  
1. Establezca la propiedad `Sorted` en `true`.  
  
     Esta configuración cambia la posición de todos los elementos de lista existentes en orden.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
