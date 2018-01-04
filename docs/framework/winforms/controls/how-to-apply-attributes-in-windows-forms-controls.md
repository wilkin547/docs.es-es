---
title: "Cómo: Aplicar atributos en controles de formularios Windows Forms"
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
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e4d5bfb445ce6ed37ad1dc63d92fde833ac9870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="4eee2-102">Cómo: Aplicar atributos en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4eee2-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="4eee2-103">Para desarrollar componentes y controles que interactúan correctamente con el entorno de diseño y se ejecuten correctamente en tiempo de ejecución, debe aplicar correctamente los atributos a las clases y miembros.</span><span class="sxs-lookup"><span data-stu-id="4eee2-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eee2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4eee2-104">Example</span></span>  
 <span data-ttu-id="4eee2-105">En el ejemplo de código siguiente se muestra cómo usar varios atributos en un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="4eee2-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="4eee2-106">El control muestra una función de registro simple.</span><span class="sxs-lookup"><span data-stu-id="4eee2-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="4eee2-107">Cuando el control se enlaza a un origen de datos, muestra los valores enviados por el origen de datos en un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4eee2-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4eee2-108">Si un valor supera el valor especificado por el `Threshold` propiedad, un `ThresholdExceeded` evento se desencadena.</span><span class="sxs-lookup"><span data-stu-id="4eee2-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="4eee2-109">El `AttributesDemoControl` registra los valores con un `LogEntry` clase.</span><span class="sxs-lookup"><span data-stu-id="4eee2-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="4eee2-110">La `LogEntry` clase es una clase de plantilla, lo que significa que se parametriza en el tipo que registra.</span><span class="sxs-lookup"><span data-stu-id="4eee2-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="4eee2-111">Por ejemplo, si la `AttributesDemoControl` representa valores de registro del tipo `float`, cada `LogEntry` instancia se declara y se utiliza como sigue.</span><span class="sxs-lookup"><span data-stu-id="4eee2-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="4eee2-112">Dado que `LogEntry` se parametriza por un tipo arbitrario, debe usar la reflexión para operar en el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="4eee2-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="4eee2-113">Para la característica de umbral para que funcione, el tipo de parámetro `T` debe implementar la <xref:System.IComparable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="4eee2-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="4eee2-114">El formulario que hospeda el `AttributesDemoControl` consulta periódicamente un contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4eee2-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="4eee2-115">Cada valor se empaqueta en un `LogEntry` del tipo adecuado y se agrega al formulario <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="4eee2-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="4eee2-116">El `AttributesDemoControl` recibe el valor a través de su enlace de datos y muestra el valor en un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4eee2-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="4eee2-117">El primer ejemplo de código es el `AttributesDemoControl` implementación.</span><span class="sxs-lookup"><span data-stu-id="4eee2-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="4eee2-118">El segundo ejemplo de código muestra un formulario que utiliza el `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="4eee2-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="4eee2-119">Atributos de nivel de clase</span><span class="sxs-lookup"><span data-stu-id="4eee2-119">Class-level Attributes</span></span>  
 <span data-ttu-id="4eee2-120">Algunos atributos se aplican en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="4eee2-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="4eee2-121">En el ejemplo de código siguiente se muestra los atributos que normalmente se aplican a un control de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4eee2-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="4eee2-122">Atributo TypeConverter</span><span class="sxs-lookup"><span data-stu-id="4eee2-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="4eee2-123"><xref:System.ComponentModel.TypeConverterAttribute>es otro atributo de nivel de clase de uso frecuente.</span><span class="sxs-lookup"><span data-stu-id="4eee2-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="4eee2-124">En el ejemplo de código siguiente se muestra su uso para la `LogEntry` clase.</span><span class="sxs-lookup"><span data-stu-id="4eee2-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="4eee2-125">En este ejemplo también muestra una implementación de un <xref:System.ComponentModel.TypeConverter> para el `LogEntry` tipo, denominado `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="4eee2-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="4eee2-126">Atributos de nivel de miembro</span><span class="sxs-lookup"><span data-stu-id="4eee2-126">Member-level Attributes</span></span>  
 <span data-ttu-id="4eee2-127">Algunos atributos se aplican en el nivel de miembro.</span><span class="sxs-lookup"><span data-stu-id="4eee2-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="4eee2-128">Los ejemplos de código siguientes muestran algunos atributos que normalmente se aplican a las propiedades de controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4eee2-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="4eee2-129">Atributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="4eee2-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="4eee2-130">En el ejemplo siguiente se muestra la <xref:System.ComponentModel.AmbientValueAttribute> y muestra código que admite su interacción con el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="4eee2-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="4eee2-131">Se llama a esta interacción *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="4eee2-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="4eee2-132">Atributos de enlace de datos</span><span class="sxs-lookup"><span data-stu-id="4eee2-132">Databinding Attributes</span></span>  
 <span data-ttu-id="4eee2-133">Los ejemplos siguientes muestran una implementación de enlace de datos complejo.</span><span class="sxs-lookup"><span data-stu-id="4eee2-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="4eee2-134">El nivel de clase <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, como se muestra anteriormente, especifica la `DataSource` y `DataMember` propiedades que se usará para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="4eee2-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="4eee2-135">El <xref:System.ComponentModel.AttributeProviderAttribute> especifica el tipo al que el `DataSource` se enlazará la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4eee2-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4eee2-136">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4eee2-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="4eee2-137">El formulario que hospeda el `AttributesDemoControl` requiere una referencia a la `AttributesDemoControl` ensamblado con el fin de crear.</span><span class="sxs-lookup"><span data-stu-id="4eee2-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eee2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eee2-138">See Also</span></span>  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="4eee2-139">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4eee2-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="4eee2-140">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4eee2-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="4eee2-141">Cómo: serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="4eee2-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
