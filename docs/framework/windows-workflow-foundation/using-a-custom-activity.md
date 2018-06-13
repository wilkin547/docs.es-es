---
title: Usar una actividad personalizada
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 4bd76ebb9e8a9b7c6cad48f2085ad27b2dee7450
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515515"
---
# <a name="using-a-custom-activity"></a>Usar una actividad personalizada
Las actividades que se derivan de <xref:System.Activities.Activity> o sus subclases pueden componerse en flujos de trabajo de mayor tamaño o crearse directamente en el código. En este tema se describe cómo usar las actividades personalizadas en flujos de trabajo creados en el código o en el diseñador.  
  
> [!NOTE]
>  Las actividades personalizadas que pueden usarse en el mismo proyecto en el que se definen, siempre y cuando la actividad personalizada y la actividad que lo utilice se compilan (es decir, se carga un tipo de crear instancias generadas por el proceso de compilación) si se carga la actividad de referencia dinámicamente (por ejemplo, mediante ActivityXAMLServices), a continuación, se debe colocar el ensamblado que se hace referencia en un proyecto diferente o el XAML generado por el diseñador tiene que editar manualmente para habilitar esta opción.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Usar una actividad personalizada en un proyecto de flujo de trabajo  
  
1.  Agregue una referencia del proyecto host al proyecto de biblioteca de actividades que contiene la actividad personalizada.  
  
2.  Compile la solución.  
  
3.  Para usar la actividad personalizada en el diseñador, busque la actividad personalizada en el cuadro de herramientas y arrástrela sobre la superficie del diseñador.  
  
4.  Para usar la actividad personalizada en código, agregue una instrucción Using que haga referencia al proyecto de actividad personalizada y pase una nueva instancia de la actividad a <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
