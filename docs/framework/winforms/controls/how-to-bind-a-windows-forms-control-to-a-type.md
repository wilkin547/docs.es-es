---
title: Enlazar el control a un tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 0bc1f92ee8922990bd0e461655168f5618ba39a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744990"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="25d2a-102">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="25d2a-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="25d2a-103">Al crear controles que interactúan con datos, a veces necesitará enlazar un control a un tipo en lugar de a un objeto.</span><span class="sxs-lookup"><span data-stu-id="25d2a-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="25d2a-104">Estas situaciones se producen especialmente en tiempo de diseño, cuando puede que los datos no estén disponibles pero los controles enlazados a datos necesitan mostrar la información de una interfaz pública del tipo.</span><span class="sxs-lookup"><span data-stu-id="25d2a-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="25d2a-105">Por ejemplo, puede enlazar un control <xref:System.Windows.Forms.DataGridView> a un objeto expuesto por un servicio Web y quiere que el control <xref:System.Windows.Forms.DataGridView> etiquete sus columnas en tiempo de diseño con los nombres de miembro de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="25d2a-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="25d2a-106">Puede enlazar fácilmente un control a un tipo con el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="25d2a-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25d2a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d2a-107">Example</span></span>  
 <span data-ttu-id="25d2a-108">En el ejemplo de código siguiente se muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un tipo personalizado mediante un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="25d2a-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="25d2a-109">Al ejecutar el ejemplo, observará que <xref:System.Windows.Forms.DataGridView> ha etiquetado las columnas que reflejan las propiedades de un objeto `Customer` antes de que el control se rellene con datos.</span><span class="sxs-lookup"><span data-stu-id="25d2a-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="25d2a-110">El ejemplo tiene un botón Add Customer para agregar datos al control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="25d2a-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="25d2a-111">Al hacer clic en el botón, se agrega un nuevo objeto `Customer` al <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="25d2a-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="25d2a-112">En un escenario real, los datos se pueden obtener mediante una llamada a un servicio Web o a otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25d2a-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="25d2a-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="25d2a-113">Compiling the Code</span></span>  
 <span data-ttu-id="25d2a-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="25d2a-114">This example requires:</span></span>  
  
- <span data-ttu-id="25d2a-115">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="25d2a-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d2a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="25d2a-116">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="25d2a-117">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="25d2a-117">BindingSource Component</span></span>](bindingsource-component.md)
