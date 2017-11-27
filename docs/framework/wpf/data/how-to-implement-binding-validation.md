---
title: "Cómo: Implementar la validación de enlaces"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec860cc9cc58febd98d8642c98a50ec296592d02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="83f8f-102">Cómo: Implementar la validación de enlaces</span><span class="sxs-lookup"><span data-stu-id="83f8f-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="83f8f-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para proporcionar comentarios visuales para informar al usuario cuando se escribe un valor no válido, basado en una regla de validación personalizada.</span><span class="sxs-lookup"><span data-stu-id="83f8f-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83f8f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83f8f-104">Example</span></span>  
 <span data-ttu-id="83f8f-105">El texto del contenido de la <xref:System.Windows.Controls.TextBox> en el siguiente ejemplo se enlaza a la `Age` propiedad (de tipo int) de un objeto de origen de enlace denominado `ods`.</span><span class="sxs-lookup"><span data-stu-id="83f8f-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="83f8f-106">El enlace se configura para usar una regla de validación denominada `AgeRangeRule`, por lo que si el usuario especifica caracteres no numéricos o un valor inferior a 21 o superior a 130, aparece un signo de exclamación junto al cuadro de texto y aparece información sobre herramientas con el mensaje de error cuando el usuario coloca el mouse sobre el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="83f8f-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="83f8f-107">En el ejemplo siguiente se muestra la implementación de `AgeRangeRule`, que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método.</span><span class="sxs-lookup"><span data-stu-id="83f8f-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="83f8f-108">Se llama al método Int32.Parse() en el valor para asegurarse de que no contiene caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="83f8f-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="83f8f-109">El <xref:System.Windows.Controls.ValidationRule.Validate%2A> método devuelve un <xref:System.Windows.Controls.ValidationResult> que indica si el valor es válido en función de si se detecta una excepción durante el análisis y si el valor de vigencia está fuera de los límites inferior y superior.</span><span class="sxs-lookup"><span data-stu-id="83f8f-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="83f8f-110">En el ejemplo siguiente se muestra la opción de instalación <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` que crea un signo de admiración rojo para notificar al usuario de un error de validación.</span><span class="sxs-lookup"><span data-stu-id="83f8f-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="83f8f-111">Las plantillas de control se usan para redefinir la apariencia de un control.</span><span class="sxs-lookup"><span data-stu-id="83f8f-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="83f8f-112">Como se muestra en el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error se crea utilizando el estilo denominado `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="83f8f-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="83f8f-113">Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true`, el desencadenador establece la información sobre herramientas del elemento actual <xref:System.Windows.Controls.TextBox> a su primer error de validación.</span><span class="sxs-lookup"><span data-stu-id="83f8f-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="83f8f-114">El <xref:System.Windows.Data.Binding.RelativeSource%2A> se establece en <xref:System.Windows.Data.RelativeSourceMode.Self>, que hace referencia al elemento actual.</span><span class="sxs-lookup"><span data-stu-id="83f8f-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="83f8f-115">Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="83f8f-115">For the complete example, see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="83f8f-116">Tenga en cuenta que si no proporciona un personalizado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> la plantilla de error predeterminada aparece proporcionar información visual al usuario cuando se produce un error de validación.</span><span class="sxs-lookup"><span data-stu-id="83f8f-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="83f8f-117">Vea "Validación de datos" en [Información sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="83f8f-117">See "Data Validation" in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="83f8f-118">Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación incorporada que selecciona las excepciones que se producen durante la actualización de la propiedad del origen de enlace.</span><span class="sxs-lookup"><span data-stu-id="83f8f-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="83f8f-119">Para obtener más información, consulta <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="83f8f-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f8f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="83f8f-120">See Also</span></span>  
 [<span data-ttu-id="83f8f-121">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="83f8f-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="83f8f-122">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="83f8f-122">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
