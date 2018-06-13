---
title: 'Cómo: Implementar la validación de enlaces'
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 347e38ba036e5c1a716a9edb75572c1a49f99631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556971"
---
# <a name="how-to-implement-binding-validation"></a>Cómo: Implementar la validación de enlaces
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para proporcionar comentarios visuales para informar al usuario cuando se escribe un valor no válido, basado en una regla de validación personalizada.  
  
## <a name="example"></a>Ejemplo  
 El texto del contenido de la <xref:System.Windows.Controls.TextBox> en el siguiente ejemplo se enlaza a la `Age` propiedad (de tipo int) de un objeto de origen de enlace denominado `ods`. El enlace se configura para usar una regla de validación denominada `AgeRangeRule`, por lo que si el usuario especifica caracteres no numéricos o un valor inferior a 21 o superior a 130, aparece un signo de exclamación junto al cuadro de texto y aparece información sobre herramientas con el mensaje de error cuando el usuario coloca el mouse sobre el cuadro de texto.  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 En el ejemplo siguiente se muestra la implementación de `AgeRangeRule`, que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método. Se llama al método Int32.Parse() en el valor para asegurarse de que no contiene caracteres no válidos. El <xref:System.Windows.Controls.ValidationRule.Validate%2A> método devuelve un <xref:System.Windows.Controls.ValidationResult> que indica si el valor es válido en función de si se detecta una excepción durante el análisis y si el valor de vigencia está fuera de los límites inferior y superior.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 En el ejemplo siguiente se muestra la opción de instalación <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` que crea un signo de admiración rojo para notificar al usuario de un error de validación. Las plantillas de control se usan para redefinir la apariencia de un control.  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Como se muestra en el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error se crea utilizando el estilo denominado `textBoxInError`. Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true`, el desencadenador establece la información sobre herramientas del elemento actual <xref:System.Windows.Controls.TextBox> a su primer error de validación. El <xref:System.Windows.Data.Binding.RelativeSource%2A> se establece en <xref:System.Windows.Data.RelativeSourceMode.Self>, que hace referencia al elemento actual.  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Tenga en cuenta que si no proporciona un personalizado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> la plantilla de error predeterminada aparece proporcionar información visual al usuario cuando se produce un error de validación. Vea "Validación de datos" en [Información sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md) para obtener más información. Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación incorporada que selecciona las excepciones que se producen durante la actualización de la propiedad del origen de enlace. Para obtener más información, consulta <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
