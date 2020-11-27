---
title: Opciones de creación de actividades en WF
ms.date: 03/30/2017
ms.assetid: b9061f5f-12c3-47f0-adbe-1330e2714c94
ms.openlocfilehash: e80750b3865a21d072f45b0245ae114660012e66
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289209"
---
# <a name="activity-authoring-options-in-wf"></a>Opciones de creación de actividades en WF

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias opciones para crear actividades personalizadas. El método correcto que usar para crear una actividad determinada depende de las características en tiempo de ejecución que se requieran.  
  
## <a name="deciding-which-base-activity-class-to-use-for-authoring-custom-activities"></a>Decidir qué clase base de actividad usar para crear actividades personalizadas  

 En la siguiente tabla se muestran las características disponibles en las clases base de actividad personalizadas.  
  
|Clase base de actividad|Características disponibles|  
|-------------------------|------------------------|  
|<xref:System.Activities.Activity>|Crea grupos de actividades proporcionadas por el sistema y personalizadas en una actividad compuesta.|  
|<xref:System.Activities.CodeActivity>|Implementa la funcionalidad imperativa proporcionando un método <xref:System.Activities.CodeActivity%601.Execute%2A> que se puede invalidar. También proporciona acceso a seguimiento, variables y argumentos.|  
|<xref:System.Activities.NativeActivity>|Proporciona todas las características de <xref:System.Activities.CodeActivity>, además de anular la ejecución de actividades, cancelar la ejecución de actividades secundarias, usar marcadores y programar actividades, acciones de actividad y funciones.|  
|<xref:System.Activities.DynamicActivity>|Proporciona un enfoque de tipo DOM para construir actividades que interactúen con el diseñador WF y la maquinaria en tiempo de ejecución a través de <xref:System.ComponentModel.ICustomTypeDescriptor>, con lo que se permite la creación de nuevas actividades sin definir nuevos tipos.|  
  
## <a name="authoring-activities-using-activity"></a>Crear actividades mediante la actividad  

 Las actividades que se derivan de <xref:System.Activities.Activity> crean la funcionalidad ensamblando otras actividades existentes. Estas actividades pueden ser actividades personalizadas existentes y actividades de la biblioteca de actividades de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]. Ensamblar estas actividades es la manera más básica de crear la funcionalidad personalizada. Lo normal es que se use este enfoque cuando se trata de un entorno de diseño visual para crear flujos de trabajo.  
  
## <a name="authoring-activities-using-codeactivity-or-asynccodeactivity"></a>Crear actividades mediante CodeActivity o AsyncCodeActivity  

 Las actividades que se derivan de <xref:System.Activities.CodeActivity> o <xref:System.Activities.AsyncCodeActivity>pueden implementar la funcionalidad imperativa invalidando el método <xref:System.Activities.CodeActivity%601.Execute%2A> con código imperativo personalizado. Se ejecuta el código personalizado cuando el tiempo de ejecución ejecuta la actividad. Aunque las actividades creadas de esta forma tienen acceso a la funcionalidad personalizada, no tienen acceso a todas las características del tiempo de ejecución, como el acceso total al entorno de ejecución, la posibilidad de programar actividades secundarias, la creación de marcadores o compatibilidad con un método Abort o Cancel. Cuando <xref:System.Activities.CodeActivity> se ejecuta, tiene acceso a una versión reducida del entorno de ejecución (a través de la clase <xref:System.Activities.CodeActivityContext> o <xref:System.Activities.AsyncCodeActivityContext>). Las actividades creadas usando <xref:System.Activities.CodeActivity> tienen acceso al argumento y la resolución de variables, extensiones y seguimiento. La programación de la actividad asincrónica se puede hacer mediante <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="authoring-activities-using-nativeactivity"></a>Crear actividades mediante NativeActivity  

 Las actividades que deriven de <xref:System.Activities.NativeActivity>, como aquéllas que derivan de <xref:System.Activities.CodeActivity>, crean la funcionalidad imperativa invalidando <xref:System.Activities.NativeActivity.Execute%2A>, pero también tienen acceso a toda la funcionalidad del tiempo de ejecución del flujo de trabajo a través de <xref:System.Activities.NativeActivityContext> que se transfiere al método <xref:System.Activities.NativeActivity.Execute%2A>. Este contexto admite programar y cancelar actividades secundarias, ejecutar objetos <xref:System.Activities.ActivityAction> y <xref:System.Activities.ActivityFunc%601>, hacer fluir transacciones en un flujo de trabajo, invocar procesos asincrónicos, cancelar y anular la ejecución, tener acceso a propiedades y extensiones de ejecución, y marcadores (controladores para reanudar flujos de trabajo en pausa).  
  
## <a name="authoring-activities-using-dynamicactivity"></a>Crear actividades mediante DynamicActivity  

 A diferencia de los otros tres tipos de actividad, la nueva funcionalidad no se crea derivando los nuevos tipos de <xref:System.Activities.DynamicActivity> (la clase está sellada) sino ensamblando la funcionalidad en las propiedades <xref:System.Activities.DynamicActivity.Properties%2A> y <xref:System.Activities.DynamicActivity.Implementation%2A> mediante el uso de un modelo de objeto de documento (DOM) de actividad.  
  
## <a name="authoring-activities-that-return-a-result"></a>Crear actividades que devuelven un resultado  

 Muchas actividades deben devolver un resultado después de su ejecución. Aunque siempre es posible definir una clase <xref:System.Activities.OutArgument%601> personalizada en una actividad para este propósito, se aconseja usar en su lugar <xref:System.Activities.Activity%601> o derivar de <xref:System.Activities.CodeActivity%601> o <xref:System.Activities.NativeActivity%601>. Cada una de estas clases base tiene un resultado denominado <xref:System.Activities.OutArgument%601> que su actividad puede usar para el valor de devolución. Las actividades que devuelven un resultado se deben usar únicamente si solo se necesita devolver un resultado desde una actividad; si se necesita devolver múltiples resultados, se deben usar miembros de <xref:System.Activities.OutArgument%601> diferentes en su lugar.
