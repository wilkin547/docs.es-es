---
title: Filtrar para serializar y deserializar datos JSON
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 6363a8e161969c188c5dd18c425ffd42969e9adc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106163"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="74cdf-102">Filtrar Serializar y deserializar datos JSON</span><span class="sxs-lookup"><span data-stu-id="74cdf-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="74cdf-103">JSON (notación de objetos JavaScript) es un formato de codificación de datos eficaz que permite intercambios rápidos de cantidades pequeñas de datos entre los exploradores de cliente y servicios web con AJAX (JavaScript asincrónico y XML) habilitado.</span><span class="sxs-lookup"><span data-stu-id="74cdf-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="74cdf-104">Este artículo muestra cómo serializar objetos de tipo .NET en datos codificados por JSON y, a continuación, deserializar los datos en el formato JSON en instancias de tipos. NET.</span><span class="sxs-lookup"><span data-stu-id="74cdf-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="74cdf-105">Este ejemplo utiliza un contrato de datos para mostrar la serialización y deserialización de definido por el usuario `Person` tipo y usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="74cdf-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="74cdf-106">Normalmente, deserialización y serialización de JSON se controlan automáticamente por Windows Communication Foundation (WCF) al usar tipos de contrato de datos en las operaciones de servicio que se exponen a través de puntos de conexión habilitada para AJAX.</span><span class="sxs-lookup"><span data-stu-id="74cdf-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="74cdf-107">Sin embargo, en algunos casos es posible que deba trabajar directamente con datos JSON.</span><span class="sxs-lookup"><span data-stu-id="74cdf-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
>  <span data-ttu-id="74cdf-108">Si se produce un error durante la serialización de una respuesta saliente en el servidor o por algún otro motivo, no obtener devolver al cliente como un error.</span><span class="sxs-lookup"><span data-stu-id="74cdf-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="74cdf-109">En este artículo se basa en el [serialización JSON](../samples/json-serialization.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74cdf-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="74cdf-110">Para definir el contrato de datos para un tipo de persona</span><span class="sxs-lookup"><span data-stu-id="74cdf-110">To define the data contract for a Person type</span></span> 
  
1.  <span data-ttu-id="74cdf-111">Defina el contrato de datos para `Person` adjuntando <xref:System.Runtime.Serialization.DataContractAttribute> a la clase y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros que desee serializar.</span><span class="sxs-lookup"><span data-stu-id="74cdf-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="74cdf-112">Para obtener más información acerca de los contratos de datos, vea [diseño de contratos de servicio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="74cdf-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
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
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="74cdf-113">Para serializar una instancia de tipo Persona a JSON</span><span class="sxs-lookup"><span data-stu-id="74cdf-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="74cdf-114">Cree una instancia del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="74cdf-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="74cdf-115">Serializar el `Person` objeto a una secuencia de memoria mediante el uso de la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="74cdf-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="74cdf-116">Utilice el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> para escribir datos JSON en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="74cdf-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="74cdf-117">Muestre la salida JSON.</span><span class="sxs-lookup"><span data-stu-id="74cdf-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="74cdf-118">Deserialización de una instancia de tipo Persona a partir de JSON</span><span class="sxs-lookup"><span data-stu-id="74cdf-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="74cdf-119">Deserialice los datos codificados con JSON en una nueva instancia de `Person` utilizando el método <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="74cdf-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="74cdf-120">Muestre los resultados.</span><span class="sxs-lookup"><span data-stu-id="74cdf-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="74cdf-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74cdf-121">Example</span></span>  
  
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
>  <span data-ttu-id="74cdf-122">El serializador de JSON inicia una excepción de serialización para los contratos de datos que tienen varios miembros con el mismo nombre, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74cdf-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74cdf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="74cdf-123">See also</span></span>

- [<span data-ttu-id="74cdf-124">Serialización independiente de JSON</span><span class="sxs-lookup"><span data-stu-id="74cdf-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="74cdf-125">Compatibilidad con JSON y otros datos de formatos de transferencia</span><span class="sxs-lookup"><span data-stu-id="74cdf-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)
