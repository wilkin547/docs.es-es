---
title: 'Cómo: Usar el patrón principal-detalle con datos XML jerárquicos'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733416"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Cómo: Usar el patrón principal-detalle con datos XML jerárquicos
Este ejemplo muestra cómo implementar el escenario principal-detalle con datos XML.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo es la versión de datos XML del ejemplo que se describe en [uso del patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). En este ejemplo, los datos proceden del archivo `League.xml`. Observe cómo el tercer control de <xref:System.Windows.Controls.ListBox> realiza un seguimiento de los cambios de selección en el segundo <xref:System.Windows.Controls.ListBox> enlazando a su propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.HierarchicalDataTemplate>
- [Temas "Cómo..."](data-binding-how-to-topics.md)
