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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="2aadf-102">Procedimiento para implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="2aadf-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="2aadf-103">En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="2aadf-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="2aadf-104">Implemente esta interfaz en objetos de negocios que se usan en el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2aadf-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="2aadf-105">Cuando se implementa, la interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="2aadf-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aadf-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2aadf-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2aadf-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aadf-107">See also</span></span>

- [<span data-ttu-id="2aadf-108">Cómo: Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="2aadf-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="2aadf-109">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aadf-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="2aadf-110">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="2aadf-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="2aadf-111">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2aadf-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
