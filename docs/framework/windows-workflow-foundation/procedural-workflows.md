---
title: Flujos de trabajo de procedimiento
description: En Workflow Foundation, los flujos de trabajo de procedimientos usan métodos de control de flujo similares a los que se encuentran en los lenguajes de procedimientos.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 97664c1352928e7d05c2ed15fc118dd21474cfc3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421441"
---
# <a name="procedural-workflows"></a>Flujos de trabajo de procedimiento
Los flujos de trabajo de procedimiento usan métodos de control de flujo similares a los que se encuentren en lenguajes de procedimiento. Estas construcciones incluyen `While` y `If`. Estos flujos de trabajo se pueden crear libremente con otras actividades de control de flujo como <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Controlar el flujo de ejecución  
 La biblioteca de actividades del flujo de trabajo tiene actividades para modelar la mayoría de los métodos de control de flujo usados en lenguajes de procedimientos. Estas incluyen:  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Para usar las actividades de control de flujo, arrástrelas y colóquelas desde el cuadro de herramientas de **actividad** en una actividad compuesta dentro de la ventana del diseñador.  
  
> [!NOTE]
> Si usa las características de hospedaje de Windows Server AppFabric para hospedar flujos de trabajo en una granja de servidores Web, AppFabric moverá las instancias entre diferentes servidores de AppFabric. Esto necesita que los recursos se puedan compartir entre todos los nodos.  Ninguna de las actividades de flujo de trabajo predeterminadas de .NET 4 contiene ninguna operación que tenga acceso a recursos locales. Puesto que AppFabric no ofrece ningún mecanismo para marcar un flujo de trabajo como inamovible, un desarrollador no debe crear actividades personalizadas que produzcan errores cuando se mueva un flujo de trabajo.  
  
## <a name="see-also"></a>Consulta también

- [Flujos de trabajo del diagrama de flujo](flowchart-workflows.md)
