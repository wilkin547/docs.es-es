---
title: Tipos obsoletos en Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: b0ec30d2778333537e781e6681927f7048b630ea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543789"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Tipos obsoletos en Windows Workflow Foundation
En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> . Con el lanzamiento de .NET 4,5 beta, estamos marcando la mayoría de los tipos en los espacios de nombres "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> y  <xref:System.Workflow.Runtime> como obsoletos.  
  
## <a name="obsolete-namespaces-and-tools"></a>Espacios de nombres y herramientas obsoletos  
 Los ensamblados siguientes tienen uno o varios tipos públicos que están en desuso:  
  
- System.Workflow.Activities.dll  
  
- System.Workflow.ComponentModel.dll  
  
- System.Workflow.Runtime.dll  
  
- System.WorkflowServices.dll  
  
- Microsoft.Workflow.DebugController.dll  
  
- Microsoft.Workflow.Compiler.exe  
  
- Wfc.exe  
  
 Como resultado, los clientes que usan API obsoletas de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:  
  
 **ADVERTENCIA BC40000: X está obsoleto: los tipos de WF 3 están en desuso. En su lugar, use WF 4.** Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario (no en 4.5). Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4. Por supuesto, continuaremos admitiendo estos tipos de WF 3 en la [Directiva del ciclo de vida de soporte técnico de Microsoft](/lifecycle/). Las aplicaciones de WF3 existentes se ejecutarán sin problemas en .NET 4,5 y Visual Studio 2012 admitirá soluciones basadas en WF3 nuevas y existentes.  
  
 Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.  
  
 Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en la [Guía de migración de flujo de trabajo 4](migration-guidance.md).
