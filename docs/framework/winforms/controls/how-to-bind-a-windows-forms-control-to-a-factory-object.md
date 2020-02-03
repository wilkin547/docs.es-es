---
title: Enlazar el control a un objeto de generador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2b4d9aca3345a0cb1e7e995f66a8982dee983ca8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745096"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="d7ba4-102">Cómo: Enlazar un control de Windows Forms a un objeto Factory</span><span class="sxs-lookup"><span data-stu-id="d7ba4-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="d7ba4-103">Al crear controles que interactúan con datos, a veces considerará necesario enlazar un control a un objeto o un método que genere otros objetos.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="d7ba4-104">Este tipo de objetos o métodos se denomina generador.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="d7ba4-105">El origen de datos podría ser, por ejemplo, el valor devuelto de una llamada al método, en lugar de un objeto en la memoria o un tipo.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="d7ba4-106">Puede enlazar un control a este tipo de origen de datos mientras el origen devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="d7ba4-107">Puede enlazar fácilmente un control a un objeto de generador utilizando el control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7ba4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7ba4-108">Example</span></span>  
 <span data-ttu-id="d7ba4-109">El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un método de generador mediante el uso de un control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="d7ba4-110">El método de generador se denomina `GetOrdersByCustomerId` y devuelve todos los pedidos de un cliente determinado en la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7ba4-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d7ba4-111">Compiling the Code</span></span>  
 <span data-ttu-id="d7ba4-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d7ba4-112">This example requires:</span></span>  
  
- <span data-ttu-id="d7ba4-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d7ba4-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ba4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7ba4-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d7ba4-115">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="d7ba4-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d7ba4-116">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="d7ba4-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
