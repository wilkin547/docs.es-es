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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="cddda-103">Procedimiento para implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="cddda-103">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="cddda-104">En el ejemplo de código siguiente se muestra cómo implementar la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="cddda-104">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="cddda-105">Implemente esta interfaz en objetos comerciales que se usan en Windows Forms enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="cddda-105">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="cddda-106">Cuando se implementa, la interfaz se comunica con un control enlazado que la propiedad cambia en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="cddda-106">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cddda-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cddda-107">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cddda-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="cddda-108">See also</span></span>

- [<span data-ttu-id="cddda-109">Procedimiento para aplicar el patrón PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="cddda-109">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="cddda-110">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cddda-110">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="cddda-111">Procedimiento para provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="cddda-111">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="cddda-112">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cddda-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
