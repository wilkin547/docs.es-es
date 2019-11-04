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
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458857"
---
# <a name="how-to-convert-bound-data"></a>Cómo: Convertir datos enlazados
En este ejemplo se muestra cómo aplicar la conversión a los datos que se utilizan en los enlaces.  
  
 Para convertir los datos durante el enlace, debe crear una clase que implemente la interfaz <xref:System.Windows.Data.IValueConverter>, que incluye los métodos <xref:System.Windows.Data.IValueConverter.Convert%2A> y <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la implementación de un convertidor de fechas que convierte el valor de fecha pasado para que solo muestre el año, el mes y el día. Al implementar la interfaz <xref:System.Windows.Data.IValueConverter>, se recomienda decorar la implementación con un atributo <xref:System.Windows.Data.ValueConversionAttribute> para indicar a las herramientas de desarrollo los tipos de datos implicados en la conversión, como en el ejemplo siguiente:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Una vez que haya creado un convertidor, puede agregarlo como un recurso en el archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. En el ejemplo siguiente, *src* se asigna al espacio de nombres en el que se define *DateConverter* .  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Por último, puede usar el convertidor en el enlace con la siguiente sintaxis. En el ejemplo siguiente, el contenido de texto del <xref:System.Windows.Controls.TextBlock> se enlaza a *startDate*, que es una propiedad de un origen de datos externo.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Los recursos de estilo a los que se hace referencia en el ejemplo anterior se definen en una sección de recursos que no se muestra en este tema.  
  
## <a name="see-also"></a>Vea también

- [Implementar la validación de enlaces](how-to-implement-binding-validation.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
