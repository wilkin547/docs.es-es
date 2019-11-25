---
title: 'Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: cf2ddc93a7c46ee6956d2731a786289f64086360
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976420"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada
En este ejemplo se muestra cómo obtener el objeto de enlace desde una propiedad de destino enlazada a datos.

## <a name="example"></a>Ejemplo
 Puede hacer lo siguiente para obtener el objeto de <xref:System.Windows.Data.Binding>:

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> Debe especificar la propiedad de dependencia para el enlace que desee porque es posible que más de una propiedad del objeto de destino esté usando el enlace de datos.

 Como alternativa, puede obtener el <xref:System.Windows.Data.BindingExpression> y, a continuación, obtener el valor de la propiedad <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.

 Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](https://go.microsoft.com/fwlink/?LinkID=159972).

> [!NOTE]
> Si el enlace es un <xref:System.Windows.Data.MultiBinding>, utilice <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>. Si es un <xref:System.Windows.Data.PriorityBinding>, utilice <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>. Si no está seguro de si la propiedad de destino está enlazada mediante un <xref:System.Windows.Data.Binding>, un <xref:System.Windows.Data.MultiBinding>o un <xref:System.Windows.Data.PriorityBinding>, puede utilizar <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- [Crear un enlace mediante código](how-to-create-a-binding-in-code.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
