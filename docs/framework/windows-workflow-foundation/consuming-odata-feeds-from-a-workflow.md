---
title: 'Consumir fuentes de OData desde un flujo de trabajo: WF'
ms.date: 03/30/2017
ms.assetid: 1b26617c-53e9-476a-81af-675c36d95919
ms.openlocfilehash: c9780200d9b7c7bc89797b3c16b22bc38440fccc
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802666"
---
# <a name="consuming-odata-feeds-from-a-workflow"></a>Consumir fuentes de OData desde un flujo de trabajo

WCF Data Services es un componente del .NET Framework que le permite crear servicios que usan el Open Data Protocol (OData) para exponer y consumir datos en Internet o en una intranet mediante la semántica de transferencia de estado representacional (REST). OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Cualquier aplicación puede interactuar con un servicio de datos basado en OData si puede enviar una solicitud HTTP y procesar la fuente de OData que devuelve un servicio de datos. Además, WCF Data Services incluye bibliotecas de cliente que proporcionan una experiencia de programación más enriquecida cuando se usan fuentes de OData de .NET Framework aplicaciones. En este tema se proporciona una información general del uso de una fuente de OData en un flujo de trabajo con y sin utilizar las bibliotecas de clientes.

## <a name="using-the-sample-northwind-odata-service"></a>Usar el servicio OData de ejemplo Northwind

En los ejemplos de este tema se usa el servicio de datos Northwind de ejemplo ubicado en <https://services.odata.org/Northwind/Northwind.svc/>. Este servicio se proporciona como parte del [SDK de OData](https://www.odata.org/wp-content/uploads/sites/21/odatasdkcodesamples.zip) y proporciona acceso de solo lectura a la base de datos Northwind de ejemplo. Si se quiere acceso de escritura, o un Servicio de datos de WCF local, puede seguir los pasos del [Tutorial rápido (WCF Data Services)](../data/wcf/quickstart-wcf-data-services.md) para crear un servicio OData local que proporcione acceso a la base de datos Northwind. Si sigue el tutorial rápido, sustituya el URI local por el que se proporciona en el código de ejemplo de este tema.

## <a name="consuming-an-odata-feed-using-the-client-libraries"></a>Consumir una fuente de OData mediante las bibliotecas de cliente

WCF Data Services incluye bibliotecas de cliente que le permiten consumir más fácilmente una fuente de OData desde .NET Framework y aplicaciones cliente. Estas bibliotecas simplifican el envío y recepción de los mensajes HTTP. También traducen la carga del mensaje en objetos CLR que representan los datos de entidad. Las bibliotecas cliente representan las dos clases principales <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>. Estas clases le permiten consultar un servicio de datos y, a continuación, trabajar con los datos de entidad devueltos como objetos CLR. En esta sección se incluyen dos enfoques para crear actividades que utilizan bibliotecas de clientes.

### <a name="adding-a-service-reference-to-the-wcf-data-service"></a>Agregar una referencia de servicio al servicio de datos de WCF

Para generar las bibliotecas de cliente de Northwind, puede utilizar el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio 2012 para agregar una referencia al servicio Northwind OData.

![Captura de pantalla que muestra el cuadro de diálogo Agregar referencia de servicio.](./media/consuming-odata-feeds-from-a-workflow/add-service-reference-dialog.gif)

Observe que no hay ninguna operación del servicio expuesta por el servicio y que en la lista **Servicios** hay elementos que representan las entidades expuestas por el servicio de datos Northwind. Cuando se agregue la referencia de servicio, se generarán las clases para estas entidades y se podrán utilizar en el código del cliente. Los ejemplos de este tema usan estas clases y la clase `NorthwindEntities` para realizar las consultas.

