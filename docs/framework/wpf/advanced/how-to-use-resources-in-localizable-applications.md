---
title: "Cómo: Usar recursos en aplicaciones localizables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e025b42a72def81420de7d82dcf027405669ce78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Cómo: Usar recursos en aplicaciones localizables
Localización significa adaptar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a distintas referencias culturales. Para ello, debe traducirse el texto, como títulos, leyendas, elementos de cuadro de lista, etc. Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos. Vea [adaptar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para la localización. Para realizar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizable, los desarrolladores necesitan compilar todos los recursos localizables en un ensamblado de recursos de la aplicación. El ensamblado de recursos se localiza a idiomas diferentes y el código subyacente utiliza la administración de recursos [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] para cargar. Uno de los archivos necesarios para un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación es un archivo de proyecto (proj). Todos los recursos que se usan en la aplicación deben incluirse en el archivo de proyecto. El ejemplo de código siguiente muestra cómo hacerlo.  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Para usar un recurso de la aplicación, se crea una instancia <xref:System.Resources.ResourceManager> y cargue el recurso que desea utilizar. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
