---
title: 'Cómo: Generar un valor basado en una lista de elementos enlazados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459694"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Cómo: Generar un valor basado en una lista de elementos enlazados
<xref:System.Windows.Data.MultiBinding> permite enlazar una propiedad de destino de enlace a una lista de propiedades de origen y, a continuación, aplicar la lógica para generar un valor con las entradas especificadas. En este ejemplo se muestra cómo utilizar <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `NameListData` hace referencia a la colección de objetos `PersonName`, que son objetos que contienen dos propiedades, `firstName` y `lastName`. En el ejemplo siguiente se genera un <xref:System.Windows.Controls.TextBlock> que muestra el nombre y los apellidos de una persona con el apellido primero.  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Para entender cómo se genera el formato de apellidos-nombre echemos un vistazo a la implementación de `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementa la interfaz <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` toma los valores de los enlaces individuales y los almacena en la matriz de objeto de valores. El orden en que aparecen los elementos <xref:System.Windows.Data.Binding> bajo el elemento <xref:System.Windows.Data.MultiBinding> es el orden en que esos valores se almacenan en la matriz. En el argumento de parámetro del método <xref:System.Windows.Data.MultiBinding.Converter%2A> se hace referencia al valor del atributo <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A>, que realiza un modificador en el parámetro para determinar cómo dar formato al nombre.  
  
## <a name="see-also"></a>Vea también

- [Convertir datos enlazados](how-to-convert-bound-data.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
