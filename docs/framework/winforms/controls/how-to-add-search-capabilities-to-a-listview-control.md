---
title: "C&#243;mo: Agregar capacidades de b&#250;squeda a un control ListView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "vistas de lista, habilitar búsquedas"
  - "listas, habilitar búsquedas"
  - "ListView (control) [Windows Forms], agregar funciones de búsqueda"
  - "buscar, agregar funciones de búsqueda al control ListView"
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Agregar capacidades de b&#250;squeda a un control ListView
A menudo al trabajar con una lista grande de elementos en un control <xref:System.Windows.Forms.ListView>, se desea ofrecer funciones de búsqueda al usuario.  El control <xref:System.Windows.Forms.ListView> proporciona esta función de dos maneras diferentes: la coincidencia de texto y la búsqueda de ubicación.  
  
 El método <xref:System.Windows.Forms.ListView.FindItemWithText%2A> permite realizar una búsqueda de texto en <xref:System.Windows.Forms.ListView> en una vista de lista o de detalles, proporcionando una cadena de búsqueda y un índice inicial y final opcional.  Por el contrario, el método <xref:System.Windows.Forms.ListView.FindNearestItem%2A> permite encontrar un elemento en <xref:System.Windows.Forms.ListView> en una vista en icono o en mosaico, proporcionando un conjunto de coordenadas x e y y una dirección para buscar.  
  
### Para encontrar un elemento utilizando el texto  
  
1.  Cree un <xref:System.Windows.Forms.ListView> con la propiedad <xref:System.Windows.Forms.ListView.View%2A> establecida en <xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View> y, a continuación, rellene <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame al método <xref:System.Windows.Forms.ListView.FindItemWithText%2A>, pasando el texto del elemento que le gustaría buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Forms.ListView> básico, cómo rellenarlo con elementos y cómo utilizar la entrada de texto por el usuario para buscar un elemento en la lista.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### Para buscar un elemento mediante las coordenadas x e y  
  
1.  Cree un <xref:System.Windows.Forms.ListView> con la propiedad <xref:System.Windows.Forms.View> establecida en <xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View> y, a continuación, rellene <xref:System.Windows.Forms.ListView> con elementos.  
  
2.  Llame al método <xref:System.Windows.Forms.ListView.FindNearestItem%2A>, pasando las coordenadas x e y deseadas, así como la dirección en la que desea buscar.  
  
3.  En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Forms.ListView> de icono básico, cómo rellenarlo con elementos y cómo capturar el evento <xref:System.Windows.Forms.Control.MouseDown> para buscar el elemento más cercano en una búsqueda hacia arriba.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>   
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)