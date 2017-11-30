---
title: "Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e43a23d632b397889721373471a8fa165052d7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
Controles de formularios Windows Forms no ordenan cuando están enlazados a datos. Para mostrar datos ordenados, utilizar un origen de datos que admite la ordenación y, a continuación, hacer que el origen de datos ordene. Orígenes de datos que admiten la ordenación son vistas de datos, ver administradores de datos y las matrices ordenan.  
  
 Si el control no está enlazado a datos, se puede ordenar.  
  
### <a name="to-sort-the-list"></a>Para ordenar la lista  
  
1.  Establezca la propiedad `Sorted` en `true`.  
  
     Esta configuración cambia de posición todos los elementos de lista existentes de forma ordenada.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
