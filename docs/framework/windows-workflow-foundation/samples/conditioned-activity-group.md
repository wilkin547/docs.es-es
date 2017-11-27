---
title: Grupo de actividad condicionado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab8f47601f84267d1ac357b313fa5d2215a586d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conditioned-activity-group"></a>Grupo de actividad condicionado
En el ejemplo se muestra una aplicación de reservas de viajes. La actividad <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) tiene dos actividades de código: una actividad Car y una actividad Airline. En el constructor `SimpleCAGWorkflow`, el objeto de ArrayList "travelNeedType" se rellena con los tipos de reserva de viajes que se requieren. Si se escribe un comentario en una de las instrucciones `travelNeeds.Add`, o en las dos, se modifica el comportamiento de CAG en consecuencia. Las actividades Car y Airline tienen la condición <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> con detalles de <xref:System.Workflow.Activities.CodeCondition>. La actividad Car solo se ejecuta si la colección `travelNeeds` tiene una entrada `TravelNeeds.Car`, y la actividad Airline solo se ejecuta si la colección `travelNeeds` tiene una entrada `TravelNeeds.Airline`.  
  
 La ejecución de cada actividad quita la entrada correspondiente de la colección. La condición <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> predeterminada especifica que CAG se debe cerrar cuando no se está ejecutando ningún elemento secundario ni están listos para la ejecución (en función de sus condiciones <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>). En este ejemplo, esto significa que CAG se cierra cuando la colección `travelNeeds` está vacía.  
  
### <a name="to-build-the-sample"></a>Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta SimpleCAG\bin\debug (o la carpeta SimpleCAG\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
