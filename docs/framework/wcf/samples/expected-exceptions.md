---
title: "Excepciones esperadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Excepciones esperadas
Este ejemplo muestra cómo detectar las excepciones esperadas cuando se usa un cliente con tipo.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.En este ejemplo, el cliente es una aplicación de consola \(.exe\) e Internet Information Services \(IIS\) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra la detección y administración de dos tipos de excepciones esperadas que los programas correctos deben gestionar: `TimeoutException` y `CommunicationException`.  
  
 Las excepciones que se producen a partir de los métodos de comunicación en un cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] pueden ser esperadas o inesperadas.Las inesperadas incluyen errores graves como `OutOfMemoryException` y errores de programación como `ArgumentNullException` o `InvalidOperationException`.No hay normalmente ninguna manera útil de administrar errores inesperados, por lo que normalmente no debería detectarlos cuando se llama a un método de comunicación de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Las excepciones esperadas de los métodos de comunicación en el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluyen `TimeoutException`, `CommunicationException` y cualquier clase derivada de `CommunicationException`.Indican un problema durante la comunicación que se puede administrar sin ningún riesgo anulando el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y creando un informe de un error de comunicación.Dado que los factores externos pueden producir estos errores en cualquier aplicación, las aplicaciones correctas deben detectar estas excepciones y recuperarse cuando se produzcan.  
  
 Hay varias clases derivadas de `CommunicationException` que un cliente puede iniciar.En algunos casos, las aplicaciones detectan también algunas de ellas para que se gestionen de forma especial, pero deja que otras las gestionen como `CommunicationException`.Esto se puede lograr detectando el tipo de excepción más concreto primero y detectando a continuación `CommunicationException` en una cláusula catch posterior.  
  
 El código que llama a un método de comunicación de cliente debe detectar `TimeoutException` y `CommunicationException`.Una manera de administrar tales errores es anular el cliente e informar del error de comunicación.  
  
```  
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 Si se produce una excepción esperada, el cliente podrá utilizarse después o no.Para determinar si el cliente todavía se puede utilizar, compruebe que la propiedad `State` sea `CommunicationState`.Opened.Si está abierta aún, se podría utilizar.De lo contrario debería anular el cliente y liberar todas las referencias a él.  
  
> [!CAUTION]
>  Puede observar que, en ocasiones, los clientes que tienen una sesión no se pueden usar después de una excepción. Los clientes que no tienen una sesión se pueden seguir usando después de una excepción.Sin embargo, no se garantiza ninguno de ellos, de manera que si intenta continuar usando el cliente después de una excepción, la aplicación debería comprobar la propiedad `State` para comprobar que el cliente sigue abierto.  
  
 Al ejecutar el ejemplo, las respuestas y excepciones de la operación se muestran en la ventana de la consola del cliente.  
  
 El proceso de cliente ejecuta dos escenarios, cada uno de los cuales intenta llamar a `Add` seguido por `Divide`.El primer escenario simula un problema de la red anulando el cliente antes de realizar la llamada a `Divide`.El segundo escenario produce una condición de tiempo de espera agotado definiendo un tiempo de espera demasiado corto para que el método pueda completarse.El resultado esperado del proceso de cliente es:  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
## Vea también