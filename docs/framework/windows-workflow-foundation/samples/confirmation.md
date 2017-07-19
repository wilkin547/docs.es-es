---
title: "Confirmaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Confirmaci&#243;n
En este ejemplo se muestran cuatro escenarios comunes en torno al uso de <xref:System.Activities.Statements.CompensableActivity> y la confirmación.En el ejemplo se ejecutan cuatro flujos de trabajo para mostrar la confirmación.Este ejemplo está disponible en versiones declarativa e imperativa.  
  
## Confirmar una actividad compensable  
 El primer flujo de trabajo muestra cómo confirmar una actividad compensable y consta de una secuencia de dos instancias de <xref:System.Activities.Statements.CompensableActivity>.Después de completar la segunda actividad <xref:System.Activities.Statements.CompensableActivity>, una actividad de confirmación confirma la primera actividad.Cuando el flujo de trabajo se completa correctamente, todas las instancias de <xref:System.Activities.Statements.CompensableActivity> que no se han confirmado ni compensado se confirman automáticamente según el orden predeterminado.Sin la confirmación, la segunda actividad <xref:System.Activities.Statements.CompensableActivity> se habría confirmado en primer lugar.  
  
## Compensación explícita  
 El segundo escenario muestra el efecto en la confirmación predeterminada cuando una actividad <xref:System.Activities.Statements.CompensableActivity> se compensa explícitamente.El flujo de trabajo está compuesto de una secuencia de dos actividades <xref:System.Activities.Statements.CompensableActivity>; cuando se completa la segunda, la primera se compensa explícitamente.Como resultado, cuando se completa el flujo de trabajo únicamente está confirmada la segunda actividad <xref:System.Activities.Statements.CompensableActivity>.  
  
## Controlar el orden de confirmación para las actividades CompensableActivity anidadas  
 En el tercer escenario se muestra cómo controlar el orden de confirmación de actividades <xref:System.Activities.Statements.CompensableActivity> anidadas.El escenario consta de una actividad <xref:System.Activities.Statements.CompensableActivity> como raíz del flujo de trabajo.El cuerpo de la actividad <xref:System.Activities.Statements.CompensableActivity> raíz es una secuencia de tres actividades <xref:System.Activities.Statements.CompensableActivity>.La propiedad <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> de la actividad <xref:System.Activities.Statements.CompensableActivity> raíz es una secuencia que especifica que se debe confirmar la primera actividad <xref:System.Activities.Statements.CompensableActivity> anidada y a continuación la segunda.Cuando el flujo de trabajo se completa, confirma la actividad <xref:System.Activities.Statements.CompensableActivity> raíz que, a continuación, confirma la primera, segunda y tercera actividad <xref:System.Activities.Statements.CompensableActivity> anidadas, en ese orden.Como resultado, el orden de confirmación predeterminado se invierte.Dado que la propiedad <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> no confirmó explícitamente la tercera actividad <xref:System.Activities.Statements.CompensableActivity> como parte de la actividad <xref:System.Activities.Statements.CompensableActivity>, se confirma según el orden predeterminado.Sin embargo, dado que es la única actividad <xref:System.Activities.Statements.CompensableActivity> sin confirmar, simplemente significa que se confirma.  
  
## Ámbito de variables  
 En el cuarto escenario se muestra cómo la duración de las variables definidas para una actividad <xref:System.Activities.Statements.CompensableActivity> o uno de sus elementos primarios todavía está dentro del ámbito cuando se ejecutan los controladores <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> o <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>aunque la actividad o el flujo de trabajo se hayan completado.El flujo de trabajo consta de una secuencia de dos actividades <xref:System.Activities.Statements.CompensableActivity>.En el cuerpo de la primera, se establece la variable `mySum` en la suma de 5 y 10 y el resultado se imprime.En el cuerpo de la segunda actividad <xref:System.Activities.Statements.CompensableActivity>, la suma se establece en la suma de la suma existente y 7, y el resultado se imprime.Para la primera actividad <xref:System.Activities.Statements.CompensableActivity> se define un controlador de confirmación personalizado, que imprime la suma, resta 7 e imprime la suma de nuevo.La inspección de las sumas impresas deja claro que la variable no solo está en el ámbito para los cuerpos de ambas actividades <xref:System.Activities.Statements.CompensableActivity>, sino también del controlador <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.  
  
#### Para ejecutar el ejemplo  
  
1.  Cargue la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Ejecute la aplicación ConfirmationSample.exe.  
  
3.  Observe el siguiente resultado:  
  
 **Explicit confirmation:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Confirmation HandlerEnd of workflowCompensableActivity2: Confirmation HandlerExplicit compensation:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Compensation HandlerEnd of workflowCompensableActivity2: Confirmation HandlerCustom confirmation handler:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd of workflowCompensableActivity1: Confirmation HandlerCompensableActivity2: Confirmation HandlerCompensableActivity3: Confirmation HandlerVariable access in a confirmation handler:Start of workflowCompensableActivity1: BodyCompensableActivity1: The sum is: 15CompensableActivity2: BodyCompensableActivity2: Adding 7 to the sumCompensableActivity2: The sum is now: 22End of workflowCompensableActivity2: Confirmation HandlerCompensableActivity1: Confirmation HandlerCompensableActivity2: The sum is: 22CompensableActivity2: After subtracting 12 the sum is now: 10Press ENTER to exit.**  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`  
  
## Vea también