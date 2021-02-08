---
description: 'Más información acerca de: DataContractResolver'
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 629316e45a125eaedad46c57dc22844a24d5e79f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778261"
---
# <a name="datacontractresolver"></a><span data-ttu-id="64093-103">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="64093-103">DataContractResolver</span></span>

<span data-ttu-id="64093-104">Este ejemplo muestra cómo se pueden personalizar los procesos de deserialización y serialización utilizando la clase <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="64093-104">This sample demonstrates how the serialization and deserialization processes can be customized by using the <xref:System.Runtime.Serialization.DataContractResolver> class.</span></span> <span data-ttu-id="64093-105">En este ejemplo muestra cómo usar DataContractResolver para asignar los tipos CLR entre una representación xsi:type durante la serialización y la deserialización.</span><span class="sxs-lookup"><span data-stu-id="64093-105">This sample shows how to use a DataContractResolver to map CLR types to and from an xsi:type representation during serialization and deserialization.</span></span>

## <a name="sample-details"></a><span data-ttu-id="64093-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="64093-106">Sample Details</span></span>

 <span data-ttu-id="64093-107">En el ejemplo se definen los tipos CLR siguientes.</span><span class="sxs-lookup"><span data-stu-id="64093-107">The sample defines the following CLR types.</span></span>

```csharp
using System;
using System.Runtime.Serialization;

namespace Types
{
    [DataContract]
    public class Customer
    {
        [DataMember]
        public string Name { get; set; }
    }

    [DataContract]
    public class VIPCustomer : Customer
    {
        [DataMember]
        public string VipInfo { get; set; }
    }

    [DataContract]
    public class RegularCustomer : Customer
    {
    }

    [DataContract]
    public class PreferredVIPCustomer : VIPCustomer
    {
    }
}
```

 <span data-ttu-id="64093-108">El ejemplo carga el ensamblado, extrae cada uno de estos tipos y, a continuación, los serializa y los deserializa.</span><span class="sxs-lookup"><span data-stu-id="64093-108">The sample loads the assembly, extracts each of these types, and then serializes and deserializes them.</span></span> <span data-ttu-id="64093-109">El objeto <xref:System.Runtime.Serialization.DataContractResolver> se conecta en el proceso de serialización pasando una instancia de la clase derivada <xref:System.Runtime.Serialization.DataContractResolver> al constructor <xref:System.Runtime.Serialization.DataContractSerializer>, según se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="64093-109">The <xref:System.Runtime.Serialization.DataContractResolver> is plugged into the serialization process by passing an instance of the <xref:System.Runtime.Serialization.DataContractResolver>-derived class to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, as shown in the following example.</span></span>

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 <span data-ttu-id="64093-110">En el ejemplo se serializan entonces los tipos CLR según se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="64093-110">The sample then serializes the CLR types as shown in the following code example.</span></span>

```csharp
Assembly assembly = Assembly.Load(new AssemblyName("Types"));

public void serialize(Type type)
{
    Object instance = Activator.CreateInstance(type);

    Console.WriteLine("----------------------------------------");
    Console.WriteLine();
    Console.WriteLine("Serializing type: {0}", type.Name);
    Console.WriteLine();
    this.buffer = new StringBuilder();
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))
    {
        try
        {
            this.serializer.WriteObject(xmlWriter, instance);
        }
        catch (SerializationException error)
        {
            Console.WriteLine(error.ToString());
        }
    }
    Console.WriteLine(this.buffer.ToString());
}
```

 <span data-ttu-id="64093-111">En el ejemplo se deserializa xsi:types según se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="64093-111">The sample then deserializes the xsi:types as shown in the following code example.</span></span>

```csharp
public void deserialize(Type type)
{
    Console.WriteLine();
    Console.WriteLine("Deserializing type: {0}", type.Name);
    Console.WriteLine();
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))
    {
        Object obj = this.serializer.ReadObject(xmlReader);
    }
}
```

 <span data-ttu-id="64093-112">Dado que el objeto <xref:System.Runtime.Serialization.DataContractResolver> personalizado se pasa en el constructor <xref:System.Runtime.Serialization.DataContractSerializer>, el método <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> se llama durante la serialización para asignar un tipo CLR a un `xsi:type` equivalente.</span><span class="sxs-lookup"><span data-stu-id="64093-112">Since the custom <xref:System.Runtime.Serialization.DataContractResolver> is passed in to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, the <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> is called during serialization to map a CLR type to an equivalent `xsi:type`.</span></span> <span data-ttu-id="64093-113">Al igual que el método <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> se llama durante la deserialización para asignar `xsi:type` a un tipo CLR equivalente.</span><span class="sxs-lookup"><span data-stu-id="64093-113">Similarly the <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> is called during deserialization to map the `xsi:type` to an equivalent CLR type.</span></span> <span data-ttu-id="64093-114">En este ejemplo, <xref:System.Runtime.Serialization.DataContractResolver> se define como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="64093-114">In this sample, the <xref:System.Runtime.Serialization.DataContractResolver> is defined as shown in the following example.</span></span>

 <span data-ttu-id="64093-115">El ejemplo de código siguiente es una clase que deriva de <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="64093-115">The following code example is a class deriving from <xref:System.Runtime.Serialization.DataContractResolver>.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();
    Assembly assembly;

    public MyDataContractResolver(Assembly assembly)
    {
        this.assembly = assembly;
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        XmlDictionaryString tName;
        XmlDictionaryString tNamespace;
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))
        {
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);
        }
        else
        {
            return null;
        }
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        string name = dataContractType.Name;
        string namesp = dataContractType.Namespace;
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);
        if (!dictionary.ContainsKey(dataContractType.Name))
        {
            dictionary.Add(name, typeName);
        }
        if (!dictionary.ContainsKey(dataContractType.Namespace))
        {
            dictionary.Add(namesp, typeNamespace);
        }
    }
}
```

 <span data-ttu-id="64093-116">Como parte del ejemplo, el proyecto de tipos genera el ensamblado con todos los tipos que se utilizan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="64093-116">As part of the sample, the Types project generates the assembly with all the types that are used in this sample.</span></span> <span data-ttu-id="64093-117">Utilice este proyecto para agregar, quitar o modificar los tipos que se serializarán.</span><span class="sxs-lookup"><span data-stu-id="64093-117">Use this project to add, remove or modify the types that will be serialized.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="64093-118">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="64093-118">To use this sample</span></span>

1. <span data-ttu-id="64093-119">Con Visual Studio 2012, abra el archivo de solución Cdrsample. sln.</span><span class="sxs-lookup"><span data-stu-id="64093-119">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="64093-120">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="64093-120">To run the solution, press F5</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64093-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="64093-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="64093-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="64093-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="64093-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="64093-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64093-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="64093-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a><span data-ttu-id="64093-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="64093-125">See also</span></span>

- [<span data-ttu-id="64093-126">Utilizar una resolución del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="64093-126">Using a Data Contract Resolver</span></span>](../feature-details/using-a-data-contract-resolver.md)
