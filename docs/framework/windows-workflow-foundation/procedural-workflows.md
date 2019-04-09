---
title: Flujos de trabajo de procedimiento
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 05942418038ca4349e32973aeefdfc4a50e49f46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164754"
---
# <a name="procedural-workflows"></a>Flujos de trabajo de procedimiento
Los flujos de trabajo de procedimiento usan métodos de control de flujo similares a los que se encuentren en lenguajes de procedimiento. Estas construcciones incluyen `While` y `If`. Estos flujos de trabajo se pueden crear libremente con otras actividades de control de flujo como <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Controlar el flujo de ejecución  
 La biblioteca de actividades del flujo de trabajo tiene actividades para modelar la mayoría de los métodos de control de flujo usados en lenguajes de procedimientos. Se incluyen los siguientes:  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 Para usar actividades de flujo de control, arrastrar y colocar desde el **actividad** cuadro de herramientas en una actividad compuesta dentro de la ventana del diseñador.  
  
> [!NOTE]
>  Si se usa [!INCLUDE[dublin](../../../includes/dublin-md.md)] para hospedar flujos de trabajo en una granja de servidores web, AppFabric moverá instancias entre diferentes servidores de AppFabric. Esto necesita que los recursos se puedan compartir entre todos los nodos.  Ninguna de las actividades de flujo de trabajo predeterminadas de .NET 4 contiene ninguna operación que tenga acceso a recursos locales. Puesto que AppFabric no ofrece ningún mecanismo para marcar un flujo de trabajo como inamovible, un desarrollador no debe crear actividades personalizadas que produzcan errores cuando se mueva un flujo de trabajo.  
  
## <a name="see-also"></a>Vea también

- [Flujos de trabajo del diagrama de flujo](flowchart-workflows.md)
