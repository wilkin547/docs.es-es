---
title: Flujo de la transacción WS
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 781934e9ab27f761e71841c2edc509f9b8022aa7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094753"
---
# <a name="ws-transaction-flow"></a>Flujo de la transacción WS
Este ejemplo muestra el uso de una transacción coordinada por cliente y las opciones de servidor y cliente para el flujo de la transacción utilizando la Transacción atómica del WS o el protocolo OleTransactions. Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora, pero las operaciones se atribuyen para mostrar el uso de la `TransactionFlowAttribute` con la enumeración **TransactionFlowOption** para determinar en qué grado se habilita el flujo de transacciones. Dentro del ámbito de la transacción fluida, un registro de las operaciones solicitadas se escribe a una base de datos y se conserva hasta que la transacción coordinada por el cliente se ha completado - si la transacción del cliente no se completa, la transacción del Servicio Web se asegura de que no se confirmen las actualizaciones adecuadas a la base de datos.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Después de iniciar una conexión al servicio y una transacción, el cliente tiene acceso a varias operaciones del servicio. El contrato para el servicio se define como sigue con cada una de las operaciones que muestran un valor diferente para `TransactionFlowOption`:  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);   
}  
```

 Esto define las operaciones en el orden que serán procesadas:  
  
- Una solicitud de operación `Add` debe incluir una transacción fluida.  
  
- Una solicitud de operación `Subtract` puede incluir una transacción fluida.  
  
- Una solicitud de operación `Multiply` no debe incluir una transacción fluida a través del valor NotAllowed explícito.  
  
- Una solicitud de operación `Divide` no debe incluir una transacción fluida a través de la omisión de un atributo `TransactionFlow`.  
  
 Para habilitar el flujo de la transacción, se deben usar los enlaces con la propiedad [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) , además de los atributos de operación adecuados. En este ejemplo, la configuración del servicio expone un punto de conexión del TCP y un punto de conexión HTTP además del punto de conexión de intercambio de metadatos. El extremo TCP y el extremo HTTP usan los siguientes enlaces, que tienen habilitada la propiedad [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) .  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
> El netTcpBinding proporcionado por el sistema permite especificaciones de transactionProtocol, mientras que el wsHttpBinding proporcionado por el sistema utiliza solamente el protocolo más interoperable WSAtomicTransactionOctober2004. El protocolo OleTransactions solo está disponible para los clientes Windows Communication Foundation (WCF).  
  
 Para la clase que implementa la interfaz `ICalculator`, todos los métodos se atribuyen con propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> establecida en `true`. Este valor declara que todas las acciones tomadas dentro del método se producen dentro del ámbito de una transacción. En este caso, las acciones tomadas incluyen la grabación a la base de datos de registro. Si la solicitud de la operación incluye a continuación una transacción fluida las acciones se producen dentro del ámbito de la transacción entrante o se genera automáticamente un nuevo ámbito de la transacción.  
  
> [!NOTE]
> La propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> define el comportamiento local de las implementaciones de método de servicio y no define la capacidad del cliente ni el requisito para que una transacción fluya.  

```csharp
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```

 En el cliente, la configuración de `TransactionFlowOption` del servicio en las operaciones se refleja en la definición generada del cliente de la interfaz `ICalculator`. Asimismo, la configuración de propiedades del servicio `transactionFlow` se refleja en la configuración de la aplicación del cliente. El cliente puede seleccionar el transporte y el protocolo seleccionando el `endpointConfigurationName` adecuado:  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> El comportamiento observado de este ejemplo es el mismo, independientemente de qué protocolo o transporte se elige.  
  
 Habiendo iniciado la conexión al servicio, el cliente crea un nuevo `TransactionScope` alrededor de las llamadas a las operaciones del servicio.  

```csharp
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```

 Las llamadas a las operaciones son como sigue:  
  
- La solicitud `Add` provoca que la transacción necesaria fluya hasta al servicio y las acciones del servicio se producen dentro del ámbito de la transacción del cliente.  
  
- La primera solicitud `Subtract` también fluye la transacción permitida hacia el servicio y de nuevo las acciones del servicio se producen dentro del ámbito de la transacción del cliente.  
  
- La segunda solicitud `Subtract` se realiza dentro de un nuevo ámbito de la transacción declarado con la opción `TransactionScopeOption.Suppress`. Esto suprime la transacción exterior inicial del cliente y la solicitud no fluye hasta una transacción al servicio. Este enfoque permite a un cliente cancelar explícitamente una suscripción y protegerse contra el fluir de una transacción a un servicio cuando no es necesario. Las acciones del servicio se producen dentro del ámbito de una transacción nueva y no conectada.  
  
- La solicitud `Multiply` no fluye una transacción al servicio porque la definición generada del cliente de la interfaz `ICalculator` incluye un conjunto <xref:System.ServiceModel.TransactionFlowAttribute> establecido como <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.  
  
- La solicitud `Divide` no fluye una transacción al servicio porque, de nuevo, la definición de la interfaz `ICalculator` generada del cliente, no incluye un `TransactionFlowAttribute`. Las acciones del servicio se producen de nuevo dentro del ámbito de otra transacción nueva y no conectada.  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 El registro de las solicitudes de operación de servicio se muestra en la ventana de la consola del servicio. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 Después de una ejecución correcta, el ámbito de la transacción del cliente se completa y se confirman todas las acciones tomadas dentro de ese ámbito. Específicamente, los 5 registros nombrados se conservan en la base de datos del servicio. Los 2 primeros de éstos se han producido dentro del ámbito de la transacción del cliente.  
  
 Si se produce una excepción en cualquier parte dentro del `TransactionScope` del cliente, la transacción no puede completarse. Esto produce que los registros registrados dentro de ese ámbito no se confirmen en la base de datos. Este efecto se puede observar repitiendo el ejemplo ejecutado después de marcar como comentario la llamada para completar el `TransactionScope` exterior. En este tipo de procesos, solo se registran las tres últimas acciones (desde la segunda solicitud `Subtract`, `Multiply` y `Divide`) porque la transacción del cliente no fluyó hacia ellas.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Para compilar C# o Visual Basic versión .net de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2. Asegúrese de que se ha instalado SQL Server Express Edition o SQL Server, y que la cadena de conexión se ha establecido correctamente en el archivo de configuración de la aplicación del servicio. Para ejecutar el ejemplo sin utilizar una base de datos, establezca el valor `usingSql` en el archivo de configuración de la aplicación del servicio en `false`  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Para una configuración de varios equipos, habilite el Coordinador de transacciones distribuidas mediante las instrucciones siguientes, y utilice la herramienta WsatConfig.exe de Windows SDK con el fin de habilitar la compatibilidad para red de las transacciones WCF. Para obtener información sobre cómo configurar WsatConfig. exe, consulte [configuración de la compatibilidad con transacciones WS-Atomic](../feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Tanto si ejecuta el ejemplo en el mismo equipo como en equipos diferentes, debe configurar Microsoft Coordinador de transacciones distribuidas (MSDTC) para habilitar el flujo de transacciones de red y usar la herramienta WsatConfig. exe para habilitar la compatibilidad de red de las transacciones de WCF.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>Para configurar el Coordinador de transacciones distribuidas (MSDTC) con el fin de permitir la ejecución del ejemplo  
  
1. En un equipo de servicio que ejecute Windows Server 2003 o Windows XP, configure MSDTC para permitir las transacciones de red de entrada según estas instrucciones.  
  
    1. En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas**y servicios de **componentes**.  
  
    2. Expanda **servicios de componentes**. Abra la carpeta **equipos** .  
  
    3. Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.  
  
    4. En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.  
  
    5. Compruebe el **acceso a DTC desde la red** y **permita la entrada**.  
  
    6. Haga clic en **Aceptar**y, a continuación, en **sí** para reiniciar el servicio MSDTC.  
  
    7. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
2. En un equipo de servicio que ejecute Windows Server 2008 o Windows Vista, configure MSDTC para permitir las transacciones de red de entrada según estas instrucciones.  
  
    1. En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas**y servicios de **componentes**.  
  
    2. Expanda **servicios de componentes**. Abra la carpeta **equipos** . Seleccione **Coordinador de transacciones distribuidas**.  
  
    3. Haga clic con el botón secundario en **Coordinador de DTC** y seleccione **propiedades**.  
  
    4. En la pestaña **seguridad** , Active **acceso a DTC desde la red** y **permitir entrantes**.  
  
    5. Haga clic en **Aceptar**y, a continuación, en **sí** para reiniciar el servicio MSDTC.  
  
    6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3. En el equipo cliente, configure MSDTC para permitir las transacciones de red salientes:  
  
    1. En el menú **Inicio** , vaya a `Control Panel`, a continuación, a **herramientas administrativas**y a **servicios de componentes**.  
  
    2. Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.  
  
    3. En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.  
  
    4. Compruebe el **acceso a DTC desde la red** y **permita el tráfico saliente**.  
  
    5. Haga clic en **Aceptar**y, a continuación, en **sí** para reiniciar el servicio MSDTC.  
  
    6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
