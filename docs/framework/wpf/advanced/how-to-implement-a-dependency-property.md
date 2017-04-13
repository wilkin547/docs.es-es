---
title: "C&#243;mo: Implementar una propiedad de dependencia | Microsoft Docs"
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
  - "propiedades de dependencia, respaldar propiedades con"
  - "propiedades, respaldar con propiedades de dependencia"
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Implementar una propiedad de dependencia
En este ejemplo se muestra cómo respaldar una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] con un campo <xref:System.Windows.DependencyProperty>, para definir así una [propiedad de dependencia](GTMT).  Si define sus propias propiedades y desea que admitan numerosos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como [propiedades de dependencia](GTMT).  
  
## Ejemplo  
 En el ejemplo siguiente se registra en primer lugar una [propiedad de dependencia](GTMT) llamando al método <xref:System.Windows.DependencyProperty.Register%2A>.  El nombre del campo identificador que se utiliza para almacenar el nombre y las características de la [propiedad de dependencia](GTMT) debe ser el valor de <xref:System.Windows.DependencyProperty.Name%2A> que eligió para la propiedad de dependencia como la parte de la llamada al método <xref:System.Windows.DependencyProperty.Register%2A>, con la cadena literal `Property` anexada a dicho valor.  Por ejemplo, si registra una propiedad de dependencia cuyo valor de <xref:System.Windows.DependencyProperty.Name%2A> es `Location`, el campo identificador que defina para la propiedad de dependencia deberá denominarse `LocationProperty`.  
  
 En este ejemplo, el nombre de la [propiedad de dependencia](GTMT) y su descriptor de acceso [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] es `State`; el campo de identificador es `StateProperty`; el tipo de la propiedad es <xref:System.Boolean>; y el tipo que registra la [propiedad de dependencia](GTMT) es `MyStateControl`.  
  
 Si no sigue este modelo de nombres, puede que los diseñadores no informen correctamente sobre la propiedad y es posible que algunos aspectos de la aplicación de estilos del sistema a las propiedades no se comporten como cabría esperar.  
  
 También puede especificar metadatos predeterminados para una [propiedad de dependencia](GTMT).  En este ejemplo se registra que el valor predeterminado de la [propiedad de dependencia](GTMT) `State` es `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Para obtener más información sobre cómo y por qué implementar una [propiedad de dependencia](GTMT), en lugar de limitarse a respaldar una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con un campo privado, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)