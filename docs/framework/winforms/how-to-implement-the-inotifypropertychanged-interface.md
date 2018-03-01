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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="88ca7-102">Cómo: Implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="88ca7-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="88ca7-103">En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="88ca7-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="88ca7-104">Implemente esta interfaz en los objetos de negocios que se utilizan en el enlace de datos de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88ca7-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="88ca7-105">Cuando se implementa, la interfaz comunica con un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="88ca7-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88ca7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88ca7-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="88ca7-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="88ca7-107">See Also</span></span>  
 [<span data-ttu-id="88ca7-108">Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="88ca7-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [<span data-ttu-id="88ca7-109">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88ca7-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="88ca7-110">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="88ca7-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [<span data-ttu-id="88ca7-111">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88ca7-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
