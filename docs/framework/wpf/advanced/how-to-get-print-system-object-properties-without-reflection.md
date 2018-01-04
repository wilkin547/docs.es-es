---
title: "Cómo: Obtener propiedades de un objeto de sistema de impresión sin reflexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d93919f691b51d5f177b074e5d9cef2c140458e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Cómo: Obtener propiedades de un objeto de sistema de impresión sin reflexión
Use la reflexión para detallar las propiedades (y los tipos de esas propiedades) en un objeto puede ralentizar el rendimiento de la aplicación. El <xref:System.Printing.IndexedProperties> espacio de nombres proporciona un medio para obtener esta información sin utilizar la reflexión.  
  
## <a name="example"></a>Ejemplo  
 Los pasos para hacerlo son los siguientes.  
  
1.  Cree una instancia del tipo. En el ejemplo siguiente, el tipo es el <xref:System.Printing.PrintQueue> tipo que se suministra con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], pero un código prácticamente idéntico debería funcionar para los tipos que derivan de <xref:System.Printing.PrintSystemObject>.  
  
2.  Crear un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. El <xref:System.Collections.DictionaryEntry.Value%2A> propiedad de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Enumerar a los miembros del diccionario. Para cada uno de ellos, haga lo siguiente.  
  
4.  Convierta el valor de cada entrada para <xref:System.Printing.IndexedProperties.PrintProperty> y usarlo para crear un <xref:System.Printing.IndexedProperties.PrintProperty> objeto.  
  
5.  Obtiene el tipo de la <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> de cada uno de los <xref:System.Printing.IndexedProperties.PrintProperty> objeto.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)
