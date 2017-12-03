---
title: "Suprimir el ámbito de transacción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9fb46dfee70cdcf136578a32709f3ceddddbeb81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="suppress-transaction-scope"></a>Suprimir el ámbito de transacción
El ejemplo muestra cómo crear una actividad `SuppressTransactionScope` personalizada para suprimir la transacción en tiempo de ejecución ambiente, si está presente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 La actividad personalizada es útil para evitar el flujo de una transacción a otro servicio si el flujo de la transacción no resulta deseable para el escenario determinado. El tiempo de ejecución de flujo de trabajo dispone de compatibilidad integrada para suprimir la transacción ambiente en la clase <xref:System.Activities.NativeActivity>, pero para utilizar esta compatibilidad es necesario crear una clase <xref:System.Activities.NativeActivity> personalizada como la de este ejemplo.  
  
 El escenario consta de tres partes. Primero, una clase <xref:System.Activities.Statements.TransactionScope> crea una transacción en tiempo de ejecución que se convierte en transacción ambiente. Esto se comprueba mediante una actividad personalizada que imprime los identificadores local y distribuido de la transacción. A continuación, la transacción fluye a un servicio remoto antes de comenzar la segunda parte. Durante la segunda parte, el flujo de trabajo entra en una actividad `SuppressTransactionScope` y de nuevo repite el proceso de imprimir los identificadores de transacción y hacer fluir la transacción. Sin embargo, la actividad personalizada no encuentra una transacción ambiente y el mensaje que fluyó al servicio no contiene la transacción. Como resultado, el servicio crea una transacción, lo que significa que el identificador distribuido impreso en el cliente y el servicio no coinciden. La parte final se produce después de salir de `SuppressTransactionScope` cuando la transacción en tiempo de ejecución se convierte en transacción ambiente tal como lo comprueba otro mensaje al servicio con un identificador distribuido que coincide con el identificador del primer mensaje.  
  
 La propia actividad deriva de <xref:System.Activities.NativeActivity> porque debe programar una actividad secundaria y agregar una propiedad de ejecución. La actividad `SuppressTransactionScope` tiene una clase <xref:System.Activities.Variable> de tipo <xref:System.Activities.RuntimeTransactionHandle>, que se debe utilizar en lugar de un campo de instancia de tipo <xref:System.Activities.RuntimeTransactionHandle> porque se debe inicializar el controlador. `Variable<RuntimeTransactionHandle>` se agrega a los metadatos de la actividad como una variable de implementación porque solo se utiliza internamente.  
  
 Cuando se ejecuta la actividad, en primer lugar comprueba si se especificó un cuerpo y en ese caso, establece la propiedad `SuppressTransaction` de la clase <xref:System.Activities.RuntimeTransactionHandle>. Una vez establecida la propiedad, se agrega a las propiedades de ejecución y se convierte en ambiente. Esto significa que cualquier actividad que sea un elemento secundario de `SuppressTransactionScope` puede ver la propiedad y por consiguiente exige la supresión de la transacción en tiempo de ejecución y hace que una clase <xref:System.Activities.Statements.TransactionScope> anidada produzca una excepción. Una vez agregado el controlador a las propiedades de ejecución, se programa la ejecución del cuerpo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución SuppressTransactionScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
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
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`