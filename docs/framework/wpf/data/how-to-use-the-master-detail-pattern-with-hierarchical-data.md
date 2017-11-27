---
title: "Cómo: Usar el patrón principal-detalle con datos jerárquicos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Cómo: Usar el patrón principal-detalle con datos jerárquicos
En este ejemplo se muestra cómo implementar el escenario principal-detalle.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `LeagueList` es una colección de `Leagues`. Cada `League` tiene un `Name` y una colección de `Divisions`y cada `Division` tiene un nombre y una colección de `Teams`. Cada `Team` tiene un nombre de equipo.  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 La siguiente captura de pantalla muestra el ejemplo. El `Divisions` <xref:System.Windows.Controls.ListBox> automáticamente realiza un seguimiento de las selecciones en la `Leagues` <xref:System.Windows.Controls.ListBox> y mostrar los datos correspondientes. El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en los otros dos <xref:System.Windows.Controls.ListBox> controles.  
  
 ![Patrón &#45; ejemplo detalle](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Las dos cosas que se observan en este ejemplo son:  
  
1.  Los tres <xref:System.Windows.Controls.ListBox> controles se enlazan al mismo origen. Establece el <xref:System.Windows.Data.Binding.Path%2A> propiedad del enlace para especificar el nivel de datos desea que el <xref:System.Windows.Controls.ListBox> para mostrar.  
  
2.  Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` en el <xref:System.Windows.Controls.ListBox> controles de los cuales la selección está realizando el seguimiento. Al establecer esta propiedad se asegura de que el elemento seleccionado siempre se establece como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene datos de un <xref:System.Windows.Data.CollectionViewSource>, sincroniza automáticamente selección y moneda.  
  
 La técnica es ligeramente diferente cuando se utiliza [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos. Para obtener un ejemplo, vea [usar el patrón principal-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [Enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
