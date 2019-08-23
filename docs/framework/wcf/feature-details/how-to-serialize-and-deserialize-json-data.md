---
title: Procedimiento para serializar y deserializar datos JSON
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 0bebdbb3d74d58db093c4ec1e0e88138c7080335
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947897"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="3b0b7-102">Procedimiento Serialización y deserialización de datos JSON</span><span class="sxs-lookup"><span data-stu-id="3b0b7-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="3b0b7-103">JSON (notación de objetos JavaScript) es un formato de codificación de datos eficaz que permite intercambios rápidos de cantidades pequeñas de datos entre los exploradores de cliente y servicios web con AJAX (JavaScript asincrónico y XML) habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="3b0b7-104">En este artículo se muestra cómo serializar objetos de tipo .NET en datos codificados con JSON y, a continuación, deserializar los datos en formato JSON en instancias de tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="3b0b7-105">En este ejemplo se usa un contrato de datos para mostrar la serialización y la deserialización `Person` de un tipo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>definido por el usuario y se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="3b0b7-106">Normalmente, Windows Communication Foundation (WCF) administra automáticamente la serialización y deserialización de JSON cuando se usan tipos de contrato de datos en operaciones de servicio que se exponen a través de puntos de conexión habilitados para AJAX.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="3b0b7-107">Sin embargo, en algunos casos puede que necesite trabajar directamente con datos JSON.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
> <span data-ttu-id="3b0b7-108">Si se produce un error durante la serialización de una respuesta saliente en el servidor o por algún otro motivo, puede que no se devuelva al cliente como un error.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="3b0b7-109">Este artículo se basa en el ejemplo de serialización de [JSON](../samples/json-serialization.md) .</span><span class="sxs-lookup"><span data-stu-id="3b0b7-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="3b0b7-110">Para definir el contrato de datos para un tipo de persona</span><span class="sxs-lookup"><span data-stu-id="3b0b7-110">To define the data contract for a Person type</span></span> 
  
1. <span data-ttu-id="3b0b7-111">Defina el contrato de datos para `Person` adjuntando <xref:System.Runtime.Serialization.DataContractAttribute> a la clase y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros que desee serializar.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="3b0b7-112">Para obtener más información sobre los contratos de datos, consulte [diseño de contratos de servicio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b7-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="3b0b7-113">Para serializar una instancia de tipo Persona a JSON</span><span class="sxs-lookup"><span data-stu-id="3b0b7-113">To serialize an instance of type Person to JSON</span></span>  
  
1. <span data-ttu-id="3b0b7-114">Cree una instancia del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    var p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. <span data-ttu-id="3b0b7-115">Serialice el `Person` objeto en una secuencia <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>de memoria mediante.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    var stream1 = new MemoryStream();  
    var ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. <span data-ttu-id="3b0b7-116">Utilice el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> para escribir datos JSON en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. <span data-ttu-id="3b0b7-117">Muestre la salida JSON.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    var sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="3b0b7-118">Deserialización de una instancia de tipo Persona a partir de JSON</span><span class="sxs-lookup"><span data-stu-id="3b0b7-118">To deserialize an instance of type Person from JSON</span></span>  
  
1. <span data-ttu-id="3b0b7-119">Deserialice los datos codificados con JSON en una nueva instancia de `Person` utilizando el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="3b0b7-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    var p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. <span data-ttu-id="3b0b7-120">Muestre los resultados.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="3b0b7-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b0b7-121">Example</span></span>  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    // Create User object.  
    var user = new User("Bob", 42);  
  
    // Create a stream to serialize the object to.  
    var ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    var ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    var deserializedUser = new User();  
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="3b0b7-122">El serializador de JSON inicia una excepción de serialización para los contratos de datos que tienen varios miembros con el mismo nombre, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3b0b7-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b0b7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b0b7-123">See also</span></span>

- [<span data-ttu-id="3b0b7-124">Serialización de JSON independiente</span><span class="sxs-lookup"><span data-stu-id="3b0b7-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="3b0b7-125">Compatibilidad con JSON y otros formatos de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="3b0b7-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)
