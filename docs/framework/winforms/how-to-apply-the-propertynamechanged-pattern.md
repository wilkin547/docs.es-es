---
title: Filtrar para aplicar el patrón PropertyNameChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 36670eee6235277a7fe98770192df9ae05d3dd03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213030"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="93b6b-102">Filtrar para aplicar el patrón PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="93b6b-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="93b6b-103">En el ejemplo de código siguiente se muestra cómo aplicar el *PropertyName*patrón ha cambiado a un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="93b6b-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="93b6b-104">Este patrón se aplican al implementar controles personalizados que se usan con el motor de enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="93b6b-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93b6b-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93b6b-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93b6b-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="93b6b-106">Compiling the Code</span></span>  
 <span data-ttu-id="93b6b-107">Para compilar el ejemplo de código anterior:</span><span class="sxs-lookup"><span data-stu-id="93b6b-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="93b6b-108">Pegue el código en un archivo de código vacío.</span><span class="sxs-lookup"><span data-stu-id="93b6b-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="93b6b-109">Debe usar el control personalizado en un formulario de Windows que contenga un `Main` método.</span><span class="sxs-lookup"><span data-stu-id="93b6b-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b6b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b6b-110">See also</span></span>

- [<span data-ttu-id="93b6b-111">Filtrar para implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="93b6b-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="93b6b-112">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93b6b-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="93b6b-113">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93b6b-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
