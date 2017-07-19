---
title: "Encabezados de direcci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Encabezados de direcci&#243;n
El ejemplo de encabezados de dirección muestra cómo los clientes pueden pasar los parámetros de referencia a un servicio utilizando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La especificación del direccionamiento del WS define la noción de una referencia del extremo como una manera de direccionar un extremo de servicio Web determinado.En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las referencias del extremo se modelan utilizando la clase `EndpointAddress`\- `EndpointAddress` es el tipo del campo de dirección de la clase `ServiceEndpoint`.  
  
 La parte del modelo de referencia de extremo es que cada referencia puede llevar algunos parámetros de referencia que agregan información de identificación excepcional.En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], estos parámetros de referencia se modelan como instancias de la clase `AddressHeader`.  
  
 En este ejemplo, el cliente agrega un parámetro de referencia a `EndpointAddress` del extremo del cliente.El servicio busca este parámetro de referencia y utiliza su valor en la lógica de su operación del servicio "Hola".  
  
## Cliente  
 Para que el cliente envíe un parámetro de referencia, debe agregar un `AddressHeader` a `EndpointAddress` de `ServiceEndpoint`.Dado que la clase `EndpointAddress` es inmutable, la modificación de una dirección del extremo se debe hacer utilizando la clase `EndpointAddressBuilder`.El código siguiente inicializa el cliente para enviar un parámetro de referencia como parte de su mensaje.  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 El código crea un `EndpointAddressBuilder` utilizando el `EndpointAddress` original como un valor inicial.Agrega a continuación un encabezado de dirección creado recientemente; la llamada a `CreateAddressHeadercreates` un encabezado con un nombre, espacio de nombres y valor determinados.Aquí el valor es "John."Una vez agregado al generador el encabezado, el método `ToEndpointAddress()` convierte el generador \(mutable\) en una dirección del extremo \(inmutable\), la cual está asignada al campo de dirección del extremo del cliente.  
  
 Ahora cuando el cliente llama a `Console.WriteLine(client.Hello());`, el servicio puede obtener el valor de este parámetro de dirección, como se ha visto en el resultado del cliente.  
  
 `Hello, John`  
  
## Servidor  
 La implementación de la operación del servicio`Hello()` utiliza el `OperationContext` actual para inspeccionar los valores de los encabezados en el mensaje entrante.  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 El código produce iteraciones sobre todos los encabezados en el mensaje entrante, buscando encabezados que son parámetros de referencia con el nombre determinado y.Cuando se encuentra el parámetro, lee el valor del parámetro y lo almacena en la variante de "id.".  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
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
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## Vea también