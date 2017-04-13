---
title: "Deprecated types in Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Deprecated types in Windows Workflow Foundation
En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> .  Con la versión de .NET 4.5 Beta vamos a marcar la mayoría de los tipos de los espacios de nombres de "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel> y <xref:System.Workflow.Runtime> como obsoletos.  
  
## Espacios de nombres y herramientas obsoletos  
 Los ensamblados siguientes tienen uno o varios tipos públicos que están obsoletos:  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 Como resultado, los clientes que usan API obsoletas de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:  
  
  **Advertencia BC40000: X está obsoleta: los tipos de WF 3 están obsoletos.  Use W4 en su lugar.**  Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario \(no en 4.5\).  Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4.  Por supuesto, continuaremos dando soporte a estos tipos de WF 3 con la [Directiva del ciclo de vida de soporte técnico de Microsoft](http://aka.ms/MicrosoftSupportLifecycle).  Las aplicaciones WF3 existentes se ejecutarán sin problema en .NET 4.5, y [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] admitirá nuevas y existentes soluciones basadas en WF3.  
  
 Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.  
  
 Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en los artículos de MSDN sobre [Orientación de migración de flujo de trabajo 4](http://aka.ms/WF4MigrationGuidance) y en el [Kit de migración de WF 4](http://aka.ms/WF4MigrationKit) en el [WF Codeplex](http://aka.ms/WFCodeplex).