---
title: "Cómo: Aplicar el modelo PropertyNameChanged"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe397a92ac6e79e84757baa0c41f6e0c54b7f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="c8ded-102">Cómo: Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="c8ded-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="c8ded-103">En el ejemplo de código siguiente se muestra cómo aplicar el *PropertyName*modelo Changed a un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8ded-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="c8ded-104">Este patrón se aplican al implementar controles personalizados que se usan con el motor de enlace de datos de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c8ded-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ded-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8ded-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8ded-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c8ded-106">Compiling the Code</span></span>  
 <span data-ttu-id="c8ded-107">Para compilar el ejemplo de código anterior:</span><span class="sxs-lookup"><span data-stu-id="c8ded-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="c8ded-108">Pegue el código en un archivo de código vacío.</span><span class="sxs-lookup"><span data-stu-id="c8ded-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="c8ded-109">Debe utilizar el control personalizado en un formulario Windows Forms que contiene un `Main` método.</span><span class="sxs-lookup"><span data-stu-id="c8ded-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ded-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8ded-110">See Also</span></span>  
 [<span data-ttu-id="c8ded-111">Implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="c8ded-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="c8ded-112">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ded-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="c8ded-113">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ded-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
