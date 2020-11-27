---
title: Operaciones sincrónicas y asincrónicas
description: Obtenga información sobre cómo implementar y llamar a operaciones de servicio asincrónicas. Los servicios y clientes WCF pueden usar operaciones asincrónicas en dos niveles de la aplicación.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
ms.openlocfilehash: f14e206bb99215a7a9b2535f99feb9971274532b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254199"
---
# <a name="synchronous-and-asynchronous-operations"></a>Operaciones sincrónicas y asincrónicas

Este tema explica cómo implementar y llamar a operaciones de servicio asincrónicas.  
  
 Muchas aplicaciones llaman a métodos de forma asincrónica porque permite que la aplicación siga realizando un trabajo útil mientras la llamada al método se ejecuta. Los servicios y clientes de Windows Communication Foundation (WCF) pueden participar en llamadas de operación asincrónica en dos niveles distintos de la aplicación, que proporcionan a las aplicaciones de WCF aún más flexibilidad para maximizar el rendimiento equilibrado con interactividad.  
  
## <a name="types-of-asynchronous-operations"></a>Tipos de operaciones asincrónicas  

 Todos los contratos de servicio en WCF, independientemente de los tipos y los valores devueltos de los parámetros, usan atributos de WCF para especificar un patrón de intercambio de mensajes determinado entre el cliente y el servicio. WCF enruta automáticamente los mensajes de entrada y de salida a la operación de servicio o al código de cliente adecuado.  
  
 El cliente posee solo el contrato de servicio, que especifica el patrón de intercambio de mensajes para una operación determinada. Los clientes pueden ofrecer cualquier modelo de programación que elijan al programador, siempre y cuando se observe el patrón de intercambio de mensajes subyacente. Así, también, los servicios pueden implementar operaciones de cualquier manera, siempre que se observe el patrón del mensaje especificado.  
  
 La independencia del contrato de servicio del servicio o de la implementación del cliente habilita los formularios siguientes de ejecución asincrónica en aplicaciones de WCF:  
  
- Los clientes pueden invocar operaciones de solicitud/respuesta asincrónicamente mediante un intercambio de mensajes sincrónico.  
  
- Los servicios pueden implementar una operación de solicitud/respuesta asincrónicamente mediante un intercambio de mensajes sincrónico.  
  
- Los intercambios de mensajes pueden ser unidireccionales, sin tener en cuenta la implementación del cliente o servicio.  
  
### <a name="suggested-asynchronous-scenarios"></a>Escenarios asincrónicos sugeridos  

 Use un enfoque asincrónico en una implementación de operación de servicio si la implementación del servicio de la operación realiza una llamada en bloque, como al realizar operaciones de E/S. En una implementación de operación asincrónica, intente llamar a métodos y operaciones asincrónicos para extender la ruta de acceso de la llamada asincrónica al máximo. Por ejemplo, llame a una `BeginOperationTwo()` desde `BeginOperationOne()`.  
  
- Use un enfoque asincrónico en una aplicación de cliente o que realiza la llamada en los casos siguientes:  
  
- Si invoca operaciones desde una aplicación de nivel intermedio. (Para obtener más información acerca de estos escenarios, vea [Aplicaciones cliente de nivel intermedio](./feature-details/middle-tier-client-applications.md)).  
  
- Si invoca operaciones desde una página ASP.NET, use páginas asincrónicas.  
  
- Si invoca operaciones desde cualquier aplicación de proceso simple, como Windows Forms o Windows Presentation Foundation (WPF). Si utiliza el modelo de llamada asincrónica basado en evento, el evento resultante se genera en el proceso de interfaz de usuario, agregando capacidad de respuesta a la aplicación sin que sea necesario controlar procesos múltiples.  
  
- En general, si puede elegir entre una llamada sincrónica y una asincrónica, elija la asincrónica.  
  
### <a name="implementing-an-asynchronous-service-operation"></a>Implementar una operación de servicio asincrónica  

 Las operaciones asincrónicas se pueden implementar mediante uno de los tres métodos siguientes:  
  
1. El patrón asincrónico basado en tareas  
  
2. El patrón asincrónico basado en eventos  
  
3. El patrón asincrónico de IAsyncResult  
  
