---
title: Filtrar para agregar funcionalidades de búsqueda a un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: c1c59c3d4bb5d0d35103371575ebdd49d3559bbe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108555"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Filtrar para agregar funcionalidades de búsqueda a un control ListView
A menudo, cuando se trabaja con una amplia lista de elementos en un <xref:System.Windows.Forms.ListView> control, desea ofrecer capacidades de búsqueda para el usuario. El <xref:System.Windows.Forms.ListView> control ofrece esta funcionalidad de dos maneras diferentes: coincidencia de texto y búsqueda de ubicación.  
  
 El <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método le permite realizar una búsqueda de texto en un <xref:System.Windows.Forms.ListView> en la vista de lista o detalles, dada una cadena de búsqueda y una inicial y final opcional índice. En cambio, el <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método le permite encontrar un elemento en un <xref:System.Windows.Forms.ListView> en el icono o el icono de vista, dado un conjunto de coordenadas x e y y una dirección de búsqueda.  
  
### <a name="to-find-an-item-using-text"></a>Para encontrar un elemento usando el texto  
  
1.  Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.ListView.View%2A> propiedad establecida en <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame a la <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método, pasando el texto del elemento que desea buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Forms.ListView>, rellenarla con los elementos y usar la entrada de texto del usuario para encontrar un elemento en la lista.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Para buscar un elemento mediante las coordenadas x e y  
  
1.  Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.View> propiedad establecida en <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame a la <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método, pasando el deseado: coordenadas x e y- y la dirección que desea buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un icono básico <xref:System.Windows.Forms.ListView>, rellenarla con los elementos y capture el <xref:System.Windows.Forms.Control.MouseDown> eventos para buscar el elemento más cercano en la búsqueda hacia arriba.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [Control ListView](listview-control-windows-forms.md)
- [Información general sobre el control ListView](listview-control-overview-windows-forms.md)
- [Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
