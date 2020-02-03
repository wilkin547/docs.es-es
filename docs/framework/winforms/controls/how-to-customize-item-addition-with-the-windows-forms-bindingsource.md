---
title: Personalización de la adición de elementos con el componente BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 7d74fe6b4bbb1ddb94b359f5ba3ae32ed398d1dd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738317"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="0ae97-102">Cómo: Personalizar la forma de agregar elementos con el control BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ae97-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="0ae97-103">Al usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar un control de Windows Forms a un origen de datos, quizá necesite personalizar la creación de nuevos elementos.</span><span class="sxs-lookup"><span data-stu-id="0ae97-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="0ae97-104">Para facilitar este proceso, el componente <xref:System.Windows.Forms.BindingSource> proporciona el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , que normalmente se produce cuando el control enlazado necesita crear un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="0ae97-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="0ae97-105">El controlador de eventos puede proporcionar el comportamiento personalizado necesario (por ejemplo, llamar a un método en un servicio Web u obtener un nuevo objeto de un generador de clases).</span><span class="sxs-lookup"><span data-stu-id="0ae97-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ae97-106">Cuando se agrega un elemento controlando el evento <xref:System.Windows.Forms.BindingSource.AddingNew> , no se puede cancelar la adición.</span><span class="sxs-lookup"><span data-stu-id="0ae97-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ae97-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ae97-107">Example</span></span>  
 <span data-ttu-id="0ae97-108">El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un generador de clases mediante un componente <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="0ae97-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="0ae97-109">Cuando el usuario hace clic en la nueva fila del control <xref:System.Windows.Forms.DataGridView> , se produce el evento <xref:System.Windows.Forms.BindingSource.AddingNew> .</span><span class="sxs-lookup"><span data-stu-id="0ae97-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="0ae97-110">El controlador de eventos crea un nuevo objeto `DemoCustomer` , que se asigna a la propiedad <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0ae97-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0ae97-111">Esto hace que el nuevo objeto se agregue `DemoCustomer` a la lista del componente <xref:System.Windows.Forms.BindingSource> y que se muestre en la nueva fila del control <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="0ae97-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ae97-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0ae97-112">Compiling the Code</span></span>  
 <span data-ttu-id="0ae97-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0ae97-113">This example requires:</span></span>  
  
- <span data-ttu-id="0ae97-114">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0ae97-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae97-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ae97-115">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="0ae97-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="0ae97-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="0ae97-117">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="0ae97-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
