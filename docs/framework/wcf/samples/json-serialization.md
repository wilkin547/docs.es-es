---
title: Ejemplo de DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 52e10ee28137b16bd90e6f3f3ac41f839528f334
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904539"
---
# <a name="datacontractjsonserializer-sample"></a>Ejemplo de DataContractJsonSerializer

> [!NOTE]
> Este ejemplo es para <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. Para la mayoría de los escenarios que implican la serialización y deserialización de JSON, se recomiendan las API en el [espacio de nombres System. Text. JSON](../../../standard/serialization/system-text-json-overview.md). 

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite los mismos tipos que <xref:System.Runtime.Serialization.DataContractSerializer>. El formato de datos de JSON es especialmente útil al escribir JavaScript asincrónico y aplicaciones web de estilo XML (AJAX). La compatibilidad de AJAX en Windows Communication Foundation (WCF) se ha optimizado para su uso con ASP.NET AJAX a través del control ScriptManager. Para obtener ejemplos de cómo usar Windows Communication Foundation (WCF) con ASP.NET AJAX, vea los [ejemplos de Ajax](ajax.md).  
  
El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
El ejemplo utiliza un contrato de datos `Person` para mostrar la serialización y deserialización.  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 Para serializar una instancia del tipo `Person` a JSON, cree primero <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y utilice el método `WriteObject` para escribir los datos de JSON en una secuencia.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 La secuencia de la memoria contiene los datos de JSON válidos.
  
```json  
{"age":42,"name":"John"}  
```  
  
 El ejemplo muestra cómo deserializar a partir de datos de JSON en un objeto. Se rebobina la secuencia y se llama a `ReadObject`.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 Al examinar el objeto `p2`, se revela que se han deserializado los datos de JSON correctamente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1. Compile la solución JsonSerialization. sln tal y como se describe en [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Ejecute la aplicación de consola resultante.  
