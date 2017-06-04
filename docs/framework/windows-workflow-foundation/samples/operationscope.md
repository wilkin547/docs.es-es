---
title: "OperationScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OperationScope
En este ejemplo se muestra cómo las actividades de mensajería, <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>, se pueden utilizar para exponer una actividad personalizada existente como una operación en un servicio de flujo de trabajo.En este ejemplo se incluye una nueva actividad personalizada denominada `OperationScope`.Pretende facilitar el desarrollo de un servicio de flujo de trabajo permitiendo a los usuarios crear el cuerpo de sus operaciones por separado como actividades personalizadas y exponiéndolas fácilmente como operaciones del servicio mediante la actividad `OperationScope`.Por ejemplo, una actividad `Add` personalizada que toma dos argumentos `in` y devuelve un argumento `out` se puede exponer como una operación `Add` en el servicio de flujo de trabajo si se coloca en una actividad `OperationScope`.  
  
 El ámbito funciona inspeccionando la actividad proporcionada como su cuerpo.Se supone que los argumentos `in` no enlazados son entradas del mensaje entrante.Se supone que todos los argumentos `out`, independientemente de si están enlazados, son salidas en el mensaje de respuesta subsiguiente.El nombre de la operación expuesta se toma del nombre para mostrar de la actividad `OperationScope`.El resultado final es que la actividad del cuerpo se incluye en las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> con los parámetros de los mensajes enlazados a los argumentos de la actividad.  
  
 En este ejemplo se expone un servicio del flujo de trabajo mediante extremos HTTP.Para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).Al ejecutar el siguiente comando en un símbolo del sistema elevado, se agregan las ACL adecuadas \(asegúrese de que %DOMAIN%\\%UserName% se reemplaza con el dominio y nombre de usuario\).  
  
 **netsh http add urlacl url\=http:\/\/\+:8000\/ user\=%DOMAIN%\\%UserName%**  
  
### Para ejecutar el ejemplo  
  
1.  Abra la solución OperationScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Establezca varios proyectos de inicio haciendo clic con el botón secundario en la solución en el Explorador de soluciones y seleccionando **Establecer proyectos de inicio**.Agregue Scenario y Scenario\_Client \(en ese orden\) como proyectos de inicio múltiples.  
  
3.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
    > [!WARNING]
    >  Este paso es necesario para ver el flujo de trabajo de BankService.xaml debido a la actividad `OperationScope` personalizada.  
  
4.  Presione CTRL\+F5 para ejecutar la aplicación.La consola de Scenario\_Client solicita las entradas; el resultado correspondiente se ve en la consola de Scenario.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`  
  
## Vea también