---
description: Más información acerca de cómo usar las actividades de WF .NET Framework 3,0 en .NET Framework 4 con la actividad Interop
title: Usar actividades de WF de .NET Framework 3.0 en .NET Framework 4 con la actividad Interop
ms.date: 03/30/2017
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
ms.openlocfilehash: 8a91e9488b9885682d2d46f7b6afd512700157d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720116"
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>Usar actividades de WF de .NET Framework 3.0 en .NET Framework 4 con la actividad Interop

La <xref:System.Activities.Statements.Interop> actividad es una [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] actividad (WF 4,5) que contiene una actividad .NET Framework 3,5 (WF 3,5) dentro de un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo. La actividad WF 3 puede ser una actividad de hoja única o un árbol completo de actividades. La ejecución (incluida la cancelación y el control de excepciones) y la persistencia de la actividad .NET Framework 3,5 se producen dentro del contexto de la [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] instancia de flujo de trabajo que se está ejecutando.  
  
> [!NOTE]
> La <xref:System.Activities.Statements.Interop> actividad no aparece en el cuadro de herramientas del diseñador de flujo de trabajo a menos que el proyecto del flujo de trabajo tenga la configuración de la **plataforma de destino** establecida en **.NET Framework 4,5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Criterios para usar una actividad WF 3 con una actividad de interoperabilidad  

 Para ejecutar una actividad WF3 dentro de una actividad <xref:System.Activities.Statements.Interop>, se deben cumplir los siguientes criterios:  
  
- La actividad WF 3 debe derivarse de <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType>.  
  
- La actividad WF 3 debe declararse como `public` y no ser `abstract`.  
  
- La actividad WF 3 debe tener un constructor sin parámetros público.  
  
- Debido a las limitaciones en los tipos de interfaz que la actividad <xref:System.Activities.Statements.Interop> puede admitir, <xref:System.Workflow.Activities.HandleExternalEventActivity> y <xref:System.Workflow.Activities.CallExternalMethodActivity> no se pueden usar directamente, aunque se pueden usar actividades derivativas creadas con la herramienta de actividad de comunicación de flujo de trabajo (WCA.exe). Consulte [herramientas de Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms734408(v=vs.90)) para obtener más información.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Configurar una actividad WF 3 dentro de una actividad de interoperabilidad  

 Para configurar y pasar datos dentro y fuera de una actividad WF 3 (a través del límite de interoperabilidad), la actividad <xref:System.Activities.Statements.Interop> expone las propiedades de los metadatos y de la actividad WF 3. Las propiedades de metadatos de la actividad WF 3 (como <xref:System.Workflow.ComponentModel.Activity.Name%2A>) se exponen a través de la colección de <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A>. Se trata de una colección de valores nombre-valor que se usa para definir los valores para las propiedades de metadatos de la actividad WF 3. Una propiedad de metadatos es una propiedad respaldada por la propiedad de dependencia para la que se define la marca <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata>.  
  
 Las propiedades de la actividad WF 3 se exponen mediante la colección de <xref:System.Activities.Statements.Interop.ActivityProperties%2A>. Se trata de un conjunto de pares nombre-valor, en el que cada valor es un objeto <xref:System.Activities.Argument> que se usa para definir los argumentos para las propiedades de la actividad WF 3. Dado que no se puede inferir la dirección de una propiedad de actividad de WF 3, todas las propiedades se muestran como un <xref:System.Activities.InArgument> / <xref:System.Activities.OutArgument> par. Dependiendo del uso de la actividad de la propiedad, es posible que desee proporcionar una entrada <xref:System.Activities.InArgument>, una entrada <xref:System.Activities.OutArgument> o ambas. El nombre que se espera para la entrada <xref:System.Activities.InArgument> en la colección es el nombre de la propiedad tal y como se define en la actividad WF 3. El nombre esperado de la <xref:System.Activities.OutArgument> entrada en la colección es una concatenación del nombre de la propiedad y la cadena "out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Limitaciones de usar una actividad WF 3 dentro de una actividad de interoperabilidad  

 Las actividades WF 3 proporcionadas por el sistema no se pueden encapsular en una actividad <xref:System.Activities.Statements.Interop>. Para algunas actividades WF 3, como <xref:System.Workflow.Activities.DelayActivity>, esto se debe a que hay una actividad WF 4.5 análoga. En otros casos, esto se debe a que no se admite la funcionalidad de la actividad. Se pueden usar muchas actividades proporcionadas por el sistema WF 3 dentro de los flujos de trabajo encapsulados por la actividad <xref:System.Activities.Statements.Interop>, aunque sujetas a las siguientes restricciones:  
  
1. No se puede usar <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive> en una actividad <xref:System.Activities.Statements.Interop>.  
  
2. No se pueden usar <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity> y <xref:System.Workflow.Activities.WebServiceFaultActivity> en una actividad <xref:System.Activities.Statements.Interop>.  
  
3. No se puede usar <xref:System.Workflow.Activities.InvokeWorkflowActivity> en una actividad <xref:System.Activities.Statements.Interop>.  
  
4. No se puede usar <xref:System.Workflow.ComponentModel.SuspendActivity> en una actividad <xref:System.Activities.Statements.Interop>.  
  
5. Las actividades relacionadas con la compensación no se pueden usar dentro de una actividad <xref:System.Activities.Statements.Interop>.  
  
 Hay también algunas características de comportamiento que entender según el uso de las actividades WF 3 dentro de la actividad <xref:System.Activities.Statements.Interop>:  
  
1. Las actividades WF 3 incluidas en una actividad <xref:System.Activities.Statements.Interop> se inicializan cuando se ejecuta la actividad <xref:System.Activities.Statements.Interop>. En WF 4.5 no hay ninguna fase de inicialización para una instancia de flujo de trabajo antes de su ejecución.  
  
2. El runtime de WF 4.5 no controla el estado de la instancia de flujo de trabajo cuando comienza una transacción, independientemente del lugar donde empiece (dentro o fuera de una actividad <xref:System.Activities.Statements.Interop> ).  
  
3. Los registros de seguimiento de WF 3 para las actividades dentro de una actividad <xref:System.Activities.Statements.Interop> se proporcionan a los participantes de seguimiento de WF 4.5 como objetos <xref:System.Activities.Tracking.InteropTrackingRecord>. <xref:System.Activities.Tracking.InteropTrackingRecord> es un derivado de <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4. Una actividad personalizada WF 3 puede tener acceso a los datos usando las colas del flujo de trabajo incluidas en el entorno de interoperación exactamente de la misma manera que dentro del tiempo de ejecución del flujo de trabajo de WF 3. No se requiere ningún cambio en el código de actividad personalizado. En el host, los datos son colocan en una cola de flujo de trabajo de WF 3 al reanudar <xref:System.Activities.Bookmark>. El nombre del marcador es la forma de la cadena del nombre de la cola de flujo de trabajo <xref:System.IComparable>.
