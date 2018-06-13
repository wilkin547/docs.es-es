---
title: 'Cómo: Convertir datos enlazados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 526305f32280fb75e95538b9014c34c11ed8bffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556645"
---
# <a name="how-to-convert-bound-data"></a>Cómo: Convertir datos enlazados
En este ejemplo se muestra cómo aplicar la conversión a datos que se utilizan en enlaces.  
  
 Para convertir datos durante el enlace, debe crear una clase que implementa el <xref:System.Windows.Data.IValueConverter> interfaz, que incluye el <xref:System.Windows.Data.IValueConverter.Convert%2A> y <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> métodos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la implementación de un convertidor de fecha que convierte el valor de fecha pasado de manera que solo muestra el año, mes y día. Al implementar el <xref:System.Windows.Data.IValueConverter> interfaz, es una buena práctica para decorar la implementación con un <xref:System.Windows.Data.ValueConversionAttribute> atributo para indicar al desarrollo de herramientas de los tipos de datos implicados en la conversión, como en el ejemplo siguiente:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Una vez haya creado un convertidor, puede agregarlo como recurso en el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo. En el ejemplo siguiente, *src* se asigna al espacio de nombres en el que *DateConverter* está definido.  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Por último, puede usar el convertidor en el enlace mediante la sintaxis siguiente. En el ejemplo siguiente, el texto del contenido de la <xref:System.Windows.Controls.TextBlock> está enlazado a *StartDate*, que es una propiedad de un origen de datos externo.  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Los recursos de estilo que se hace referencia en el ejemplo anterior se definen en una sección de recursos que no se muestra en este tema.  
  
## <a name="see-also"></a>Vea también  
 [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