> [!NOTE]
> Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos (WCF Data Services)](../data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

### <a name="using-asynchronous-methods"></a>Usar métodos asincrónicos

Para resolver los posibles problemas de latencia que se pueden producir al tener acceso a los recursos en Web, recomendamos el acceso asincrónico a Servicios de datos de WCF. Las bibliotecas de cliente de WCF Data Services incluyen métodos asincrónicos para invocar consultas y Windows Workflow Foundation (WF) proporciona la clase <xref:System.Activities.AsyncCodeActivity> para crear actividades asincrónicas. <xref:System.Activities.AsyncCodeActivity> se pueden escribir actividades derivadas para aprovechar las clases de .NET Framework que tienen métodos asincrónicos, o el código que se ejecuta de forma asincrónica se puede colocar en un método e invocar mediante un delegado. Esta sección proporciona dos ejemplos de una actividad derivada de <xref:System.Activities.AsyncCodeActivity> ; uno que utiliza los métodos asincrónicos de las bibliotecas cliente de los Servicios de datos de WCF y otro que usa un delegado.

> [!NOTE]
> Para obtener más información, vea [operaciones asincrónicas (WCF Data Services)](../data/wcf/asynchronous-operations-wcf-data-services.md) y [crear actividades asincrónicas](creating-asynchronous-activities-in-wf.md).

### <a name="using-client-library-asynchronous-methods"></a>Usar métodos asincrónicos de la biblioteca de cliente

La clase <xref:System.Data.Services.Client.DataServiceQuery%601> proporciona los métodos <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> y <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para consultar asincrónicamente un servicio OData. Se puede llamar a estos métodos desde <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> invalida de una clase derivada de <xref:System.Activities.AsyncCodeActivity> . Cuando se devuelve el <xref:System.Activities.AsyncCodeActivity> <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> invalidación, el flujo de trabajo puede pasar a inactivo (pero no conservar) y, cuando se completa el trabajo asincrónico, el tiempo de ejecución invoca <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>.

En el ejemplo siguiente, se define una actividad `OrdersByCustomer` con dos argumentos de entrada. El argumento `CustomerId` representa el cliente que identifica qué pedidos se va a devolver, mientras que el argumento `ServiceUri` representa el URI del servicio de OData que se va a consultar. Dado que la actividad deriva de `AsyncCodeActivity<IEnumerable<Order>>` hay también un parámetro de salida <xref:System.Activities.Activity%601.Result%2A> que se utiliza para devolver los resultados de la consulta. La <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> reemplazada crea un consulta LINQ que selecciona todos los pedidos del cliente especificado. Esta consulta se especifica como la <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> de la <xref:System.Activities.AsyncCodeActivityContext>pasada y, a continuación, se llama al método de la consulta <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> . Observe que la devolución de llamada y el estado que se pasan a la <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> de la consulta son las que se pasan al método <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> de la actividad. Cuando la consulta se ha terminado de ejecutar, se invoca el método <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> de la actividad. La consulta se recupera desde <xref:System.Activities.AsyncCodeActivityContext.UserState%2A>y, a continuación, se llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> de la consulta. Este método devuelve las <xref:System.Collections.Generic.IEnumerable%601> del tipo de entidad especificado; en este caso `Order`. Puesto que `IEnumerable<Order>` es el tipo genérico del <xref:System.Activities.AsyncCodeActivity%601>, este <xref:System.Collections.IEnumerable> se establece como el <xref:System.Activities.OutArgument%601> <xref:System.Activities.Activity%601.Result%2A> de la actividad.

[!code-csharp[CFX_WCFDataServicesActivityExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#100)]

En el siguiente ejemplo, la actividad `OrdersByCustomer` recupera una lista de pedidos para el cliente especificado y a continuación una actividad <xref:System.Activities.Statements.ForEach%601> enumera los pedidos devueltos y escribe la fecha de cada pedido en la consola.

[!code-csharp[CFX_WCFDataServicesActivityExample#10](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#10)]

Cuando se invoca este flujo de trabajo, se escriben los siguientes datos en la consola:

```console
Calling WCF Data Service...
8/25/1997
10/3/1997
10/13/1997
1/15/1998
3/16/1998
4/9/1998
```

> [!NOTE]
> Si no se puede establecer una conexión al servidor de OData, obtendrá una excepción similar a la siguiente:
>
> Excepción no controlada: System.InvalidOperationException: Error al procesar esta solicitud. ---> System.Net.WebException: No es posible conectar con el servidor remoto ---> System.Net.Sockets.SocketException: Error de intento de conexión porque la parte conectada no respondió correctamente después de un período de tiempo, o error de la conexión establecida porque el host conectado no respondió.

Si se requiere cualquier procesamiento adicional de los datos devueltos por la consulta, se puede hacer al reemplazar <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> en la actividad. Se invocan <xref:System.Activities.AsyncCodeActivity%601.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> al usar el subproceso del flujo de trabajo y cualquier código de estos reemplazos no se ejecuta de forma asincrónica. Si el procesamiento adicional es extenso o de ejecución prolongada, o se paginan los resultados de la consulta, debería considerar el enfoque descrito en la sección siguiente, que utiliza un delegado para ejecutar la consulta y realizar el procesamiento adicional de forma asincrónica.

### <a name="using-a-delegate"></a>Usar un delegado

Además de invocar el método asincrónico de una clase .NET Framework, una actividad basada en <xref:System.Activities.AsyncCodeActivity>también puede definir la lógica asincrónica en uno de sus métodos. Este método se especifica al usar un delegado en el reemplazo de <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> de la actividad. Cuando el método devuelve un resultado, el runtime invoca el reemplazo de <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> de la actividad. Al llamar a un servicio de OData desde un flujo de trabajo, este método se puede utilizar para consultar el servicio y proporcionar cualquier procesamiento adicional.

En el ejemplo siguiente, se define una actividad `ListCustomers` . Esta actividad consulta el servicio de datos de Northwind de ejemplo y devuelve una `List<Customer>` que contiene todos los clientes de la base de datos Northwind. El método `GetCustomers` realiza el trabajo asincrónico. Este método consulta todos los clientes del servicio y, a continuación, los copia en una `List<Customer>`. Después, comprueba si los resultados están paginados. En ese caso, consulta en el servicio la siguiente página de resultados, los agrega a la lista y continúa hasta que se hayan recuperado todos los datos del cliente.

> [!NOTE]
> Para obtener más información acerca de la paginación en WCF Data Services, consulte [Cómo: cargar resultados paginados (WCF Data Services)](../data/wcf/how-to-load-paged-results-wcf-data-services.md).

Una vez agregados todos los clientes, se devuelve la lista. El método `GetCustomers` se especifica en el reemplazo de <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> de la actividad. Puesto que el método tiene un valor devuelto, se crea `Func<string, List<Customer>>` para especificar el método.

> [!NOTE]
> Si el método que realiza el trabajo asincrónico no tiene un valor devuelto, se utiliza  <xref:System.Action> en lugar de <xref:System.Func%601>. Para obtener ejemplos de cómo crear un ejemplo asincrónico con ambos enfoques, vea [crear actividades asincrónicas](creating-asynchronous-activities-in-wf.md).

<xref:System.Func%601> está asignado a <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> y, a continuación, se llama a `BeginInvoke`. Puesto que el método que se va a invocar no tiene el acceso al entorno de argumentos de la actividad, el valor del argumento `ServiceUri` se pasa como el primer parámetro, junto con la devolución de llamada y estado por los que se pasaron en <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>. Cuando `GetCustomers` devuelve un resultado, el runtime invoca a <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. El código de <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> recupera el delegado desde la propiedad <xref:System.Activities.AsyncCodeActivityContext.UserState%2A>, llama a `EndInvoke`y devuelve el resultado, que es la lista de clientes devuelta desde el método `GetCustomers` .

[!code-csharp[CFX_WCFDataServicesActivityExample#200](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#200)]

En el siguiente ejemplo, la actividad `ListCustomers` recupera una lista de clientes y, a continuación, una actividad <xref:System.Activities.Statements.ForEach%601> los enumera y escribe el nombre de la compañía y nombre de contacto de cada cliente en la consola.

[!code-csharp[CFX_WCFDataServicesActivityExample#20](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#20)]

Cuando se invoca este flujo de trabajo, se escriben los siguientes datos en la consola. Puesto que esta consulta devuelve muchos clientes, solo se mostró aquí una parte del resultado.

```console
Calling WCF Data Service...
Alfreds Futterkiste, Contact: Maria Anders
Ana Trujillo Emparedados y helados, Contact: Ana Trujillo
Antonio Moreno Taquería, Contact: Antonio Moreno
Around the Horn, Contact: Thomas Hardy
Berglunds snabbköp, Contact: Christina Berglund
...
```

## <a name="consuming-an-odata-feed-without-using-the-client-libraries"></a>Consumir una fuente de OData sin usar las bibliotecas de cliente

OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Al utilizar las bibliotecas de clientes, se crean estos URI para usted, pero no tiene que utilizar las bibliotecas de clientes. Si se desea, se puede tener acceso directo a los servicios OData sin utilizar las bibliotecas de clientes. Cuando no se usan las bibliotecas de clientes, la ubicación del servicio y los datos deseados son especificados por el URI y los resultados se devuelven en respuesta a la solicitud HTTP. Entonces, estos datos sin procesar se pueden procesar o manipular del modo deseado. Una manera de recuperar los resultados de una consulta de OData es utilizando la clase <xref:System.Net.WebClient> . En este ejemplo, se recupera el nombre de contacto para el cliente representado por la clave ALFKI.

[!code-csharp[CFX_WCFDataServicesActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#2)]

Cuando se ejecuta este código, en la consola se muestra el siguiente resultado:

```console
Raw data returned:
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<ContactName xmlns="http://schemas.microsoft.com/ado/2007/08/dataservices">Maria Anders</ContactName>
```

En un flujo de trabajo, el código de este ejemplo podría incorporarse al reemplazo <xref:System.Activities.CodeActivity.Execute%2A> de una actividad personalizada basada en <xref:System.Activities.CodeActivity>, pero también se puede lograr la misma funcionalidad utilizando la actividad <xref:System.Activities.Expressions.InvokeMethod%601>. La actividad <xref:System.Activities.Expressions.InvokeMethod%601> permite a los autores del flujo de trabajo invocarlos métodos estáticos y de instancia de una clase, pero también tiene una opción para invocar el método especificado de forma asincrónica. En el siguiente ejemplo, se configura una actividad <xref:System.Activities.Expressions.InvokeMethod%601> para llamar al método <xref:System.Net.WebClient.DownloadString%2A> de la clase <xref:System.Net.WebClient> y devolver una lista de clientes.

[!code-csharp[CFX_WCFDataServicesActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#3)]

<xref:System.Activities.Expressions.InvokeMethod%601> puede llamar métodos estáticos y de instancia de una clase. Puesto que <xref:System.Net.WebClient.DownloadString%2A> es un método de instancia de la clase <xref:System.Net.WebClient> , una nueva instancia de la clase <xref:System.Net.WebClient> se especifica para <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A>. `DownloadString` se especifica como <xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A>, el URI que contiene la consulta se especifica en la colección <xref:System.Activities.Expressions.InvokeMethod%601.Parameters%2A> y el valor devuelto se asigna al valor de <xref:System.Activities.Activity%601.Result%2A> . El valor <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A> se establece en `true`, lo que significa que la invocación del método se ejecutará de forma asincrónica con respecto al flujo de trabajo. En el siguiente ejemplo, se construye un flujo de trabajo que utiliza la actividad <xref:System.Activities.Expressions.InvokeMethod%601> para consultar en el servicio de datos de Northwind dl ejemplo una lista de pedidos para un cliente concreto y, a continuación, los datos devueltos se escriben en la consola.

[!code-csharp[CFX_WCFDataServicesActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#1)]

Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado. Puesto que esta consulta devuelve varios pedidos, solo se muestra aquí una parte del resultado.

```console
Calling WCF Data Service...
Raw data returned:

<?xml version="1.0" encoding="utf-8" standalone="yes"?>*
<feed
xml:base="http://services.odata.org/Northwind/Northwind.svc/"
xmlns:d="http://schemas.microsoft.com/ado/2007/08/dataservices"
xmlns:m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"
xmlns="http://www.w3.org/2005/Atom">
<title type="text">Orders\</title>
<id>http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders\</id>
<updated>2010-05-19T19:37:07Z\</updated>
<link rel="self" title="Orders" href="Orders" />
<entry>
<id>http://services.odata.org/Northwind/Northwind.svc/Orders(10643)\</id>
<title type="text">\</title>
<updated>2010-05-19T19:37:07Z\</updated>
<author>
<name />
</author>
<link rel="edit" title="Order" href="Orders(10643)" />
<link rel="http://schemas.microsoft.com/ado/2007/08/dataservices/related/Customer" type="application/atom+xml;type=entry" title="Customer" href="Orders(10643)/Customer" />
...
```

Este ejemplo proporciona un método que los autores de aplicación de flujo de trabajo pueden usar para consumir los datos sin formato devueltos de un servicio de OData. Para obtener más información sobre el acceso a WCF Data Services mediante URI, consulte [acceso a los recursos del servicio de datos (WCF Data Services)](../data/wcf/accessing-data-service-resources-wcf-data-services.md) y [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
