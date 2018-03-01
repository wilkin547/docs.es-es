---
title: "Cómo: Implementar la interfaz INotifyPropertyChanged"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ded5d11c9a9f93848e17c372e961f9f6a3b4226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Cómo: Implementar la interfaz INotifyPropertyChanged
En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Implemente esta interfaz en los objetos de negocios que se utilizan en el enlace de datos de formularios Windows Forms. Cuando se implementa, la interfaz comunica con un control enlazado los cambios de propiedad en un objeto comercial.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Aplicar el modelo PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
