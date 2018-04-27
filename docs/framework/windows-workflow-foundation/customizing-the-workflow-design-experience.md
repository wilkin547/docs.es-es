---
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ee64ae3db9dbf98f2a62397075406c118a867bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizar la experiencia de diseño del flujo de trabajo
Los escenarios para diseñar las actividades personalizadas y para re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] se han simplificado enormemente en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. El desarrollo y la implementación resultan ahora más fáciles y más flexibles. El cambio infraestructural clave es que el nuevo modelo de programación Diseñador de actividad se compila en Windows Presentation Foundation (WPF). Esto proporciona la capacidad de definir diseñadores de actividad mediante declaración y re-hospedar [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en otras aplicaciones con relativa facilidad. Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado. La integración con [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se ha vuelto más uniforme con el uso de los servicios del flujo de trabajo. Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de plantillas y diseñadores de actividad personalizados](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 Describe cómo crear diseñadores de actividad personalizados y plantillas.  
  
 [Rehospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 Describe cómo re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] fuera de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] y cómo mostrar errores de validación.  
  
 [Utilización de un editor de expresiones personalizado](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 Describe cómo implementar un editor de expresiones personalizado para utilizar con los diseñadores de flujo de trabajo rehospedados fuera de [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
## <a name="reference"></a>Referencia  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a>Vea también  
 [Extensión de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [Diseñador](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [Diseñadores de actividad personalizados](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [Rehospedaje del diseñador](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
