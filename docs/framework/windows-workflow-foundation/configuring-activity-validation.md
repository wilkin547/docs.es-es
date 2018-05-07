---
title: Configurar la validación de actividades
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: e6fa043e0a0a96875319d556c19ab8ee90cd2139
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-activity-validation"></a>Configurar la validación de actividades
La validación de la actividad permite a los autores y usuarios de actividades identificar y notificar los errores en la configuración de una actividad antes de su ejecución. Windows Workflow Foundation (WF) proporciona los tres tipos siguientes de validación de actividad:  
  
-   Atributos `RequiredArgument` y `OverloadGroup`.  
  
-   Validación basada en código imperativo.  
  
-   Restricciones declarativas.  
  
 Los atributos `RequiredArgument` y `OverloadGroup` indican que se requieren ciertos argumentos en una actividad. La validación imperativa basada en código proporciona un método simple para que una actividad proporcione la validación sobre sí misma. Las restricciones declarativas permiten la validación sobre la actividad y su relación con el flujo de trabajo que contiene. Si una actividad no se configura correctamente según los requisitos de validación, se devuelven los errores de validación y las advertencias. Si el flujo de trabajo que contiene se crea con el diseñador de flujo de trabajo, en el diseñador se mostrarán los errores y advertencias de validación. Si el flujo de trabajo se crea fuera del diseñador de flujo de trabajo, se devuelven errores de validación cuando se invoca el flujo de trabajo. Independientemente de cómo se cree el flujo de trabajo, nunca se permite que se ejecute un flujo de trabajo con errores de validación. En esta sección se proporciona una información general de estos tipos de validación de actividad y cómo se invoca la validación de actividad.  
  
## <a name="in-this-section"></a>En esta sección  
 [Argumentos necesarios y grupos de sobrecarga](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 Describe cómo usar los atributos `RequiredArgument` y `OverloadGroup` para proporcionar la validación.  
  
 [Validación basada en código imperativo](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 Describe cómo usar la validación basada en código para las actividades basadas en <xref:System.Activities.CodeActivity> y <xref:System.Activities.NativeActivity>.  
  
 [Restricciones declarativas](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 Describe cómo usar las restricciones declarativas para proporcionar la validación de actividad compleja.  
  
 [Invocación de la validación de actividades](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 Trata cuándo se invoca automáticamente la validación de la actividad y cómo invocarla de manera explícita.  
  
## <a name="reference"></a>Referencia  
  
## <a name="related-sections"></a>Secciones relacionadas
