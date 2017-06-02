---
title: "C&#243;mo: Usar un diccionario de recursos en el &#225;mbito de aplicaci&#243;n | Microsoft Docs"
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
  - "diccionarios de recursos en el ámbito de la aplicación"
  - "diccionarios, recurso"
  - "diccionarios de recursos, ámbito de la aplicación"
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Usar un diccionario de recursos en el &#225;mbito de aplicaci&#243;n
En este ejemplo se muestra cómo definir y usar un diccionario de recursos personalizado de ámbito de aplicación.  
  
## Ejemplo  
 <xref:System.Windows.Application> expone un almacén de ámbito de aplicación para los recursos compartidos: <xref:System.Windows.Application.Resources%2A>.  De manera predeterminada, la propiedad <xref:System.Windows.Application.Resources%2A> se inicializa con una instancia del tipo <xref:System.Windows.ResourceDictionary>.  Esta instancia se usa al obtener y establecer propiedades del ámbito de aplicación mediante la propiedad <xref:System.Windows.Application.Resources%2A>.  \(Para obtener más información, vea [How to: Get and Set an Application\-Scope Resource](http://msdn.microsoft.com/es-es/39e0420c-c9fc-47dc-8956-fdd95b214095)\).  
  
 Si tiene varios recursos que se establecen mediante <xref:System.Windows.Application.Resources%2A>, en su lugar puede utilizar un diccionario de recursos personalizado para almacenar esos recursos y establecer <xref:System.Windows.Application.Resources%2A> en dicho diccionario.  A continuación se muestra cómo declarar un diccionario de recursos personalizado mediante XAML.  
  
 [!code-xml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 El intercambio de diccionarios de recursos completos mediante <xref:System.Windows.Application.Resources%2A> permite admitir temas del ámbito de aplicación, donde cada tema se encapsula en un solo diccionario de recursos.  En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 A continuación se muestra cómo puede obtener recursos del ámbito de la aplicación del diccionario de recursos expuesto por <xref:System.Windows.Application.Resources%2A> en XAML.  
  
 [!code-xml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 A continuación se muestra cómo puede obtener también los recursos en código.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Debe tener en cuenta dos aspectos al usar <xref:System.Windows.Application.Resources%2A>.  En primer lugar, la *clave* de diccionario es un objeto, por lo que debe usar exactamente la misma instancia de objeto al establecer y al obtener un valor de propiedad.  \(Tenga en cuenta que la clave distingue mayúsculas de minúsculas cuando se usa una cadena.\) En segundo lugar, el *valor* del diccionario es un objeto, por lo que tendrá que convertir el valor al tipo que desee cuando obtenga un valor de propiedad.  
  
## Vea también  
 <xref:System.Windows.ResourceDictionary>   
 <xref:System.Windows.Application.Resources%2A>   
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Diccionarios de recursos combinados](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)