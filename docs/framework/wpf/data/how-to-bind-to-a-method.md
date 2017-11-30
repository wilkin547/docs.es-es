---
title: "Cómo: Enlazar a un método"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c276e9da3eaaf786038a117532848364b03e9b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-method"></a>Cómo: Enlazar a un método
En el ejemplo siguiente se muestra cómo enlazar a un método mediante <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `TemperatureScale` es una clase que tiene un método `ConvertTemp`, que toma dos parámetros (uno de tipo `double` y uno de tipo `enum``TempType)`, y convierte el valor dado de una escala de temperatura a otra. En el ejemplo siguiente, un <xref:System.Windows.Data.ObjectDataProvider> se utiliza para crear una instancia de la `TemperatureScale` objeto. Se llama al método `ConvertTemp` con dos parámetros especificados.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ahora que el método está disponible como un recurso, puede enlazar a los resultados. En el ejemplo siguiente, la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de la <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> de la <xref:System.Windows.Controls.ComboBox> están enlazados a los dos parámetros del método. Esto permite al usuario especificar la temperatura que se desea convertir y la escala de temperatura desde la que realizar la conversión. Tenga en cuenta que <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> está establecido en `true` porque estamos enlazando a la <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> propiedad de la <xref:System.Windows.Data.ObjectDataProvider> instancia y no las propiedades del objeto englobado por la <xref:System.Windows.Data.ObjectDataProvider> (la `TemperatureScale` objeto).  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> de la última <xref:System.Windows.Controls.Label> se actualiza cuando el usuario modifica el contenido de la <xref:System.Windows.Controls.TextBox> o la selección de la <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 El convertidor `DoubleToString` toma un valor doble y la convierte en una cadena en el <xref:System.Windows.Data.IValueConverter.Convert%2A> dirección (desde el origen de enlace al destino de enlace, que es el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad) y convierte un `string` a una `double` en el <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> dirección.  
  
 El `InvalidationCharacterRule` es un <xref:System.Windows.Controls.ValidationRule> que comprueba si hay caracteres no válidos. La plantilla de error predeterminada, que es un borde rojo alrededor de la <xref:System.Windows.Controls.TextBox>, aparece para notificar a los usuarios cuando el valor de entrada no es un valor de tipo double.  
  
## <a name="see-also"></a>Vea también  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Enlazar a una enumeración](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
