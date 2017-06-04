---
title: "C&#243;mo: Usar recursos en aplicaciones localizables | Microsoft Docs"
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
  - "aplicaciones, localizables"
  - "aplicaciones localizables"
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Usar recursos en aplicaciones localizables
La localización significa adaptar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a otras referencias culturales.  Para ello, los textos tales como los títulos, leyendas, elementos de cuadro de lista, etc. deben traducirse.  Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos.  Vea [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para localización.  Para que una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sea localizable, los programadores deben integrar todos los recursos localizables en un ensamblado de recursos.  El ensamblado de recursos se localiza a distintos idiomas y el código subyacente utiliza la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] de administración de recursos para cargarse.  Uno de los archivos requeridos para una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un archivo de proyecto \(.proj\).  Todos los recursos que se utilizan en una aplicación deben incluirse en el archivo de proyecto.  El ejemplo de código siguiente lo demuestra.  
  
## Ejemplo  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Para utilizar un recurso en la aplicación, cree una instancia de <xref:System.Resources.ResourceManager> y cargue el recurso que desea utilizar.  A continuación se muestra cómo hacerlo.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]