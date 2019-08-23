---
title: Procedimiento para aplicar atributos en controles de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922784"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="38cce-102">Procedimiento para aplicar atributos en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38cce-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="38cce-103">Para desarrollar componentes y controles que interactúen correctamente con el entorno de diseño y se ejecuten correctamente en tiempo de ejecución, debe aplicar correctamente los atributos a las clases y miembros.</span><span class="sxs-lookup"><span data-stu-id="38cce-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38cce-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38cce-104">Example</span></span>  
 <span data-ttu-id="38cce-105">En el ejemplo de código siguiente se muestra cómo utilizar varios atributos en un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38cce-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="38cce-106">El control muestra una funcionalidad de registro simple.</span><span class="sxs-lookup"><span data-stu-id="38cce-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="38cce-107">Cuando el control está enlazado a un origen de datos, muestra los valores enviados por el origen de datos <xref:System.Windows.Forms.DataGridView> en un control.</span><span class="sxs-lookup"><span data-stu-id="38cce-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="38cce-108">Si un valor supera el valor especificado por la `Threshold` propiedad, se `ThresholdExceeded` genera un evento.</span><span class="sxs-lookup"><span data-stu-id="38cce-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="38cce-109">Registra los valores con una `LogEntry` clase. `AttributesDemoControl`</span><span class="sxs-lookup"><span data-stu-id="38cce-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="38cce-110">La `LogEntry` clase es una clase de plantilla, lo que significa que se parametriza en el tipo que registra.</span><span class="sxs-lookup"><span data-stu-id="38cce-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="38cce-111">Por ejemplo, si `AttributesDemoControl` está registrando valores de tipo `float`, cada `LogEntry` instancia se declara y se usa como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="38cce-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="38cce-112">Dado `LogEntry` que está parametrizado por un tipo arbitrario, debe usar la reflexión para operar en el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="38cce-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="38cce-113">Para que la característica de umbral funcione, el tipo `T` de parámetro debe <xref:System.IComparable> implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="38cce-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="38cce-114">El formulario que hospeda la `AttributesDemoControl` consulta periódicamente un contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="38cce-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="38cce-115">Cada valor se empaqueta en un `LogEntry` del tipo adecuado y se agrega a la del <xref:System.Windows.Forms.BindingSource>formulario.</span><span class="sxs-lookup"><span data-stu-id="38cce-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="38cce-116">Recibe el valor a través de su enlace de datos y muestra el valor <xref:System.Windows.Forms.DataGridView> en un control. `AttributesDemoControl`</span><span class="sxs-lookup"><span data-stu-id="38cce-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="38cce-117">El primer ejemplo de código es `AttributesDemoControl` la implementación de.</span><span class="sxs-lookup"><span data-stu-id="38cce-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="38cce-118">En el segundo ejemplo de código se muestra un formulario `AttributesDemoControl`que utiliza.</span><span class="sxs-lookup"><span data-stu-id="38cce-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="38cce-119">Atributos de nivel de clase</span><span class="sxs-lookup"><span data-stu-id="38cce-119">Class-level Attributes</span></span>  
 <span data-ttu-id="38cce-120">Algunos atributos se aplican en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="38cce-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="38cce-121">En el ejemplo de código siguiente se muestran los atributos que se suelen aplicar a un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="38cce-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="38cce-122">TypeConverter (atributo)</span><span class="sxs-lookup"><span data-stu-id="38cce-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="38cce-123"><xref:System.ComponentModel.TypeConverterAttribute>es otro atributo de nivel de clase de uso común.</span><span class="sxs-lookup"><span data-stu-id="38cce-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="38cce-124">En el ejemplo de código siguiente se muestra su `LogEntry` uso para la clase.</span><span class="sxs-lookup"><span data-stu-id="38cce-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="38cce-125"><xref:System.ComponentModel.TypeConverter> En este ejemplo también se muestra una implementación de para `LogEntry` el tipo, `LogEntryTypeConverter`denominado.</span><span class="sxs-lookup"><span data-stu-id="38cce-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="38cce-126">Atributos de nivel de miembro</span><span class="sxs-lookup"><span data-stu-id="38cce-126">Member-level Attributes</span></span>  
 <span data-ttu-id="38cce-127">Algunos atributos se aplican en el nivel de miembro.</span><span class="sxs-lookup"><span data-stu-id="38cce-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="38cce-128">En los siguientes ejemplos de código se muestran algunos atributos que se suelen aplicar a las propiedades de los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="38cce-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="38cce-129">Atributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="38cce-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="38cce-130">En el ejemplo siguiente se <xref:System.ComponentModel.AmbientValueAttribute> muestra y se muestra el código que admite su interacción con el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="38cce-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="38cce-131">Esta interacción se denomina *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="38cce-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="38cce-132">Atributos de DataBinding</span><span class="sxs-lookup"><span data-stu-id="38cce-132">Databinding Attributes</span></span>  
 <span data-ttu-id="38cce-133">En los siguientes ejemplos se muestra una implementación de enlace de datos complejo.</span><span class="sxs-lookup"><span data-stu-id="38cce-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="38cce-134">El nivel <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>de clase, que se mostró anteriormente, especifica `DataMember` las `DataSource` propiedades y que se van a usar para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="38cce-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="38cce-135">Especifica el tipo al que se enlazará la `DataSource` propiedad. <xref:System.ComponentModel.AttributeProviderAttribute></span><span class="sxs-lookup"><span data-stu-id="38cce-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38cce-136">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="38cce-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="38cce-137">El formulario que hospeda el `AttributesDemoControl` requiere una referencia `AttributesDemoControl` al ensamblado para poder compilar.</span><span class="sxs-lookup"><span data-stu-id="38cce-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cce-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="38cce-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="38cce-139">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="38cce-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="38cce-140">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38cce-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="38cce-141">[Cómo: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="38cce-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
