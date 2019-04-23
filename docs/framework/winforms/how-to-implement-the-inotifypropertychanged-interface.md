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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225604"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="94923-102">Procedimiento para implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="94923-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="94923-103">En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="94923-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="94923-104">Implemente esta interfaz en objetos de negocios que se usan en el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94923-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="94923-105">Cuando se implementa, la interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="94923-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94923-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94923-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="94923-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="94923-107">See also</span></span>

- [<span data-ttu-id="94923-108">Cómo: Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="94923-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="94923-109">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94923-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="94923-110">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="94923-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="94923-111">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94923-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
