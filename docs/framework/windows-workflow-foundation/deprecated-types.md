---
title: Tipos en desuso en Windows Workflow Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 085b0590d08843477c4dff4754791c93110b1fb7
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Tipos en desuso en Windows Workflow Foundation
En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> . Con la versión de .NET 4.5 Beta vamos a marcar la mayoría de los tipos en el "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, y <xref:System.Workflow.Runtime> los espacios de nombres como obsoleto.  
  
## <a name="obsolete-namespaces-and-tools"></a>Espacios de nombres y herramientas obsoletos  
 Los ensamblados siguientes tienen uno o varios tipos públicos que están obsoletos:  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 Como resultado, los clientes que usan API en desuso de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:  
  
 **Advertencia BC40000: X está obsoleta: tipos de WF 3 están en desuso. Use W4 en su lugar.** Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario (no en 4.5). Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4. Por supuesto, continuaremos admitir estos tipos de WF 3 en el [directiva de ciclo de vida de Microsoft admiten](http://aka.ms/MicrosoftSupportLifecycle). Las aplicaciones WF3 existentes se ejecutarán sin problema en .NET 4.5, y [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] admitirá nuevas y existentes soluciones basadas en WF3.  
  
 Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.  
  
 Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en la [Guía de migración de flujo de trabajo 4](migration-guidance.md).
