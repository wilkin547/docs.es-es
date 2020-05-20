---
title: Conceptos fundamentales de Windows Workflow
description: En este artículo se describen algunos de los conceptos del desarrollo de flujos de trabajo en el .NET Framework 4.6.1 que pueden ser desconocidos para algunos desarrolladores.
ms.date: 03/30/2017
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
ms.openlocfilehash: 07498241280191fb62a35a559a3391f7148c05b9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419898"
---
# <a name="fundamental-windows-workflow-concepts"></a>Conceptos fundamentales de Windows Workflow
El desarrollo del flujo de trabajo en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] usa conceptos que pueden ser nuevos para algunos desarrolladores de software. En este tema se describen algunos de ellos y la forma en que se implementan.  
  
## <a name="workflows-and-activities"></a>Flujos de trabajo y actividades  
 Un flujo de trabajo es una colección estructurada de acciones que modela un proceso y cada acción en el flujo de trabajo se modela como una actividad. Un host interactúa con un flujo de trabajo mediante <xref:System.Activities.WorkflowInvoker> para invocar un flujo de trabajo como si fuera un método, <xref:System.Activities.WorkflowApplication> para el control explícito sobre la ejecución de una instancia de flujo de trabajo y <xref:System.ServiceModel.WorkflowServiceHost> para las interacciones basadas en mensajes en escenarios de varias instancias. Dado que los pasos del flujo de trabajo se definen como una jerarquía de actividades, se puede decir que la actividad de nivel superior en la jerarquía define el propio flujo de trabajo. Este modelo de jerarquía ocupa el lugar de las clases `SequentialWorkflow` y `StateMachineWorkflow` explícitas de versiones anteriores. Las actividades se desarrollan como colecciones de otras actividades (con la clase <xref:System.Activities.Activity> como base, normalmente definida con XAML) o se crean de manera personalizada mediante la clase <xref:System.Activities.CodeActivity> (que puede usar el tiempo de ejecución para tener acceso a los datos) o usando la clase <xref:System.Activities.NativeActivity>, que expone todo el tiempo de ejecución del flujo de trabajo a disposición del autor de la actividad. Las actividades desarrolladas con las clases <xref:System.Activities.CodeActivity> y <xref:System.Activities.NativeActivity> se crean con lenguajes conformes a CLR como, por ejemplo, C#.  
  
## <a name="activity-data-model"></a>Modelo de datos de actividad  
 Las actividades se almacenan y comparten datos con los tipos mostrados en la siguiente tabla.  
  
|||  
|-|-|  
|Variable|Almacena los datos en una actividad.|  
|Argumento|Mueve los datos dentro y fuera de una de una actividad.|  
|Expresión|Una actividad con un valor devuelto elevado usado en enlaces de argumento.|  
  
## <a name="workflow-runtime"></a>Tiempo de ejecución de flujo de trabajo  
 El tiempo de ejecución de flujo de trabajo es el entorno en el que los flujos de trabajo se ejecutan. <xref:System.Activities.WorkflowInvoker> es la manera más sencilla de ejecutar un flujo de trabajo. El host usa <xref:System.Activities.WorkflowInvoker> para lo siguiente:  
  
- Para invocar un flujo de trabajo de forma sincrónica.  
  
- Para proporcionar datos o recuperar las salidas de un flujo de trabajo.  
  
- Para agregar extensiones que van a usar las actividades.  
  
 <xref:System.Activities.ActivityInstance> es el proxy seguro para subprocesos que los hosts pueden usar para interactuar con el tiempo de ejecución. El host usa <xref:System.Activities.ActivityInstance> para lo siguiente:  
  
- Para adquirir una instancia creándola o cargándola desde un almacén de instancias.  
  
- Para que se le notifique sobre los eventos de ciclo de vida de la instancia.  
  
- Para controlar la ejecución del flujo de trabajo.  
  
- Para proporcionar datos o recuperar las salidas de un flujo de trabajo.  
  
- Para señalar una continuación del flujo de trabajo y pasar valores en el flujo de trabajo.  
  
- Para conservar los datos del flujo de trabajo.  
  
- Para agregar extensiones que van a usar las actividades.  
  
 Las actividades tienen acceso al entorno de tiempo de ejecución de flujo de trabajo mediante la clase derivada de <xref:System.Activities.ActivityContext> adecuada, como <xref:System.Activities.NativeActivityContext> o <xref:System.Activities.CodeActivityContext>. Usan esto para resolver argumentos y variables, para programar las actividades secundarias, y para muchos otros objetivos.  
  
## <a name="services"></a>Servicios  
 Los flujos de trabajo proporcionan una manera natural de implementar y tener acceso a servicios flojamente acoplados usando actividades de mensajería. Las actividades de mensajería se basan en WCF y son el mecanismo principal que se usa para obtener datos dentro y fuera de un flujo de trabajo. Puede componer actividades de mensajería para modelar cualquier tipo de patrón de intercambio de mensajes que desee. Para obtener más información, consulte [actividades de mensajería](../wcf/feature-details/messaging-activities.md). Los servicios de flujo de trabajo se hospedan mediante la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Para obtener más información, vea [Introducción a los servicios de flujo de trabajo de hospedaje](../wcf/feature-details/hosting-workflow-services-overview.md). Para obtener más información sobre los servicios de flujo de trabajo, vea [servicios de flujo de trabajo](../wcf/feature-details/workflow-services.md)  
  
## <a name="persistence-unloading-and-long-running-workflows"></a>Persistencia, descarga y flujos de trabajo de ejecución prolongada  
 El flujo de trabajo de Windows simplifica la creación de programas reactivos de ejecución prolongada al proporcionar:  
  
- Actividades que tienen acceso a datos externos.  
  
- La capacidad de crear objetos <xref:System.Activities.Bookmark> que un agente de escucha del host puede reanudar.  
  
- La capacidad de conservar los datos de un flujo de trabajo y descargar el flujo de trabajo, a continuación, recargue y reactive el flujo de trabajo en respuesta a la reasunción de los objetos <xref:System.Activities.Bookmark> en un flujo de trabajo determinado.  
  
 Un flujo de trabajo ejecuta continuamente las actividades hasta que no haya más que ejecutar o hasta que todas las actividades actualmente en ejecución estén esperando datos. En este último estado, el flujo de trabajo está inactivo. Es normal que un host descargue los flujos de trabajo inactivos y los recargue para continuar con la ejecución cuando llega un mensaje. <xref:System.ServiceModel.Activities.WorkflowServiceHost> proporciona la funcionalidad para esta característica y proporciona una directiva de descarga extensible. En el caso de los bloques de ejecución que usen el estado de datos volátil o datos que no se puedan conservar, una actividad puede indicar a un host que no se debería conservar mediante <xref:System.Activities.NoPersistHandle>. Un flujo de trabajo también puede conservar explícitamente sus datos en medios de almacenamiento duraderos mediante la actividad <xref:System.Activities.Statements.Persist>.
