---
title: "Usar actividades de WF de .NET Framework 3.0 en .NET Framework 4 con la actividad Interop | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Usar actividades de WF de .NET Framework 3.0 en .NET Framework 4 con la actividad Interop
El <xref:System.Activities.Statements.Interop> actividad es un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] actividad (WF 4.5) que ajusta un [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] actividad (WF 3.5) dentro de un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo. La actividad WF 3 puede ser una actividad de hoja única o un árbol completo de actividades. La ejecución (incluso la cancelación y el control de excepciones) y la persistencia de la actividad de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] se producen en el contexto de la instancia de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] que está ejecutando.  
  
> [!NOTE]
>  El <xref:System.Activities.Statements.Interop> actividad no aparecerá en el cuadro de herramientas Diseñador de flujo de trabajo a menos que el proyecto del flujo de trabajo tiene su **.NET Framework de destino** definida en **.NET Framework 4.5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Criterios para usar una actividad WF 3 con una actividad de interoperabilidad  
 Para una actividad de WF 3 ejecutar correctamente dentro de un <xref:System.Activities.Statements.Interop> actividad, deben cumplirse los siguientes criterios:  
  
-   La actividad de WF 3 debe derivarse de <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>.  
  
-   La actividad WF 3 debe declararse como `public` y no ser `abstract`.  
  
-   La actividad WF 3 debe tener un constructor predeterminado público.  
  
-   Debido a las limitaciones de la interfaz de tipos que el <xref:System.Activities.Statements.Interop> actividad puede admitir, <xref:System.Workflow.Activities.HandleExternalEventActivity> y <xref:System.Workflow.Activities.CallExternalMethodActivity> no se pueden usadas directamente, aunque derivadas actividades creadas con la herramienta de la actividad de comunicación de flujo de trabajo (WCA.exe) pueden utilizarse. Consulte [Herramientas de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=178889) para obtener más información.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Configurar una actividad WF 3 dentro de una actividad de interoperabilidad  
 Para configurar y pasar datos dentro y fuera de una actividad WF 3 a través de los límites de interoperación, propiedades de metadatos y la actividad de WF 3 están expuestos por el <xref:System.Activities.Statements.Interop> actividad. Propiedades de metadatos de la actividad de WF 3 (como <xref:System.Workflow.ComponentModel.Activity.Name%2A>) se exponen a través de la <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A> colección. Se trata de una colección de valores nombre-valor que se usa para definir los valores para las propiedades de metadatos de la actividad WF 3. Una propiedad de metadatos es una propiedad respaldada por la propiedad de dependencia para que la <xref:System.Workflow.ComponentModel.DependencyPropertyOptions> marca está establecida.  
  
 Propiedades de la actividad de WF 3 se exponen a través de la <xref:System.Activities.Statements.Interop.ActivityProperties%2A> colección. Este es un conjunto de pares de nombre y valor, donde cada valor es un <xref:System.Activities.Argument> objeto, que se utiliza para definir los argumentos de propiedades de la actividad de WF 3. Dado que no se puede deducir la dirección de una propiedad de actividad de WF 3, cada propiedad aparece como una <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument> par. Dependiendo del uso de la actividad de la propiedad, que desee proporcionar una <xref:System.Activities.InArgument> entrada, una <xref:System.Activities.OutArgument> entrada, o ambos. El nombre que espera el <xref:System.Activities.InArgument> entrada en la colección es el nombre de la propiedad tal como se define en la actividad de WF 3. El nombre que espera el <xref:System.Activities.OutArgument> entrada en la colección es una concatenación del nombre de la propiedad y la cadena "Out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Limitaciones de usar una actividad WF 3 dentro de una actividad de interoperabilidad  
 Las actividades de WF 3 proporcionadas por el sistema no se pueden encapsular en un <xref:System.Activities.Statements.Interop> actividad. Para algunas actividades de WF 3, como <xref:System.Workflow.Activities.DelayActivity>, esto es porque hay una actividad de WF 4.5 análoga. En otros casos, esto se debe a que no se admite la funcionalidad de la actividad. Muchas actividades de WF 3 proporcionadas por el sistema se pueden utilizar dentro de flujos de trabajo ajustados por el <xref:System.Activities.Statements.Interop> actividad, las siguientes restricciones:  
  
1.  <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive> no se puede utilizar en una <xref:System.Activities.Statements.Interop> actividad.  
  
2.  <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity>, y <xref:System.Workflow.Activities.WebServiceFaultActivity> no se puede utilizar dentro de un <xref:System.Activities.Statements.Interop> actividad.  
  
3.  <xref:System.Workflow.Activities.InvokeWorkflowActivity> no se puede utilizar dentro de un <xref:System.Activities.Statements.Interop> actividad.  
  
4.  <xref:System.Workflow.ComponentModel.SuspendActivity> no se puede utilizar dentro de un <xref:System.Activities.Statements.Interop> actividad.  
  
5.  Las actividades relacionadas con la compensación no se puede utilizar dentro de un <xref:System.Activities.Statements.Interop> actividad.  
  
 También hay algunas características de comportamiento que entender acerca del uso de las actividades de WF 3 dentro de la <xref:System.Activities.Statements.Interop> actividad:  
  
1.  WF 3 actividades contenidas dentro de un <xref:System.Activities.Statements.Interop> actividad están inicializados cuando el <xref:System.Activities.Statements.Interop> se ejecuta la actividad. En WF 4.5 no hay ninguna fase de inicialización para una instancia de flujo de trabajo antes de su ejecución.  
  
2.  El tiempo de ejecución de WF 4.5 no no el estado de instancia del flujo de trabajo de punto de comprobación cuando se inicia una transacción, independientemente de donde comienza la transacción (dentro o fuera de un <xref:System.Activities.Statements.Interop> actividad).  
  
3.  Registros de seguimiento 3 de WF para las actividades dentro de un <xref:System.Activities.Statements.Interop> actividad se proporciona a los participantes del seguimiento de WF 4.5 como <xref:System.Activities.Tracking.InteropTrackingRecord> objetos. <xref:System.Activities.Tracking.InteropTrackingRecord> es un derivado de <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4.  Una actividad personalizada WF 3 puede tener acceso a los datos usando las colas del flujo de trabajo incluidas en el entorno de interoperación exactamente de la misma manera que dentro del tiempo de ejecución del flujo de trabajo de WF 3. No se requiere ningún cambio en el código de actividad personalizado. En el host, los datos son colocan en una cola del flujo de trabajo de WF 3 al reanudar un <xref:System.Activities.Bookmark>. El nombre del marcador es la forma de cadena de la <xref:System.IComparable> nombre de la cola de flujo de trabajo.  
  
## <a name="see-also"></a>Vea también  
 [Usar un .NET Framework 3.0 o .NET Framework 3.5 actividad en un flujo de trabajo de .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)