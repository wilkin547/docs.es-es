---
title: Procedimiento para implementar la interfaz INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: cfdfb22fd854a8f630243e0f612761c71cb778d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802042"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Procedimiento para implementar la interfaz INotifyPropertyChanged
En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Implemente esta interfaz en objetos de negocios que se usan en el enlace de datos de Windows Forms. Cuando se implementa, la interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Aplicar el modelo PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
- [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
