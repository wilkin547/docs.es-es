---
title: "Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados"
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
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2573f342530e59fa05e7f24342f251990b2ce47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="acdf0-102">Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados</span><span class="sxs-lookup"><span data-stu-id="acdf0-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="acdf0-103">A menudo, cuando se trabaja con enlace de datos en formularios Windows Forms, varios controles están enlazados al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acdf0-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="acdf0-104">En algunos casos, puede ser necesario realizar pasos adicionales para asegurarse de que las propiedades de los controles enlazadas sigan estando sincronizadas con entre sí y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acdf0-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="acdf0-105">Estos pasos son necesarios en dos situaciones:</span><span class="sxs-lookup"><span data-stu-id="acdf0-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="acdf0-106">Si el origen de datos no implementa <xref:System.ComponentModel.IBindingList>y, por tanto, generar <xref:System.ComponentModel.IBindingList.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="acdf0-107">Si el origen de datos implementa <xref:System.ComponentModel.IEditableObject>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="acdf0-108">En el primer caso, puede usar un <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos a los controles.</span><span class="sxs-lookup"><span data-stu-id="acdf0-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="acdf0-109">En este último caso, se utiliza un <xref:System.Windows.Forms.BindingSource> y controlar la <xref:System.Windows.Forms.BindingSource.BindingComplete> eventos y llame al método <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> en asociado <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acdf0-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acdf0-110">Example</span></span>  
 <span data-ttu-id="acdf0-111">En el ejemplo de código siguiente se muestra cómo enlazar tres controles: dos controles de cuadro de texto y un <xref:System.Windows.Forms.DataGridView> control: en la misma columna de un <xref:System.Data.DataSet> mediante un <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="acdf0-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="acdf0-112">Este ejemplo muestra cómo controlar la <xref:System.Windows.Forms.BindingSource.BindingComplete> eventos y asegúrese de que cuando se cambia el valor de texto de un cuadro de texto, el cuadro de texto adicionales y el <xref:System.Windows.Forms.DataGridView> control se actualizan con el valor correcto.</span><span class="sxs-lookup"><span data-stu-id="acdf0-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="acdf0-113">El ejemplo se usa un <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos y los controles.</span><span class="sxs-lookup"><span data-stu-id="acdf0-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="acdf0-114">Como alternativa, puede enlazar los controles directamente al origen de datos y recuperar el <xref:System.Windows.Forms.BindingManagerBase> para el enlace desde el formulario <xref:System.Windows.Forms.Control.BindingContext%2A> y, a continuación, controlar el <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> eventos para el <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="acdf0-115">Para obtener un ejemplo de cómo hacerlo, consulte la página de ayuda la <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> eventos de <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acdf0-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="acdf0-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="acdf0-117">Este ejemplo de código se necesita</span><span class="sxs-lookup"><span data-stu-id="acdf0-117">This code example requires</span></span>  
  
-   <span data-ttu-id="acdf0-118">Referencias a los ensamblados <xref:System>, <xref:System.Windows.Forms> y <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="acdf0-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="acdf0-119">Un formulario con el <xref:System.Windows.Forms.Form.Load> evento como controlado y una llamada a la `InitializeControlsAndDataSource` método en el ejemplo de la forma <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="acdf0-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acdf0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="acdf0-120">See Also</span></span>  
 [<span data-ttu-id="acdf0-121">Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="acdf0-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [<span data-ttu-id="acdf0-122">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="acdf0-122">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="acdf0-123">Interfaces relacionadas con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="acdf0-123">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [<span data-ttu-id="acdf0-124">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="acdf0-124">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
