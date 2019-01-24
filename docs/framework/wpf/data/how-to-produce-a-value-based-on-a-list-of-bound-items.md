---
title: Procedimiento Generar un valor basado en una lista de elementos enlazados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: 8f4e5b7767e475128b61080ca87e38ee311f4a3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706435"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Procedimiento Generar un valor basado en una lista de elementos enlazados
<xref:System.Windows.Data.MultiBinding> permite enlazar una propiedad de destino de enlace a una lista de propiedades de origen y, a continuación, aplicar la lógica para generar un valor con las entradas proporcionadas. Este ejemplo muestra cómo usar <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `NameListData` hace referencia a la colección de objetos `PersonName`, que son objetos que contienen dos propiedades, `firstName` y `lastName`. En el ejemplo siguiente se genera un <xref:System.Windows.Controls.TextBlock> que muestra los nombres y apellidos de una persona con el apellido en primer lugar.  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Para entender cómo se genera el formato de apellidos-nombre echemos un vistazo a la implementación de `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementa la interfaz <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` toma los valores de los enlaces individuales y los almacena en la matriz de objeto de valores. El orden en que el <xref:System.Windows.Data.Binding> elementos aparecerán bajo el <xref:System.Windows.Data.MultiBinding> elemento es el orden en que esos valores se almacenan en la matriz. El valor de la <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> atributo hace referencia el argumento del parámetro de la <xref:System.Windows.Data.MultiBinding.Converter%2A> método, que realiza un cambio en el parámetro para determinar cómo dar formato al nombre.  
  
## <a name="see-also"></a>Vea también
- [Convertir datos enlazados](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
