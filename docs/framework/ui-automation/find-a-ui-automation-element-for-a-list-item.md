---
title: Buscar un elemento de UI Automation para un elemento de lista
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: 5
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 727610b910cecbfa2b4c2eb1064fc357be822d42
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Buscar un elemento de UI Automation para un elemento de lista
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema muestra cómo recuperar un <xref:System.Windows.Automation.AutomationElement> para un elemento dentro de una lista cuando se conoce el índice del elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos maneras de recuperar un elemento especificado de una lista, uno con <xref:System.Windows.Automation.TreeWalker> y el uso de otra <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 La primera técnica suele ser más rápido para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles, pero el segundo es más rápido para los controles de Windows Presentation Foundation (WPF).  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Vea también  
 [Obtención de elementos de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
