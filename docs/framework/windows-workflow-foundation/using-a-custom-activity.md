---
title: Usar una actividad personalizada
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 43addd4e69b7f7ac3ac5cd8e5bcd41397d8f0a67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293330"
---
# <a name="using-a-custom-activity"></a>Usar una actividad personalizada

Las actividades que se derivan de <xref:System.Activities.Activity> o sus subclases pueden componerse en flujos de trabajo de mayor tamaño o crearse directamente en el código. En este tema se describe cómo usar las actividades personalizadas en flujos de trabajo creados en el código o en el diseñador.  
  
> [!NOTE]
> Las actividades personalizadas se pueden usar en el mismo proyecto en el que se definen, siempre que se compilen la actividad personalizada y la actividad que la usa (es decir, que se carguen mediante un tipo de creación de instancias generado por el proceso de compilación) si la actividad de referencia se carga dinámicamente (por ejemplo, mediante ActivityXAMLServices), el ensamblado al que se hace referencia debe colocarse o el XAML generado por el diseñador debe editarse manualmente para habilitarlo.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Usar una actividad personalizada en un proyecto de flujo de trabajo  
  
1. Agregue una referencia del proyecto host al proyecto de biblioteca de actividades que contiene la actividad personalizada.  
  
2. Compile la solución.  
  
3. Para usar la actividad personalizada en el diseñador, busque la actividad personalizada en el cuadro de herramientas y arrástrela sobre la superficie del diseñador.  
  
4. Para usar la actividad personalizada en código, agregue una instrucción Using que haga referencia al proyecto de actividad personalizada y pase una nueva instancia de la actividad a <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
