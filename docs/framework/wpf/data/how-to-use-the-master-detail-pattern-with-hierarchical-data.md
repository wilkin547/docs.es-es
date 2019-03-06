---
title: Filtrar Usar el patrón principal-detalle con datos jerárquicos
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 41f02013feb1405e5640afa73b954dc84921c924
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351488"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Filtrar Usar el patrón principal-detalle con datos jerárquicos
En este ejemplo se muestra cómo implementar el escenario principal-detalle.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `LeagueList` es una colección de `Leagues`. Cada `League` tiene un `Name` y una colección de `Divisions`y cada `Division` tiene un nombre y una colección de `Teams`. Cada `Team` tiene un nombre de equipo.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 La siguiente captura de pantalla muestra el ejemplo. El `Divisions` <xref:System.Windows.Controls.ListBox> automáticamente realiza un seguimiento de las selecciones en la `Leagues` <xref:System.Windows.Controls.ListBox> y mostrar los datos correspondientes. El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en las otras dos <xref:System.Windows.Controls.ListBox> controles.  
  
 ![Master&#45;ejemplo detalle](./media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Las dos cosas a tener en cuenta en este ejemplo son:  
  
1.  Los tres <xref:System.Windows.Controls.ListBox> los controles se enlazan al mismo origen. Establece el <xref:System.Windows.Data.Binding.Path%2A> propiedad del enlace para especificar el nivel de datos desea que el <xref:System.Windows.Controls.ListBox> para mostrar.  
  
2.  Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` en el <xref:System.Windows.Controls.ListBox> controles de los cuales la selección está realizando el seguimiento. Al establecer esta propiedad garantiza que siempre se establece el elemento seleccionado como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene sus datos desde un <xref:System.Windows.Data.CollectionViewSource>, sincronización automáticamente selección y moneda.  
  
 La técnica es ligeramente diferente cuando se usa [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos. Para obtener un ejemplo, vea [usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.HierarchicalDataTemplate>
- [Enlazar a una colección y mostrar información basada en la selección](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Información general sobre plantillas de datos](data-templating-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
