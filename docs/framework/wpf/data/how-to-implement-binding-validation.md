---
title: Filtrar Implementar la validación de enlaces
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 3950df8b6f4b48a035c6ebf37d8d65c18cb82e1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197222"
---
# <a name="how-to-implement-binding-validation"></a>Filtrar Implementar la validación de enlaces
En este ejemplo se muestra cómo usar un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para proporcionar comentarios visuales para informar al usuario cuando se escribe un valor no válido, según una regla de validación personalizada.  
  
## <a name="example"></a>Ejemplo  
 El contenido de texto el <xref:System.Windows.Controls.TextBox> en el ejemplo siguiente se enlaza a la `Age` propiedad (de tipo int) de un objeto de origen de enlace denominado `ods`. El enlace se configura para usar una regla de validación denominada `AgeRangeRule`, por lo que si el usuario especifica caracteres no numéricos o un valor inferior a 21 o superior a 130, aparece un signo de exclamación junto al cuadro de texto y aparece información sobre herramientas con el mensaje de error cuando el usuario coloca el mouse sobre el cuadro de texto.  
  
 [!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 El ejemplo siguiente muestra la implementación de `AgeRangeRule`, que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método. Se llama al método Int32.Parse() en el valor para asegurarse de que no contiene caracteres no válidos. El <xref:System.Windows.Controls.ValidationRule.Validate%2A> método devuelve un <xref:System.Windows.Controls.ValidationResult> que indica si el valor es válido según si se detecta una excepción durante el análisis y si el valor de edad está fuera de los límites superior e inferior.  
  
 [!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 El ejemplo siguiente muestra el personalizado <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` que crea un signo de exclamación rojo para avisar al usuario de un error de validación. Las plantillas de control se usan para redefinir la apariencia de un control.  
  
 [!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Como se muestra en el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error que se crea utilizando el estilo denominado `textBoxInError`. Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true`, el desencadenador establece la información sobre herramientas del elemento actual <xref:System.Windows.Controls.TextBox> a su primer error de validación. El <xref:System.Windows.Data.Binding.RelativeSource%2A> está establecido en <xref:System.Windows.Data.RelativeSourceMode.Self>, que hace referencia al elemento actual.  
  
 [!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Tenga en cuenta que si no proporcionas un personalizado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> aparece de la plantilla de error predeterminada proporcionar comentarios visuales al usuario cuando hay un error de validación. Vea "Validación de datos" en [Información sobre el enlace de datos](data-binding-overview.md) para obtener más información. Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación incorporada que selecciona las excepciones que se producen durante la actualización de la propiedad del origen de enlace. Para obtener más información, consulta <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