#### <a name="task-based-asynchronous-pattern"></a>Modelo asincrónico basado en tareas  

 El patrón asincrónico basado en tareas es la forma recomendada de implementar operaciones asincrónicas porque es la más sencilla. Para usar este método, implemente simplemente la operación de servicio y especifique un tipo de valor devuelto de task \<T> , donde T es el tipo devuelto por la operación lógica. Por ejemplo:  
  
```csharp  
public class SampleService:ISampleService
{
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)
   {
      return Task<string>.Factory.StartNew(() =>
      {
         return msg;
      });
   }  
   // ...  
}  
```  
  
 La operación SampleMethodTaskAsync devuelve task \<string> porque la operación lógica devuelve una cadena. Para obtener más información sobre el patrón asincrónico basado en tareas, [Información general sobre el patrón asincrónico basado en tareas](https://go.microsoft.com/fwlink/?LinkId=232504).  
  
> [!WARNING]
> Cuando se usa el patrón asincrónico basado en tareas, se puede iniciar T:System.AggregateException si se produce una excepción mientras se espera la finalización de la operación. Esta excepción puede producirse en el cliente o servicios  
  
#### <a name="event-based-asynchronous-pattern"></a>Patrón asincrónico basado en eventos  

 Todo servicio que admita el modelo asincrónico basado en eventos tendrá una o varias operaciones denominadas MethodNameAsync. Estos métodos pueden reflejar versiones sincrónicas, que desempeñan la misma operación en el subproceso actual. La clase también puede tener un evento MethodNameCompleted y un método MethodNameAsyncCancel (o simplemente CancelAsync). Un cliente que desea llamar a la operación definirá un controlador de eventos para que se llame cuando la operación se complete,  
  
 El fragmento de código siguiente muestra cómo declarar operaciones asincrónicas mediante el patrón asincrónico basado en eventos.  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 Para obtener más información sobre el modelo asincrónico basado en eventos, [Información general sobre el modelo asincrónico basado en eventos](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
#### <a name="iasyncresult-asynchronous-pattern"></a>Modelo asincrónico de IAsyncResult  

 Una operación de servicio se puede implementar de forma asincrónica mediante el .NET Framework modelo de programación asincrónico y marcando el `<Begin>` método con la <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> propiedad establecida en `true` . En este caso, la operación asincrónica se expone en metadatos de la misma manera que una operación sincrónica: se expone como una operación única con un mensaje de solicitud y un mensaje de respuesta correlativo. Los modelos de programación de cliente tienen entonces una opción. Pueden representar este patrón como una operación sincrónica o como una asincrónica, siempre que se origine un intercambio de mensajes solicitud-respuesta cuando se invoque el servicio.  
  
 En general, con la naturaleza asincrónica de los sistemas, no se debería adoptar la dependencia de los subprocesos.  La manera más fiable de pasar los datos a varias fases del procesamiento de envío de la operación es usar extensiones.  
  
 Para ver un ejemplo, consulte [Cómo implementar una operación de servicios asincrónica](how-to-implement-an-asynchronous-service-operation.md).  
  
 Para definir una operación de contrato `X` que se ejecuta asincrónicamente sin tener en cuenta cómo se llama en la aplicación cliente:  
  
- Defina dos métodos mediante el patrón `BeginOperation` y `EndOperation`.  
  
- El método `BeginOperation` incluye parámetros `in` y `ref` para la operación y devuelve un tipo <xref:System.IAsyncResult>.  
  
- El método `EndOperation` incluye un parámetro <xref:System.IAsyncResult> así como los parámetros `out` y `ref` y devuelve el tipo de valor devuelto de las operaciones.  
  
 Por ejemplo, vea el método siguiente.  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 Para crear una operación asincrónica, los dos métodos serían:  
  
```csharp  
[OperationContract(AsyncPattern=true)]
IAsyncResult BeginDoWork(string data,
                         ref string inout,
                         AsyncCallback callback,
                         object state);
int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>
Function BeginDoWork(ByVal data As String, _
                     ByRef inout As String, _
                     ByVal callback As AsyncCallback, _
                     ByVal state As Object) As IAsyncResult
Function EndDoWork(ByRef inout As String, ByRef outonly As String, ByVal result As IAsyncResult) As Integer  
```  
  
> [!NOTE]
> El atributo <xref:System.ServiceModel.OperationContractAttribute> se aplica solamente a los métodos de `BeginDoWork`. El contrato resultante tiene una operación WSDL denominada `DoWork`.  
  
### <a name="client-side-asynchronous-invocations"></a>Llamadas asincrónicas del cliente  

 Una aplicación cliente de WCF puede usar cualquiera de los tres modelos de llamada asincrónica descritos previamente  
  
 Cuando se usa el modelo basado en tareas, basta con llamar a la operación mediante la palabra clave await como se muestra en el fragmento de código siguiente.  
  
```csharp  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 El uso del patrón asincrónico basado en eventos solo requiere agregar un controlador de eventos para recibir una notificación de la respuesta, y el evento resultante se genera automáticamente en el subproceso de la interfaz de usuario. Para aplicar este enfoque, especifique las opciones de comando **/async** y **/tcv:Version35** con la [Herramienta de utilidad de metadatos ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), como en el ejemplo siguiente.  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 Una vez hecho esto, Svcutil.exe genera una clase de cliente de WCF con la infraestructura de cliente que permite a la aplicación de llamada implementar y asignar un controlador de eventos para recibir la respuesta y realizar la acción apropiada. Para ver un ejemplo completo, consulte [Llamada a operaciones de servicio de forma asincrónica](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 El modelo asincrónico basado en eventos, sin embargo, solo está disponible en .NET Framework 3,5. Además, no se admite incluso en .NET Framework 3,5 cuando se crea un canal de cliente de WCF mediante <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> . Con objetos de canal de cliente de WCF, debe utilizar objetos <xref:System.IAsyncResult?displayProperty=nameWithType> para invocar sus operaciones asincrónicamente. Para aplicar este enfoque, especifique la opción de comando **/async** con la [Herramienta de utilidad de metadatos ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), como en el ejemplo siguiente.  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async
```  
  
 Esto genera un contrato de servicio en el cual cada operación se modela como un método `<Begin>` con la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> establecida en `true` y un método `<End>` correspondiente. Para ver un ejemplo completo en el que se usa <xref:System.ServiceModel.ChannelFactory%601>, consulte [Llamada a operaciones de manera asincrónica mediante un generador de canales](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
 En cualquier caso, las aplicaciones pueden invocar una operación asincrónicamente aun cuando se implementa el servicio sincrónicamente, del mismo modo que una aplicación puede usar el mismo patrón para invocar de forma asincrónica un método sincrónico local. El modo en que se implementa la operación no es significativo para el cliente; Cuando llega el mensaje de respuesta, su contenido se envía al método> <asincrónico del cliente `End` y el cliente recupera la información.  
  
### <a name="one-way-message-exchange-patterns"></a>Patrones de intercambio de mensajes unidireccional  

 También puede crear un patrón de intercambio de mensajes asincrónico en el que las operaciones unidireccionales (las operaciones para las que <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> es `true` no tienen ninguna respuesta puesta en correlación) se pueden enviar en cualquier dirección por el cliente o por el servicio, independientemente del otro lado. (Usa el patrón de intercambio de mensajes dúplex con mensajes unidireccionales). En este caso, el contrato de servicio especifica un intercambio de mensajes unidireccional que cualquier lado puede implementar como llamadas o implementaciones asincrónicas, o no, según corresponda. Por lo general, cuando el contrato es un intercambio de mensajes unidireccionales, las implementaciones pueden ser muchas veces asincrónicas porque una vez se envía un mensaje, la aplicación no espera a una respuesta y puede continuar haciendo otro trabajo.  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a>Clientes asincrónicos y contratos de mensajes basados en eventos  

 Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>. De esto resulta que si un cliente importa metadatos mediante opciones de comando asincrónicas basadas en eventos y la operación devuelve más de un valor, el objeto <xref:System.EventArgs> predeterminado devuelve un valor como propiedad `Result` y el resto son propiedades del objeto <xref:System.EventArgs>.  
  
 Si desea recibir el objeto del mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, use la opción de comando **/messageContract**. Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>. Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
