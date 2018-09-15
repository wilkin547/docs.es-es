---
title: OperationScope
ms.date: 03/30/2017
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
ms.openlocfilehash: 562fd9c8ff964cb997012d49600bce73d4441465
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625898"
---
# <a name="operationscope"></a>OperationScope
En este ejemplo se muestra cómo las actividades de mensajería, <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>, se pueden utilizar para exponer una actividad personalizada existente como una operación en un servicio de flujo de trabajo. En este ejemplo se incluye una nueva actividad personalizada denominada `OperationScope`. Pretende facilitar el desarrollo de un servicio de flujo de trabajo permitiendo a los usuarios crear el cuerpo de sus operaciones por separado como actividades personalizadas y exponiéndolas fácilmente como operaciones del servicio mediante la actividad `OperationScope`. Por ejemplo, una actividad `Add` personalizada que toma dos argumentos `in` y devuelve un argumento `out` se puede exponer como una operación `Add` en el servicio de flujo de trabajo si se coloca en una actividad `OperationScope`.  
  
 El ámbito funciona inspeccionando la actividad proporcionada como su cuerpo. Se supone que los argumentos `in` no enlazados son entradas del mensaje entrante. Se supone que todos los argumentos `out`, independientemente de si están enlazados, son salidas en el mensaje de respuesta subsiguiente. El nombre de la operación expuesta se toma del nombre para mostrar de la actividad `OperationScope`. El resultado final es que la actividad del cuerpo se incluye en las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> con los parámetros de los mensajes enlazados a los argumentos de la actividad.  
  
 En este ejemplo se expone un servicio del flujo de trabajo mediante extremos HTTP. Para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas. Para obtener más información, consulte [configurar HTTP y HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353). El siguiente comando en un símbolo del sistema con privilegios elevados agrega las ACL adecuadas (asegúrese de que el dominio y el nombre de usuario se sustituyen por dominio %\\% UserName %).  
  
 **netsh http agregar urlacl url =http://+:8000/ usuario = % DOMAIN %\\% UserName %**  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución OperationScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Establezca varios proyectos de inicio haciendo clic en la solución en el Explorador de soluciones y seleccionar **Establecer proyectos de inicio**. Agregue Scenario y Scenario_Client (en ese orden) como proyectos de inicio múltiples.  
  
3.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
    > [!WARNING]
    >  Este paso es necesario para ver el flujo de trabajo de BankService.xaml debido a la actividad `OperationScope` personalizada.  
  
4.  Presione CTRL+F5 para ejecutar la aplicación. La consola de Scenario_Client solicita las entradas; el resultado correspondiente se ve en la consola de Scenario.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`