---
title: Serialización de JSON
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 389bdc8b064bda9870b33a2e4c46fdf90bb7f3ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="json-serialization"></a>Serialización de JSON
Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> para serializar y deserializar los datos en el formato de notación de objetos JavaScript (JSON). Este motor de serialización convierte los datos de JSON en instancias de tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y de nuevo en datos de JSON. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite los mismos tipos que <xref:System.Runtime.Serialization.DataContractSerializer>. El formato de datos de JSON es especialmente útil al escribir JavaScript asincrónico y aplicaciones web de estilo XML (AJAX). Compatibilidad con AJAX en Windows Communication Foundation (WCF) está optimizado para su uso con ASP.NET AJAX a través del control ScriptManager. Para obtener ejemplos de cómo usar Windows Communication Foundation (WCF) con AJAX de ASP.NET, vea el [muestra AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
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
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1.  Compile la solución JsonSerialization.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Ejecute la aplicación de consola resultante.  
  
## <a name="see-also"></a>Vea también
