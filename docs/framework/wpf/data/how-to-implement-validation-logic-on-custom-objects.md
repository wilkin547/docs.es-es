---
title: 'Cómo: Implementar lógica de validación en objetos personalizados'
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "33555969"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="8b984-102">Cómo: Implementar lógica de validación en objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="8b984-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="8b984-103">En este ejemplo se muestra cómo implementar la lógica de validación en un objeto personalizado y, a continuación, enlazar a él.</span><span class="sxs-lookup"><span data-stu-id="8b984-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b984-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b984-104">Example</span></span>  
 <span data-ttu-id="8b984-105">Puede proporcionar lógica de validación en la capa de negocio si implementa el objeto de origen <xref:System.ComponentModel.IDataErrorInfo>, como en el ejemplo siguiente, que define un `Person` objeto que implementa <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="8b984-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="8b984-106">En el ejemplo siguiente, se enlaza la propiedad text del cuadro de texto a la `Person.Age` propiedad, que se ha puesto a disposición para el enlace a través de una declaración de recursos que se da el `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="8b984-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="8b984-107">El <xref:System.Windows.Controls.DataErrorValidationRule> comprueba los errores de validación provocados por la <xref:System.ComponentModel.IDataErrorInfo> implementación.</span><span class="sxs-lookup"><span data-stu-id="8b984-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="8b984-108">Como alternativa, en lugar de usar el <xref:System.Windows.Controls.DataErrorValidationRule>, puede establecer el <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="8b984-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b984-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b984-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="8b984-110">Implementar la validación de enlaces</span><span class="sxs-lookup"><span data-stu-id="8b984-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="8b984-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="8b984-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
