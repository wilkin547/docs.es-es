---
title: "Cómo: Especificar el origen de enlace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23a4c180eb62dd152f1ed24c01b8103ccf1ec562
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-binding-source"></a>Cómo: Especificar el origen de enlace
En el enlace de datos, el objeto de origen de enlace hace referencia al objeto de que se obtienen los datos. Este tema describe las distintas maneras de especificar el origen de enlace.  
  
## <a name="example"></a>Ejemplo  
 Si va a enlazar varias propiedades con un origen común, querrá usar la propiedad `DataContext`, que proporciona una manera cómoda de establecer un ámbito dentro del cual todas las propiedades enlazadas a datos heredan un origen común.  
  
 En el ejemplo siguiente, se establece el contexto de datos en el elemento raíz de la aplicación. Esto permite que todos los elementos secundarios hereden ese contexto de datos. Los datos para el enlace proceden de una clase de datos personalizada, `NetIncome`, al que hace referencia directamente a través de una asignación y una clave de recurso determinada de `incomeDataSource`.  
  
 [!code-xaml[DirectionalBinding#DataContext1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 En el ejemplo siguiente se muestra la definición de la clase `NetIncome`.  
  
 [!code-csharp[DirectionalBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  El ejemplo anterior crea una instancia del objeto en la marcación y lo usa como un recurso. Si desea enlazar con un objeto que ya ha creado una instancia en el código, debe establecer la propiedad `DataContext` mediante programación. Para obtener un ejemplo, vea [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  
  
 Como alternativa, si desea especificar el origen en los enlaces individuales explícitamente, tiene las siguientes opciones. Estas tienen prioridad sobre el contexto de datos heredado.  
  
|Property|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Utilice esta propiedad para establecer el origen en una instancia de un objeto. Si no necesita la funcionalidad de establecer un ámbito en el que varias propiedades hereden el mismo contexto de datos, puede usar el <xref:System.Windows.Data.Binding.Source%2A> propiedad en lugar de la `DataContext` propiedad. Para obtener más información, consulta <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Esto es útil cuando desea especificar el origen con respecto a donde está el destino del enlace. Entre los escenarios frecuentes en los que puede utilizar esta propiedad se encuentran las situaciones en las que desee enlazar una propiedad del elemento con otra propiedad del mismo elemento o situaciones en las que esté definiendo un enlace en un estilo o una plantilla. Para obtener más información, consulta <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Especifique una cadena que represente el elemento con el que desee establecer el enlace. Esto es útil cuando desea enlazar con la propiedad de otro elemento de la aplicación. Por ejemplo, si desea utilizar un <xref:System.Windows.Controls.Slider> para controlar el alto de otro control en la aplicación, o si desea enlazar el <xref:System.Windows.Controls.ContentControl.Content%2A> de control del <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> propiedad de su <xref:System.Windows.Controls.ListBox> control. Para obtener más información, consulta <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>  
 [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
