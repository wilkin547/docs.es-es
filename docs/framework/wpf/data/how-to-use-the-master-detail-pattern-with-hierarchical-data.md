---
title: 'Cómo: Usar el patrón principal-detalle con datos jerárquicos'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733482"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Cómo: Usar el patrón principal-detalle con datos jerárquicos
Este ejemplo muestra cómo implementar el escenario principal-detalle.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `LeagueList` es una colección de `Leagues`. Cada `League` tiene una `Name` y una colección de `Divisions`, y cada `Division` tiene un nombre y una colección de `Teams`. Cada `Team` tiene un nombre de equipo.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 La siguiente captura de pantalla muestra el ejemplo. El `Divisions` <xref:System.Windows.Controls.ListBox> realiza un seguimiento automático de las selecciones en el `Leagues` <xref:System.Windows.Controls.ListBox> y muestra los datos correspondientes. El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en los otros dos controles de <xref:System.Windows.Controls.ListBox>.  
  
 ![Captura de pantalla que muestra&#45;un ejemplo de escenario de detalle maestro.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 Los dos aspectos que se deben tener en cuenta en este ejemplo son:  
  
1. Los tres controles <xref:System.Windows.Controls.ListBox> enlazan al mismo origen. Establezca la propiedad <xref:System.Windows.Data.Binding.Path%2A> del enlace para especificar el nivel de datos que desea que muestre el <xref:System.Windows.Controls.ListBox>.  
  
2. Debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` en los controles de <xref:System.Windows.Controls.ListBox> de los que se realiza el seguimiento de la selección. Al establecer esta propiedad, se asegura de que el elemento seleccionado siempre se establece como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si el <xref:System.Windows.Controls.ListBox> obtiene datos de una <xref:System.Windows.Data.CollectionViewSource>, sincroniza la selección y la moneda automáticamente.  
  
 La técnica es ligeramente diferente cuando se usan datos XML. Para obtener un ejemplo, consulte [usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.HierarchicalDataTemplate>
- [Enlazar a una colección y mostrar información basada en la selección](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](data-templating-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
