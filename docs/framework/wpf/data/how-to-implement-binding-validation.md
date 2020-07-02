---
title: 'Cómo: Implementar la validación de enlaces'
description: Obtenga información sobre cómo usar la validación de enlace para proporcionar información visual al usuario cuando se escribe un valor no válido en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 0813be9f79a83a9dae26db1dadb58b5e973339fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617887"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="f89fd-103">Cómo: Implementar la validación de enlaces</span><span class="sxs-lookup"><span data-stu-id="f89fd-103">How to: Implement Binding Validation</span></span>

<span data-ttu-id="f89fd-104">En este ejemplo se muestra cómo usar un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para proporcionar comentarios visuales para informar al usuario cuando se escribe un valor no válido, en función de una regla de validación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f89fd-104">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="f89fd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f89fd-105">Example</span></span>

<span data-ttu-id="f89fd-106">El contenido de texto de <xref:System.Windows.Controls.TextBox> en el ejemplo siguiente se enlaza a la `Age` propiedad (de tipo int) de un objeto de origen de enlace denominado `ods` .</span><span class="sxs-lookup"><span data-stu-id="f89fd-106">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="f89fd-107">El enlace se configura para usar una regla de validación denominada `AgeRangeRule`, por lo que si el usuario especifica caracteres no numéricos o un valor inferior a 21 o superior a 130, aparece un signo de exclamación junto al cuadro de texto y aparece información sobre herramientas con el mensaje de error cuando el usuario coloca el mouse sobre el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f89fd-107">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="f89fd-108">En el ejemplo siguiente se muestra la implementación de `AgeRangeRule` , que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f89fd-108">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="f89fd-109">`Int32.Parse`Se llama al método en el valor para asegurarse de que no contiene ningún carácter no válido.</span><span class="sxs-lookup"><span data-stu-id="f89fd-109">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="f89fd-110">El <xref:System.Windows.Controls.ValidationRule.Validate%2A> método devuelve un <xref:System.Windows.Controls.ValidationResult> valor de que indica si el valor es válido en función de si se detecta una excepción durante el análisis y si el valor de edad está fuera de los límites inferior y superior.</span><span class="sxs-lookup"><span data-stu-id="f89fd-110">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="f89fd-111">En el ejemplo siguiente se muestra el personalizado <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` que crea un signo de exclamación rojo para notificar al usuario de un error de validación.</span><span class="sxs-lookup"><span data-stu-id="f89fd-111">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="f89fd-112">Las plantillas de control se usan para redefinir la apariencia de un control.</span><span class="sxs-lookup"><span data-stu-id="f89fd-112">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="f89fd-113">Como se muestra en el ejemplo siguiente, el <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error se crea utilizando el estilo denominado `textBoxInError` .</span><span class="sxs-lookup"><span data-stu-id="f89fd-113">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="f89fd-114">Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true` , el desencadenador establece la información sobre herramientas del actual <xref:System.Windows.Controls.TextBox> en su primer error de validación.</span><span class="sxs-lookup"><span data-stu-id="f89fd-114">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="f89fd-115"><xref:System.Windows.Data.Binding.RelativeSource%2A>Se establece en <xref:System.Windows.Data.RelativeSourceMode.Self> , haciendo referencia al elemento actual.</span><span class="sxs-lookup"><span data-stu-id="f89fd-115">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="f89fd-116">Para obtener el ejemplo completo, vea [ejemplo de validación de enlace](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="f89fd-116">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="f89fd-117">Tenga en cuenta que si no proporciona un personalizado, <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> aparece la plantilla de error predeterminada para proporcionar información visual al usuario cuando se produce un error de validación.</span><span class="sxs-lookup"><span data-stu-id="f89fd-117">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="f89fd-118">Vea "Validación de datos" en [Información sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f89fd-118">See "Data Validation" in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="f89fd-119">Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación incorporada que selecciona las excepciones que se producen durante la actualización de la propiedad del origen de enlace.</span><span class="sxs-lookup"><span data-stu-id="f89fd-119">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="f89fd-120">Para obtener más información, vea <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="f89fd-120">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f89fd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f89fd-121">See also</span></span>

- [<span data-ttu-id="f89fd-122">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f89fd-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="f89fd-123">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f89fd-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
