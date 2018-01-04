---
title: "Cómo: Agregar capacidades de búsqueda a un control ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 111fc6e4945998c99e63560afab6104f4daf89e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Cómo: Agregar capacidades de búsqueda a un control ListView
A menudo cuando se trabaja con una amplia lista de elementos en una <xref:System.Windows.Forms.ListView> (control), que desea ofrecer capacidades de búsqueda para el usuario. El <xref:System.Windows.Forms.ListView> control ofrece esta capacidad de dos maneras diferentes: coincidencia de texto y búsqueda de ubicación.  
  
 El <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método le permite realizar una búsqueda de texto en un <xref:System.Windows.Forms.ListView> en la vista de lista o detalles, dada una cadena de búsqueda y un inicial y final opcional índice. En cambio, el <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método le permite encontrar un elemento en un <xref:System.Windows.Forms.ListView> en la vista de icono o en mosaico, dado un conjunto de coordenadas x e y y una dirección de búsqueda.  
  
### <a name="to-find-an-item-using-text"></a>Para buscar un elemento mediante texto  
  
1.  Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.ListView.View%2A> propiedad establecida en <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame a la <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método, pasando el texto del elemento que desea buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Forms.ListView>, rellenarlo con elementos y utilice la entrada de texto del usuario para buscar un elemento en la lista.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Para buscar un elemento mediante las coordenadas x e y  
  
1.  Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.View> propiedad establecida en <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame a la <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método, pasando el deseado - coordenadas x e y- y la dirección que desea buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un icono básico <xref:System.Windows.Forms.ListView>, rellenarlo con elementos y capture el <xref:System.Windows.Forms.Control.MouseDown> eventos para buscar el elemento más cercano en una búsqueda hacia arriba.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
