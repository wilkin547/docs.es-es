---
title: Actividades de control de errores en WF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1c0459dd562f6292a8fe9a42f8b1b48cd175516a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="error-handling-activities-in-wf"></a>Actividades de control de errores en WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias actividades proporcionadas por el sistema para implementar el control y la recuperación de errores. Para obtener más información, consulte [excepciones](../../../docs/framework/windows-workflow-foundation/exceptions.md).  
  
## <a name="error-handling-activities"></a>Actividades de control de errores  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|Vuelve a iniciar la última excepción que se produjo desde una actividad `TryCatch`.|  
|<xref:System.Activities.Statements.Throw>|Inicia una excepción.|  
|<xref:System.Activities.Statements.TryCatch>|Implementa el control de excepciones.|
