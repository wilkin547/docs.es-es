---
title: Procedimiento Enlazar a un método
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: afa7801709d733ed40389f240fa5d92a2557c7a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732081"
---
# <a name="how-to-bind-to-a-method"></a>Procedimiento Enlazar a un método
El ejemplo siguiente muestra cómo enlazar a un método mediante <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `TemperatureScale` es una clase que tiene un método `ConvertTemp`, que toma dos parámetros (uno de tipo `double` y uno de tipo `enum``TempType)`, y convierte el valor dado de una escala de temperatura a otra. En el ejemplo siguiente, un <xref:System.Windows.Data.ObjectDataProvider> se usa para crear una instancia de la `TemperatureScale` objeto. Se llama al método `ConvertTemp` con dos parámetros especificados.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ahora que el método está disponible como un recurso, puede enlazar a los resultados. En el ejemplo siguiente, la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de la <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> de la <xref:System.Windows.Controls.ComboBox> están enlazados a los dos parámetros del método. Esto permite al usuario especificar la temperatura que se desea convertir y la escala de temperatura desde la que realizar la conversión. Tenga en cuenta que <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> está establecido en `true` porque estamos enlazando a la <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> propiedad de la <xref:System.Windows.Data.ObjectDataProvider> instancia y no las propiedades del objeto ajustado por el <xref:System.Windows.Data.ObjectDataProvider> (el `TemperatureScale` objeto).  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> del último <xref:System.Windows.Controls.Label> actualiza cuando el usuario modifica el contenido de la <xref:System.Windows.Controls.TextBox> o la selección de la <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 El convertidor `DoubleToString` toma un double y lo convierte en una cadena en el <xref:System.Windows.Data.IValueConverter.Convert%2A> dirección (de origen de enlace al destino de enlace, que es el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad) y convierte un `string` a un `double` en el <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> dirección.  
  
 El `InvalidationCharacterRule` es un <xref:System.Windows.Controls.ValidationRule> que comprueba si hay caracteres no válidos. La plantilla de error predeterminada, que es un borde rojo alrededor del <xref:System.Windows.Controls.TextBox>, aparece para notificar a los usuarios cuando el valor de entrada no es un valor double.  
  
## <a name="see-also"></a>Vea también
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
- [Enlazar a una enumeración](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
