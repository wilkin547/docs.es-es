---
title: "Buscar un elemento de UI Automation basándose en una condición de propiedad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: cafd84ce3acea80905d686f33f23338e3581a9c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Buscar un elemento de UI Automation basándose en una condición de propiedad
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo buscar un elemento dentro del [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol en función de una o varias propiedades específicas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un conjunto de condiciones de propiedades se especifican que identifican un elemento determinado (o elementos) de interés en el <xref:System.Windows.Automation.AutomationElement> árbol. A continuación, se realiza una búsqueda para todos los elementos coincidentes con la <xref:System.Windows.Automation.AutomationElement.FindAll%2A> método que incorpora una serie de <xref:System.Windows.Automation.AndCondition> las operaciones booleanas para limitar el número de elementos coincidentes.  
  
> [!NOTE]
>  Al realizar búsquedas desde el <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, debe intentar obtener solo elementos secundarios directos. Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo cual puede provocar un desbordamiento de pila. Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de elemento de menú ExpandCollapsePattern y InvokePattern](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [Obtener elementos de UI Automation](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [Utilizar la propiedad AutomationID](../../../docs/framework/ui-automation/use-the-automationid-property.md)
