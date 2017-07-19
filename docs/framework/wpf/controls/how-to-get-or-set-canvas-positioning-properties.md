---
title: "C&#243;mo: Obtener o establecer propiedades de situaci&#243;n de Canvas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Canvas (control), establecer propiedades de posición"
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Obtener o establecer propiedades de situaci&#243;n de Canvas
En este ejemplo se muestra cómo utilizar los métodos de posición del elemento <xref:System.Windows.Controls.Canvas> para colocar el contenido secundario.  En este ejemplo se utiliza el contenido de <xref:System.Windows.Controls.ListBoxItem> para representar los valores de posición y se convierten los valores en instancias de <xref:System.Double>, que es un argumento necesario para establecer la posición.  A continuación, los valores se convierten de nuevo en cadenas y se muestran como texto en un elemento <xref:System.Windows.Controls.TextBlock> mediante el método <xref:System.Windows.Controls.Canvas.GetLeft%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un elemento <xref:System.Windows.Controls.ListBox> que tiene once elementos <xref:System.Windows.Controls.ListBoxItem> seleccionables.  El evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> desencadena el método personalizado `ChangeLeft`, que se define en el bloque de código subsiguiente.  
  
 Cada elemento <xref:System.Windows.Controls.ListBoxItem> representa un valor <xref:System.Double>, que es uno de los argumentos aceptados por el método <xref:System.Windows.Controls.Canvas.SetLeft%2A> de <xref:System.Windows.Controls.Canvas>.  Para utilizar <xref:System.Windows.Controls.ListBoxItem> a fin de representar una instancia de <xref:System.Double>, antes debe convertir <xref:System.Windows.Controls.ListBoxItem> al tipo de datos correcto.  
  
 [!code-xml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Cuando un usuario cambia la selección de <xref:System.Windows.Controls.ListBox>, se invoca el método personalizado `ChangeLeft`.  Este método pasa el elemento <xref:System.Windows.Controls.ListBoxItem> a un objeto <xref:System.Windows.LengthConverter>, que convierte la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de <xref:System.Windows.Controls.ListBoxItem> en una instancia de <xref:System.Double> \(observe que este valor ya se ha convertido al tipo <xref:System.String> mediante el método <xref:System.Windows.Controls.Control.ToString%2A>\).  A continuación, se devuelve este valor a los métodos <xref:System.Windows.Controls.Canvas.SetLeft%2A> y <xref:System.Windows.Controls.Canvas.GetLeft%2A> de <xref:System.Windows.Controls.Canvas> para cambiar la posición del objeto `text1`.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.ListBoxItem>   
 <xref:System.Windows.LengthConverter>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)