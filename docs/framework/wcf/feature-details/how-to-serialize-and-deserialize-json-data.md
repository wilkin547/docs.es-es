---
title: "Cómo serializar y deserializar datos JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4fd768a3a254616dc5dd8b5127ec7f794b71159
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="061f2-102">Cómo serializar y deserializar datos JSON</span><span class="sxs-lookup"><span data-stu-id="061f2-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="061f2-103">JSON (notación de objetos JavaScript) es un formato de codificación de datos eficaz que permite intercambios rápidos de cantidades pequeñas de datos entre los exploradores de cliente y servicios web con AJAX (JavaScript asincrónico y XML) habilitado.</span><span class="sxs-lookup"><span data-stu-id="061f2-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="061f2-104">En este tema se muestra cómo serializar objetos de tipo .NET en datos codificados mediante JSON y, a continuación, deserializar los datos en formato JSON en instancias de tipos .NET mediante el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="061f2-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="061f2-105">En este ejemplo, se usa un contrato de datos para mostrar la serialización y deserialización de un tipo `Person` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="061f2-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="061f2-106">Normalmente, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] controla automáticamente la serialización y deserialización de JSON cuando utiliza tipos de contrato de datos en operaciones de servicio que se exponen sobre extremos con AJAX habilitado.</span><span class="sxs-lookup"><span data-stu-id="061f2-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="061f2-107">Sin embargo, en algunos casos puede necesitar trabajar directamente con datos de JSON; éste es el escenario que este tema describe.</span><span class="sxs-lookup"><span data-stu-id="061f2-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="061f2-108">Si se produce un error durante la serialización de una respuesta saliente en el servidor o la operación de respuesta inicia una excepción por cualquier otro motivo, puede que no se devuelva al cliente como error.</span><span class="sxs-lookup"><span data-stu-id="061f2-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="061f2-109">En este tema se basa en el [serialización JSON](../../../../docs/framework/wcf/samples/json-serialization.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="061f2-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="061f2-110">Para definir el contrato de datos de una Persona</span><span class="sxs-lookup"><span data-stu-id="061f2-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="061f2-111">Defina el contrato de datos para `Person` adjuntando <xref:System.Runtime.Serialization.DataContractAttribute> a la clase y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros que desee serializar.</span><span class="sxs-lookup"><span data-stu-id="061f2-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="061f2-112">contratos de datos, vea [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="061f2-112"> data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
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
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="061f2-113">Para serializar una instancia de tipo Persona a JSON</span><span class="sxs-lookup"><span data-stu-id="061f2-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="061f2-114">Cree una instancia del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="061f2-114">Create an instance of the `Person` type.</span></span>  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="061f2-115">Serialice el objeto `Person` a una secuencia de memoria utilizando el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="061f2-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="061f2-116">Utilice el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> para escribir datos JSON en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="061f2-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="061f2-117">Muestre la salida JSON.</span><span class="sxs-lookup"><span data-stu-id="061f2-117">Show the JSON output.</span></span>  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="061f2-118">Deserialización de una instancia de tipo Persona a partir de JSON</span><span class="sxs-lookup"><span data-stu-id="061f2-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="061f2-119">Deserialice los datos codificados con JSON en una nueva instancia de `Person` utilizando el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="061f2-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="061f2-120">Muestre los resultados.</span><span class="sxs-lookup"><span data-stu-id="061f2-120">Show the results.</span></span>  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a><span data-ttu-id="061f2-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="061f2-121">Example</span></span>  
  
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
>  <span data-ttu-id="061f2-122">El serializador de JSON inicia una excepción de serialización para los contratos de datos que tienen varios miembros con el mismo nombre, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="061f2-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="061f2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="061f2-123">See Also</span></span>  
 [<span data-ttu-id="061f2-124">Serialización de JSON independiente</span><span class="sxs-lookup"><span data-stu-id="061f2-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="061f2-125">Compatibilidad con JSON y otros datos de formatos de transferencia</span><span class="sxs-lookup"><span data-stu-id="061f2-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
