---
title: Evitar problemas mediante una declaración de instrucción
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd3065a21c1714b0643bfb87b731193d3367352f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="avoiding-problems-with-the-using-statement"></a>Evitar problemas mediante una declaración de instrucción
Este ejemplo muestra cómo no debería utilizar el C# "utilizando" la instrucción para limpiar automáticamente los recursos al utilizar un cliente especificado. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora. En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra dos de los problemas comunes que se producen al utilizar el C# "utilizando" la instrucción con clientes escritos a máquina, así como el código que limpia correctamente después de las excepciones.  
  
 La instrucción C# "utilizando" resulta en una llamada a `Dispose`(). Esto es igual que `Close`(), que puede producir las excepciones cuando se produce un error en la red. Dado que la llamada a `Dispose`() ocurre implícitamente en la llave de cierre del bloque "utilizando", es probable que este origen de excepciones pase inadvertido a las personas que escriben el código y a las que leen el código. Esto representa un origen potencial de errores de aplicación.  
  
 El primer problema, mostrado en el método `DemonstrateProblemUsingCanThrow`, es que la llave de cierre inicia una excepción y el código no se ejecuta después de que la llave se cierre:  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 Aun cuando nada dentro del bloque que se está utilizando produzca una excepción , o aunque todas las excepciones dentro del bloque que está siendo utilizando la detecten, `Console.Writeline` no podrían ocurrir porque la llamada implícita `Dispose`a la llave de cierre podría producir una excepción.  
  
 El segundo problema, mostrado en el método `DemonstrateProblemUsingCanThrowAndMask`, es que otra implicación de la llave de cierre produzca una excepción:  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 Dado que `Dispose`() se produce dentro de un bloque "finalmente", el `ApplicationException` nunca se ve fuera del bloque que se está utilizando si se produce un error `Dispose`() . Si el código fuera de debe conocer sobre cuando `ApplicationException` produce, la construcción "utilizando" puede producir los problemas enmascarando esta excepción.  
  
 Finalmente, el ejemplo muestra correctamente cómo limpiar cuando se producen excepciones en `DemonstrateCleanupWithExceptions`. Esto utiliza un bloque prueba try/catch para crear informes errores y llamar`Abort`. Consulte la [espera excepciones](../../../../docs/framework/wcf/samples/expected-exceptions.md) ejemplo para obtener más información acerca de cómo detectar excepciones de las llamadas de cliente.  
  
```csharp   
try  
{  
    ...  
    client.Close();  
}  
catch (CommunicationException e)  
{  
    ...  
    client.Abort();  
}  
catch (TimeoutException e)  
{  
    ...  
    client.Abort();  
}  
catch (Exception e)  
{  
    ...  
    client.Abort();  
    throw;  
}  
```  
  
> [!NOTE]
>  La instrucción en uso y ServiceHost: Muchas aplicaciones hospedadas en sí mismas hacen poco más que hospedar un servicio y ServiceHost.Close raramente produce una excepción, por lo que tales aplicaciones pueden utilizar sin ningún riesgo la instrucción en uso con ServiceHost. Sin embargo, sea consciente que ServiceHost.Close puede iniciar una`CommunicationException`, por lo que si su aplicación continúa después de cerrar ServiceHost, debería evitar la instrucción en uso y seguir el patrón previamente proporcionado.  
  
 Al ejecutar el ejemplo, las respuestas y excepciones de la operación se muestran en la ventana de la consola del cliente.  
  
 El proceso de cliente ejecuta tres escenarios, cada uno de los cuales intentan llamar `Divide`. El primer escenario muestra un código que está omitido debido a una excepción de `Dispose`(). El segundo escenario muestra una excepción importante enmascarándose debido a una excepción de `Dispose`(). El tercer escenario muestra el proceso de limpieza correcto.  
  
 El resultado esperado del proceso de cliente es:  
  
```  
=  
= Demonstrating problem:  closing brace of using statement can throw.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating cleanup with Exceptions.  
=  
Calling client.Add(0.0, 0.0);  
        client.Add(0.0, 0.0); returned 0  
Calling client.Divide(0.0, 0.0);  
Got System.ServiceModel.CommunicationException from Divide.  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## <a name="see-also"></a>Vea también
