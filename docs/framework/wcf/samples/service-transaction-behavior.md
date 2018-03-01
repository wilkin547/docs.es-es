---
title: "Comportamiento de transacción de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4c7c9c78b821f7457f193d24bae031d49b301ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="service-transaction-behavior"></a>Comportamiento de transacción de servicio
Este ejemplo muestra el uso de una transacción coordinada por el cliente y la configuración de ServiceBehaviorAttribute y OperationBehaviorAttribute para controlar el comportamiento de las transacciones de servicio. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora, pero se ha ampliado para mantener un registro de servidor de las operaciones realizadas en una tabla de base de datos y un con estado ejecutando total para las operaciones de cálculo. Las escrituras guardadas en la tabla de registro del servidor dependen del resultado de una transacción coordinada del cliente. Si la transacción del cliente no se completa, la transacción del servicio Web garantiza que las actualizaciones de la base de datos no se confirman.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El contrato para el servicio define que todas las operaciones exigen que una transacción fluya con solicitudes:  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",  
                    SessionMode = SessionMode.Required)]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Subtract(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Multiply(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Divide(double n);  
}  
```  
  
 Para habilitar el flujo de la transacción entrante, el servicio se configura con el wsHttpBinding proporcionado por el sistema con el atributo transactionFlow establecido en `true`. Este enlace utiliza el protocolo WSAtomicTransactionOctober2004 interoperable:  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="transactionalBinding" transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
 Después de iniciar tanto una conexión con el servicio como una transacción, el cliente tiene acceso a varias operaciones de servicio dentro del ámbito de esa transacción y, a continuación, completa la transacción y cierra la conexión:  
  
```  
// Create a client  
CalculatorClient client = new CalculatorClient();  
  
// Create a transaction scope with the default isolation level of Serializable  
using (TransactionScope tx = new TransactionScope())  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation.  
    double value = 100.00D;  
    Console.WriteLine("  Adding {0}, running total={1}",  
                                        value, client.Add(value));  
  
    // Call the Subtract service operation.  
    value = 45.00D;  
    Console.WriteLine("  Subtracting {0}, running total={1}",  
                                        value, client.Subtract(value));  
  
    // Call the Multiply service operation.  
    value = 9.00D;  
    Console.WriteLine("  Multiplying by {0}, running total={1}",  
                                        value, client.Multiply(value));  
  
    // Call the Divide service operation.  
    value = 15.00D;  
    Console.WriteLine("  Dividing by {0}, running total={1}",  
                                        value, client.Divide(value));  
  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
  
// Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
 En el servicio, hay tres atributos que afectan al comportamiento de las transacciones de servicio y lo hacen de las siguientes maneras:  
  
-   En `ServiceBehaviorAttribute`:  
  
    -   La propiedad `TransactionTimeout` especifica el período dentro del cual debe completarse una transacción. En este ejemplo, está establecido en 30 segundos.  
  
    -   La propiedad `TransactionIsolationLevel` especifica el nivel de aislamiento que el servicio admite. Esto es necesario para coincidir con el nivel de aislamiento del cliente.  
  
    -   La propiedad `ReleaseServiceInstanceOnTransactionComplete` especifica si se recicla la instancia del servicio cuando se completa una transacción. Si se establece en `false`, el servicio mantiene la misma instancia del servicio en las solicitudes de operación. Esto es necesario para mantener el total en ejecución. Si se establece en `true`, se genera una instancia nueva después de cada acción completada.  
  
    -   La propiedad `TransactionAutoCompleteOnSessionClose` especifica si se completan las transacciones pendientes cuando la sesión se cierra. Si se establece en `false`, las operaciones individuales son necesarias para establecer el `OperationBehaviorAttribute``TransactionAutoComplete` propiedad `true` o exigir explícitamente una llamada a la `SetTransactionComplete` método para realizar transacciones. Este ejemplo muestra ambos enfoques.  
  
-   En `ServiceContractAttribute`:  
  
    -   La propiedad `SessionMode` especifica si el servicio pone en correlación las solicitudes adecuadas en una sesión lógica. Dado que este servicio incluye las operaciones en las que la propiedad OperationBehaviorAttribute TransactionAutoComplete está establecida en `false` (multiplicar y dividir), debe especificarse `SessionMode.Required`. Por ejemplo, la operación de multiplicación no completa su transacción sino que confía en una llamada posterior para que se complete la operación de división usando el método `SetTransactionComplete`; el servicio debe poder determinar que estas operaciones se están produciendo dentro de la misma sesión.  
  
-   En `OperationBehaviorAttribute`:  
  
    -   La propiedad `TransactionScopeRequired` especifica si las acciones de la operación se deberían ejecutar dentro del ámbito de una transacción. Se establece en `true` para todas las operaciones de este ejemplo y, dado que el cliente fluye su transacción a todas las operaciones, las acciones se producen dentro del ámbito de la transacción de ese cliente.  
  
    -   La propiedad `TransactionAutoComplete` especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se producen excepciones no controladas. Tal y como se ha descrito previamente, se establece en `true` para las operaciones de suma y resta, y en `false` para las de multiplicación y división. Las operaciones de suma y resta completan sus acciones automáticamente, la de división completa sus acciones mediante una llamada explícita al método `SetTransactionComplete` y la de multiplicación no completa sus acciones, sino que en realidad confía y necesita una llamada posterior, por ejemplo a la operación de dividir, para completar las acciones.  
  
 La implementación del servicio con atributos es como sigue:  
  
```  
[ServiceBehavior(  
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
    TransactionTimeout = "00:00:30",  
    ReleaseServiceInstanceOnTransactionComplete = false,  
    TransactionAutoCompleteOnSessionClose = false)]  
public class CalculatorService : ICalculator  
{  
    double runningTotal;  
  
    public CalculatorService()  
    {  
        Console.WriteLine("Creating new service instance...");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Add(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));  
        runningTotal = runningTotal + n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Subtract(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));  
        runningTotal = runningTotal - n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Multiply(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal * n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Divide(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal / n;  
        OperationContext.Current.SetTransactionComplete();  
        return runningTotal;  
    }  
  
    // Logging method ommitted for brevity  
}   
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Starting transaction  
Performing calculations...  
  Adding 100, running total=100  
  Subtracting 45, running total=55  
  Multiplying by 9, running total=495  
  Dividing by 15, running total=33  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 El registro de las solicitudes de operación de servicio se muestra en la ventana de la consola del servicio. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Press <ENTER> to terminate service.  
Creating new service instance...  
  Writing row 1 to database: Adding 100 to 0  
  Writing row 2 to database: Subtracting 45 from 100  
  Writing row 3 to database: Multiplying 55 by 9  
  Writing row 4 to database: Dividing 495 by 15  
```  
  
 Tenga en cuenta que además de mantener el total en ejecución de los cálculos, el servicio informa sobre la creación de instancias (una instancia en este ejemplo) y registra las solicitudes de operación en una base de datos. Como todas las solicitudes fluyen en la transacción del cliente, cualquier error para completar esa transacción da como resultado que se reviertan todas las operaciones de la base de datos. Esto se puede demostrar de varias maneras:  
  
-   Marcar como comentario la llamada del cliente en `tx.Complete`() y volver a ejecutar. Esto ocasiona que el cliente salga del ámbito de la transacción sin completar su transacción.  
  
-   Marcar como comentario la llamada a la operación de servicio de dividir. Así se impide que la acción iniciada por la operación de multiplicación se complete y, por tanto, la transacción del cliente tampoco podrá completarse.  
  
-   Iniciar una excepción no controlada en cualquier parte del ámbito de la transacción del cliente. Del mismo modo, esto impide que el cliente complete su transacción.  
  
 El resultado en cualquiera de estos casos es que no se confirma ninguna de las operaciones realizadas dentro del ámbito y no se incrementa el recuento de filas conservadas en la base de datos.  
  
> [!NOTE]
>  Como parte del proceso de compilación, el archivo de base de datos se copia en la carpeta de la bandeja. Debe examinar esa copia del archivo de base de datos para observar las filas que se conservan en el registro en lugar del archivo que está incluido en el proyecto de Visual Studio.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha instalado SQL Server 2005 Express Edition o SQL Server 2005. En el archivo App.config del servicio, puede establecerse la base de datos`connectionString` o las interacciones de la base de datos pueden deshabilitarse estableciendo el valor `usingSql` de appSettings en `false`.  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
 Si ejecuta el ejemplo en varios equipos, debe configurar el Coordinador de transacciones distribuidas de Microsoft (MSDTC, Microsoft Distributed Transaction Coordinator) para habilitar el flujo de transacciones de red y utilizar la herramienta WsatConfig.exe para habilitar la compatibilidad de red de las transacciones de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a>Para configurar MSDTC de forma que admita la ejecución del ejemplo en varios equipos  
  
1.  En el equipo de servicio, configure MSDTC para permitir las transacciones de red entrantes.  
  
    1.  Desde el **iniciar** menú, vaya a **el Panel de Control**, a continuación, **herramientas administrativas**y, a continuación, **servicios de componentes**.  
  
    2.  Haga clic en **Mi PC** y seleccione **propiedades**.  
  
    3.  En el **MSDTC** , haga clic en **configuración de seguridad**.  
  
    4.  Comprobar **acceso a DTC desde la red** y **Permitir entrantes**.  
  
    5.  Haga clic en **Sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.  
  
    6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
2.  En el equipo de servicio y el equipo cliente, configure el Firewall de Windows para incluir Microsoft DTC (MSDTC, Coordinador de transacciones distribuidas) en la lista de aplicaciones exceptuadas:  
  
    1.  Ejecute la aplicación Firewall de Windows desde el Panel de control.  
  
    2.  Desde el **excepciones** , haga clic en **Agregar programa**.  
  
    3.  Desplácese a la carpeta C:\WINDOWS\System32.  
  
    4.  Seleccione Msdtc.exe y haga clic en **abiertos**.  
  
    5.  Haga clic en **Aceptar** para cerrar el **Agregar programa** cuadro de diálogo y haga clic en **Aceptar** otra vez para cerrar el applet del Firewall de Windows.  
  
3.  En el equipo cliente, configure MSDTC para permitir las transacciones de red salientes:  
  
    1.  Desde el **iniciar** menú, vaya a **el Panel de Control**, a continuación, **herramientas administrativas**y, a continuación, **servicios de componentes**.  
  
    2.  Haga clic en **Mi PC** y seleccione **propiedades**.  
  
    3.  En el **MSDTC** , haga clic en **configuración de seguridad**.  
  
    4.  Comprobar **acceso a DTC desde la red** y **Permitir salientes**.  
  
    5.  Haga clic en **Sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.  
  
    6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`  
  
## <a name="see-also"></a>Vea también
