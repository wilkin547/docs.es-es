---
title: <services> de <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 0bd2219e7d23376d9cf91262eec3942903be6da1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556478"
---
# <a name="services-of-workflowruntime"></a>\<services> de \<workflowRuntime>
Representa la colección de servicios que se agregarán al motor <xref:System.Workflow.Runtime.WorkflowRuntime>. Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado. Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores. Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [Archivos de configuración del flujo de trabajo](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
