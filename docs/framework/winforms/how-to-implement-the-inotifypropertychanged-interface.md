---
title: Procedimiento Implementar la interfaz INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: c92406899cffa56a1001f50f89cb53303df5da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560079"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="12042-102">Procedimiento Implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="12042-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="12042-103">En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="12042-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="12042-104">Implemente esta interfaz en objetos de negocios que se usan en el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="12042-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="12042-105">Cuando se implementa, la interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="12042-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12042-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12042-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="12042-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="12042-107">See also</span></span>
- [<span data-ttu-id="12042-108">Cómo: Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="12042-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="12042-109">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12042-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="12042-110">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="12042-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="12042-111">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12042-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
