---
title: Procedimiento Implementar lógica de validación en objetos personalizados
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
ms.openlocfilehash: e183d286e4b9cd037c352126203b1ecdcca89ebb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365365"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Filtrar Implementar lógica de validación en objetos personalizados
En este ejemplo se muestra cómo implementar la lógica de validación en un objeto personalizado y, a continuación, enlazar a él.  
  
## <a name="example"></a>Ejemplo  
 Puede proporcionar lógica de validación en la capa de negocio si implementa el objeto de origen <xref:System.ComponentModel.IDataErrorInfo>, como en el ejemplo siguiente, que define un `Person` objeto que implementa <xref:System.ComponentModel.IDataErrorInfo>:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 En el ejemplo siguiente, se enlaza la propiedad text del cuadro de texto a la `Person.Age` propiedad, que se ha puesto a disposición para el enlace a través de una declaración de recursos que se da el `x:Key` `data`. El <xref:System.Windows.Controls.DataErrorValidationRule> comprueba los errores de validación provocados por la <xref:System.ComponentModel.IDataErrorInfo> implementación.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 Como alternativa, en lugar de usar el <xref:System.Windows.Controls.DataErrorValidationRule>, puede establecer el <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> propiedad `true`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [Implementar la validación de enlaces](how-to-implement-binding-validation.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
