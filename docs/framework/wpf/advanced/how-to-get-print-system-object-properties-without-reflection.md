---
title: "C&#243;mo: Obtener propiedades de un objeto de sistema de impresi&#243;n sin reflexi&#243;n | Microsoft Docs"
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
  - "PrintSystemObject, obtener propiedades"
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Obtener propiedades de un objeto de sistema de impresi&#243;n sin reflexi&#243;n
Utilizar la reflexión para detallar las propiedades \(y los tipos de esas propiedades\) de un objeto puede deteriorar el rendimiento de la aplicación.  El espacio de nombres <xref:System.Printing.IndexedProperties> proporciona un medio para obtener esta información sin utilizar la reflexión.  
  
## Ejemplo  
 Los pasos para hacerlo son los siguientes.  
  
1.  Cree una instancia del tipo.  En el ejemplo siguiente, el tipo es el tipo <xref:System.Printing.PrintQueue> que se distribuye con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], pero un código prácticamente idéntico debería funcionar para los tipos que derive de <xref:System.Printing.PrintSystemObject>.  
  
2.  Cree <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> a partir de la propiedad <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> del tipo.  La propiedad <xref:System.Collections.DictionaryEntry.Value%2A> de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Enumere los miembros del diccionario.  Para cada uno de ellos, haga lo siguiente.  
  
4.  Convierta el tipo del valor de cada entrada a <xref:System.Printing.IndexedProperties.PrintProperty> y utilícelo para crear un objeto <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
5.  Obtenga el tipo de la propiedad <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> de cada uno de los objetos <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## Vea también  
 <xref:System.Printing.IndexedProperties.PrintProperty>   
 <xref:System.Printing.PrintSystemObject>   
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)