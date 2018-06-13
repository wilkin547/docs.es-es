---
title: Uso de TransactedReceiveScope
ms.date: 03/30/2017
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
ms.openlocfilehash: 635235504a08a151053026cf25c68750dc335eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517311"
---
# <a name="use-of-transactedreceivescope"></a>Uso de TransactedReceiveScope
En este ejemplo se muestra cómo pasar una transacción de un cliente a un servidor utilizando <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir un mensaje con una transacción de flujo y determinar la duración de la transacción en el servidor. El ejemplo consta de dos proyectos que representan los roles de cliente y servidor.  
  
## <a name="client-application"></a>Aplicación de cliente  
 La aplicación cliente ejecuta un flujo de trabajo que imprime el Id. de la transacción distribuida, envía un mensaje al servidor, pasa la transacción, recibe la respuesta, imprime de nuevo el Id. de la transacción distribuida y finaliza. Cuando el Id. de la transacción distribuida se imprime inicialmente, es un GUID vacío, puesto que la transacción es todavía solo local.  
  
## <a name="server-application"></a>Servidor de aplicaciones  
 El proyecto de servidor es similar; sin embargo, el flujo de trabajo se hospeda en <xref:System.ServiceModel.Activities.WorkflowServiceHost> porque debe realizar escuchas en un extremo del mensaje procedente del cliente. El flujo de trabajo se centra en el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, que recibe la transacción de flujo del cliente, imprime el mensaje que se envió, imprime el Id. de la transacción distribuida y envía la respuesta al cliente. El Id. de la transacción distribuida es ahora un GUID que no está vacío y si se agregara una actividad que tenga en cuenta las transacciones al cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>, se ejecutaría bajo la transacción de flujo.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución TransactedReceiveScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.  
  
3.  Una vez que la compilación finalice correctamente, haga clic en la solución y seleccione **Establecer proyectos de inicio**. En el cuadro de diálogo, seleccione **proyectos de inicio múltiples** y asegúrese de que la acción para ambos proyectos es **iniciar**.  
  
4.  Presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú. Como alternativa, puede presionar CTRL + F5 o seleccione **iniciar sin depurar** desde el **depurar** menú para ejecutarlo sin depuración.  
  
    > [!NOTE]
    >  El servidor debe estar en ejecución antes de iniciar el cliente. El resultado de la ventana de la consola que hospeda el servicio indica cuándo se ha iniciado.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`