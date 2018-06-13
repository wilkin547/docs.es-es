---
title: 'Cómo: Implementar la interfaz ITypedList'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 181879d3e41e0dd140c79a4c63d52e6999acf86d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538075"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="772dc-102">Cómo: Implementar la interfaz ITypedList</span><span class="sxs-lookup"><span data-stu-id="772dc-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="772dc-103">Implemente el <xref:System.ComponentModel.ITypedList> interfaz para habilitar la detección del esquema para obtener una lista enlazable.</span><span class="sxs-lookup"><span data-stu-id="772dc-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="772dc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="772dc-104">Example</span></span>  
 <span data-ttu-id="772dc-105">En el ejemplo de código siguiente se muestra cómo implementar el <xref:System.ComponentModel.ITypedList> interfaz.</span><span class="sxs-lookup"><span data-stu-id="772dc-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="772dc-106">Un tipo genérico denominado `SortableBindingList` se deriva de la <xref:System.ComponentModel.BindingList%601> clase e implementa el <xref:System.ComponentModel.ITypedList> interfaz.</span><span class="sxs-lookup"><span data-stu-id="772dc-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="772dc-107">Una clase simple denominada `Customer` proporciona los datos, que está enlazados al encabezado de una <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="772dc-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="772dc-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="772dc-108">Compiling the Code</span></span>  
 <span data-ttu-id="772dc-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="772dc-109">This example requires:</span></span>  
  
-   <span data-ttu-id="772dc-110">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="772dc-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772dc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="772dc-111">See Also</span></span>  
 <xref:System.ComponentModel.ITypedList>  
 <xref:System.ComponentModel.BindingList%601>  
 <xref:System.ComponentModel.IBindingList>  
 [<span data-ttu-id="772dc-112">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772dc-112">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
