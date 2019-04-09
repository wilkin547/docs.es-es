---
title: Filtrar Enlazar a datos un control ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106448"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Filtrar Enlazar a datos un control ListBox
Puede crear un programador de aplicaciones <xref:System.Windows.Controls.ListBox> controles sin especificar el contenido de cada <xref:System.Windows.Controls.ListBoxItem> por separado. Puede usar el enlace de datos para enlazar datos a los elementos individuales.  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.ListBox> que rellena la <xref:System.Windows.Controls.ListBoxItem> elementos de enlace de datos a un origen de datos denominado *colores*. En este caso no es necesario utilizar <xref:System.Windows.Controls.ListBoxItem> etiquetas para especificar el contenido de cada elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Controles](../advanced/optimizing-performance-controls.md)
