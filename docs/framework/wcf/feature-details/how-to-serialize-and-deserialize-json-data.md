---
title: "C&#243;mo serializar y deserializar datos JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo serializar y deserializar datos JSON
JSON (notación de objetos JavaScript) es un formato de codificación de datos eficaz que permite intercambios rápidos de cantidades pequeñas de datos entre los exploradores de cliente y servicios web con AJAX (JavaScript asincrónico y XML) habilitado.  
  
 Este tema muestra cómo serializar objetos de tipo .NET en datos codificados mediante JSON y, a continuación, deserializar los datos en formato JSON en instancias de tipos de .NET mediante el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. En este ejemplo, se usa un contrato de datos para mostrar la serialización y deserialización de un tipo `Person` definido por el usuario.  
  
 Normalmente, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] controla automáticamente la serialización y deserialización de JSON cuando utiliza tipos de contrato de datos en operaciones de servicio que se exponen sobre extremos con AJAX habilitado. Sin embargo, en algunos casos puede necesitar trabajar directamente con datos de JSON; éste es el escenario que este tema describe.  
  
> [!NOTE]
>  Si se produce un error durante la serialización de una respuesta saliente en el servidor o la operación de respuesta inicia una excepción por cualquier otro motivo, puede que no se devuelva al cliente como error.  
  
 En este tema se basa en el [serialización JSON](../../../../docs/framework/wcf/samples/json-serialization.md) ejemplo.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Para definir el contrato de datos de una Persona  
  
1.  Definir el contrato de datos `Person` adjuntando el <xref:System.Runtime.Serialization.DataContractAttribute> a la clase y <xref:System.Runtime.Serialization.DataMemberAttribute> atributo a los miembros que desee serializar. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]contratos de datos, vea [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```  
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
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Serializar la `Person` objeto en una secuencia de memoria utilizando la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  Utilice la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> método para escribir datos JSON en la secuencia.  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Muestre la salida JSON.  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Deserialización de una instancia de tipo Persona a partir de JSON  
  
1.  Deserializar los datos codificados con JSON en una nueva instancia de `Person` utilizando la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> método de la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Muestre los resultados.  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a>Ejemplo  
  
```  
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
  
```  
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
 [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [Compatibilidad para JSON y otros datos de formatos de transferencia](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)