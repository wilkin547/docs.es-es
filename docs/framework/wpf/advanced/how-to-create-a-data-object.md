---
title: "C&#243;mo: Crear un objeto de datos | Microsoft Docs"
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
  - "objetos de datos [WPF], crear"
  - "DataObject (clase) [WPF], crear"
  - "arrastrar y colocar [WPF], crear objetos de datos"
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Crear un objeto de datos
En los ejemplos siguientes se muestran varias maneras de crear un objeto de datos mediante los constructores proporcionadas por la clase <xref:System.Windows.DataObject>.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se crea un nuevo objeto de datos y se utiliza uno de los constructores sobrecargados \(<xref:System.Windows.DataObject.%23ctor%28System.Object%29>\) para inicializar el objeto de datos con una cadena.  En este caso, se determina un formato de datos adecuado automáticamente según el tipo de datos almacenados y se permite la autoconversión de los datos almacenados de manera predeterminada.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### Descripción  
 El ejemplo de código siguiente es una versión reducida del código de ejemplo anterior.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se crea un nuevo objeto de datos y se utiliza uno de los constructores sobrecargados \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de los datos lo especifica una cadena; la clase <xref:System.Windows.DataFormats> proporciona un conjunto de cadenas de tipo predefinidas.  Se permite la autoconversión de los datos almacenados de forma predeterminada.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### Descripción  
 El ejemplo de código siguiente es una versión reducida del código de ejemplo anterior.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se crea un nuevo objeto de datos y se utiliza uno de los constructores sobrecargados \(<xref:System.Windows.DataObject.%23ctor%2A>\) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de los datos lo especifica un parámetro de <xref:System.Type>.  Se permite la autoconversión de los datos almacenados de forma predeterminada.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### Descripción  
 El ejemplo de código siguiente es una versión reducida del código de ejemplo anterior.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se crea un nuevo objeto de datos y se utiliza uno de los constructores sobrecargados \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>\) para inicializar el objeto de datos con una cadena y un formato de datos especificado.  En este caso, el formato de los datos lo especifica una cadena; la clase <xref:System.Windows.DataFormats> proporciona un conjunto de cadenas de tipo predefinidas.  La sobrecarga de este constructor determinado permite que el llamador especifique si se permite la autoconversión.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### Descripción  
 El ejemplo de código siguiente es una versión reducida del código de ejemplo anterior.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## Vea también  
 <xref:System.Windows.IDataObject>