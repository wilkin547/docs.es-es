---
title: Procedimiento para implementar la interfaz INotifyPropertyChanged
description: Obtenga información sobre cómo implementar la interfaz INotifyPropertyChanged en objetos comerciales que se usan en Windows Forms enlace de datos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619273"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Procedimiento para implementar la interfaz INotifyPropertyChanged
En el ejemplo de código siguiente se muestra cómo implementar la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Implemente esta interfaz en objetos comerciales que se usan en Windows Forms enlace de datos. Cuando se implementa, la interfaz se comunica con un control enlazado que la propiedad cambia en un objeto comercial.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para aplicar el patrón PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
- [Procedimiento para provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
