---
title: Utilizar una resolución del contrato de datos
ms.date: 03/30/2017
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
ms.openlocfilehash: 20abd4d928fc51eb359949ecbb216615e9659b7f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595029"
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="b7792-102">Utilizar una resolución del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="b7792-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="b7792-103">Una resolución del contrato de datos le permite configurar los tipos conocidos dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="b7792-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="b7792-104">Se necesitan tipos conocidos al serializar o deserializar un tipo no esperado por un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="b7792-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> <span data-ttu-id="b7792-105">Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="b7792-105">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="b7792-106">Los tipos conocidos se suelen especificar de modo estático.</span><span class="sxs-lookup"><span data-stu-id="b7792-106">Known types are normally specified statically.</span></span> <span data-ttu-id="b7792-107">Esto significa que tendría que conocer todos los tipos posibles que puede recibir una operación mientras la implementa.</span><span class="sxs-lookup"><span data-stu-id="b7792-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="b7792-108">Hay escenarios en los que no esto no se cumple y es importante saber especificar los tipos conocidos de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="b7792-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="b7792-109">Crear una resolución del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="b7792-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="b7792-110">La creación de una resolución del contrato de datos supone la implementación de dos métodos, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> y <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7792-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="b7792-111">Estos dos métodos implementan devoluciones de llamada que se utilizan durante la serialización y la deserialización respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b7792-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="b7792-112">El método <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> se invoca durante la serialización y toma un tipo de contrato de datos para asignarlo a un espacio de nombres y a un nombre `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="b7792-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="b7792-113">El método <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> se invoca durante la deserialización y toma un espacio de nombres y un nombre `xsi:type` y lo resuelve como un tipo de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="b7792-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="b7792-114">Ambos métodos tienen un parámetro `knownTypeResolver` que se puede emplear para usar la resolución de tipo conocido predeterminada en la implementación.</span><span class="sxs-lookup"><span data-stu-id="b7792-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="b7792-115">En el siguiente ejemplo, se muestra cómo implementar una clase <xref:System.Runtime.Serialization.DataContractResolver> para realizar asignaciones desde y hacia un tipo de contrato de datos denominado `Customer` derivado de una `Person` del tipo de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="b7792-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b7792-116">Cuando haya definido una <xref:System.Runtime.Serialization.DataContractResolver>, puede utilizarla pasándola al constructor <xref:System.Runtime.Serialization.DataContractSerializer>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b7792-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```csharp
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="b7792-117">Puede especificar la clase <xref:System.Runtime.Serialization.DataContractResolver> en una llamada a los métodos <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> o <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b7792-117">You can specify a <xref:System.Runtime.Serialization.DataContractResolver> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> methods, as shown in the following example.</span></span>  
  
```csharp
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="b7792-118">También puede establecerla en <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b7792-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```csharp
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 <span data-ttu-id="b7792-119">Puede especificar mediante declaración una resolución de contrato de datos implementando un atributo que pueda aplicarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="b7792-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  <span data-ttu-id="b7792-120">Para obtener más información, vea el ejemplo [KnownAssemblyAttribute](../samples/knownassemblyattribute.md) .</span><span class="sxs-lookup"><span data-stu-id="b7792-120">For more information, see the [KnownAssemblyAttribute](../samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="b7792-121">En este ejemplo se implementa un atributo denominado "KnownAssembly" que agrega una resolución de contrato de datos personalizada al comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="b7792-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7792-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7792-122">See also</span></span>

- [<span data-ttu-id="b7792-123">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="b7792-123">Data Contract Known Types</span></span>](data-contract-known-types.md)
- [<span data-ttu-id="b7792-124">Ejemplo de DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="b7792-124">DataContractSerializer Sample</span></span>](../samples/datacontractserializer-sample.md)
- [<span data-ttu-id="b7792-125">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="b7792-125">KnownAssemblyAttribute</span></span>](../samples/knownassemblyattribute.md)
