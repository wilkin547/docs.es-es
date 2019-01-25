---
title: Procedimiento Serializar y deserializar datos JSON
ms.date: 03/30/2017
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 797b29fd7ddecd3e3ed85f8cb3a6df93044942ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704347"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Procedimiento Serializar y deserializar datos JSON
JSON (notación de objetos JavaScript) es un formato de codificación de datos eficaz que permite intercambios rápidos de cantidades pequeñas de datos entre los exploradores de cliente y servicios web con AJAX (JavaScript asincrónico y XML) habilitado.  
  
 En este tema se muestra cómo serializar objetos de tipo .NET en datos codificados mediante JSON y, a continuación, deserializar los datos en formato JSON en instancias de tipos .NET mediante el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. En este ejemplo, se usa un contrato de datos para mostrar la serialización y deserialización de un tipo `Person` definido por el usuario.  
  
 Normalmente, deserialización y serialización de JSON se administra automáticamente por Windows Communication Foundation (WCF) al usar tipos de contrato de datos en las operaciones de servicio que se exponen a través de puntos de conexión habilitada para AJAX. Sin embargo, en algunos casos puede necesitar trabajar directamente con datos de JSON; éste es el escenario que este tema describe.  
  
> [!NOTE]
>  Si se produce un error durante la serialización de una respuesta saliente en el servidor o la operación de respuesta inicia una excepción por cualquier otro motivo, puede que no se devuelva al cliente como error.  
  
 En este tema se basa en el [serialización JSON](../../../../docs/framework/wcf/samples/json-serialization.md) ejemplo.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Para definir el contrato de datos de una Persona  
  
1.  Defina el contrato de datos para `Person` adjuntando <xref:System.Runtime.Serialization.DataContractAttribute> a la clase y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros que desee serializar. Para obtener más información acerca de los contratos de datos, vea [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>Para serializar una instancia de tipo Persona a JSON  
  
1.  Cree una instancia del tipo `Person`.  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Serialice el objeto `Person` a una secuencia de memoria utilizando el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  Utilice el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> para escribir datos JSON en la secuencia.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Muestre la salida JSON.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Deserialización de una instancia de tipo Persona a partir de JSON  
  
1.  Deserialice los datos codificados con JSON en una nueva instancia de `Person` utilizando el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Muestre los resultados.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  El serializador de JSON inicia una excepción de serialización para los contratos de datos que tienen varios miembros con el mismo nombre, tal y como se muestra en el siguiente código de ejemplo.  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>Vea también
- [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [Compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
