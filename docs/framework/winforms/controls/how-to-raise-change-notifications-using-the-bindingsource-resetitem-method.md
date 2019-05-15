---
title: Procedimiento para provocar notificaciones de cambios mediante el método ResetItem de BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 39beb5c7162fb01a51360330216687c158ff433c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583714"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="8e687-102">Procedimiento para provocar notificaciones de cambios mediante el método ResetItem de BindingSource</span><span class="sxs-lookup"><span data-stu-id="8e687-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="8e687-103">Algunos orígenes de datos para sus controles no provocan notificaciones de cambios cuando se cambian, agregan o eliminan elementos.</span><span class="sxs-lookup"><span data-stu-id="8e687-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="8e687-104">Con el componente <xref:System.Windows.Forms.BindingSource>, puede enlazar a tales orígenes de datos y provocar una notificación de cambios desde el código.</span><span class="sxs-lookup"><span data-stu-id="8e687-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e687-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e687-105">Example</span></span>  
 <span data-ttu-id="8e687-106">Este formulario muestra cómo utilizar un componente <xref:System.Windows.Forms.BindingSource> para enlazar una lista a un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="8e687-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8e687-107">La lista no provoca notificaciones de cambios, por lo que se llama al método <xref:System.Windows.Forms.BindingSource.ResetItem%2A> en <xref:System.Windows.Forms.BindingSource> cuando se cambia un elemento en la lista.</span><span class="sxs-lookup"><span data-stu-id="8e687-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="8e687-108">.</span><span class="sxs-lookup"><span data-stu-id="8e687-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e687-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8e687-109">Compiling the Code</span></span>  
 <span data-ttu-id="8e687-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8e687-110">This example requires:</span></span>  
  
- <span data-ttu-id="8e687-111">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8e687-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e687-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e687-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="8e687-113">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="8e687-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="8e687-114">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="8e687-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
