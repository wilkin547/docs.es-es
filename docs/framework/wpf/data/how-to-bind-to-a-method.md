---
title: 'Cómo: Enlazar a un método'
description: Siga este ejemplo para averiguar cómo enlazar con el método de un objeto en el Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619603"
---
# <a name="how-to-bind-to-a-method"></a>Cómo: Enlazar a un método
En el ejemplo siguiente se muestra cómo enlazar a un método mediante <xref:System.Windows.Data.ObjectDataProvider> .  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `TemperatureScale` es una clase que tiene un método `ConvertTemp`, que toma dos parámetros (uno de tipo `double` y uno de tipo `enum``TempType)`, y convierte el valor dado de una escala de temperatura a otra. En el ejemplo siguiente, <xref:System.Windows.Data.ObjectDataProvider> se usa para crear una instancia del `TemperatureScale` objeto. Se llama al método `ConvertTemp` con dos parámetros especificados.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ahora que el método está disponible como un recurso, puede enlazar a los resultados. En el ejemplo siguiente, la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox> y del <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ComboBox> se enlazan a los dos parámetros del método. Esto permite al usuario especificar la temperatura que se desea convertir y la escala de temperatura desde la que realizar la conversión. Tenga en cuenta que <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> se establece en `true` porque estamos enlazando a la <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> propiedad de la <xref:System.Windows.Data.ObjectDataProvider> instancia de y no a las propiedades del objeto encapsulado por <xref:System.Windows.Data.ObjectDataProvider> (el `TemperatureScale` objeto).  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> de la última <xref:System.Windows.Controls.Label> actualización cuando el usuario modifica el contenido del <xref:System.Windows.Controls.TextBox> o la selección de <xref:System.Windows.Controls.ComboBox> .  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 El convertidor `DoubleToString` toma un valor Double y lo convierte en una cadena en la <xref:System.Windows.Data.IValueConverter.Convert%2A> dirección (desde el origen de enlace hasta el destino de enlace, que es la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad) y convierte un en `string` `double` en la <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> dirección.  
  
 `InvalidationCharacterRule`Es un <xref:System.Windows.Controls.ValidationRule> que comprueba si hay caracteres no válidos. La plantilla de error predeterminada, que es un borde rojo alrededor de <xref:System.Windows.Controls.TextBox> , parece notificar a los usuarios cuando el valor de entrada no es un valor doble.  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](data-binding-how-to-topics.md)
- [Enlazar a una enumeración](how-to-bind-to-an-enumeration.md)
