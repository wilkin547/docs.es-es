---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 101c33ca197be9dff52a73c844dd0b006e62b2ac
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716591"
---
# <a name="datacontractresolver"></a>DataContractResolver
Este ejemplo muestra cómo se pueden personalizar los procesos de deserialización y serialización utilizando la clase <xref:System.Runtime.Serialization.DataContractResolver>. En este ejemplo muestra cómo usar DataContractResolver para asignar los tipos CLR entre una representación xsi:type durante la serialización y la deserialización.

## <a name="sample-details"></a>Detalles del ejemplo
 En el ejemplo se definen los tipos CLR siguientes.

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

 El ejemplo carga el ensamblado, extrae cada uno de estos tipos y, a continuación, los serializa y los deserializa. El objeto <xref:System.Runtime.Serialization.DataContractResolver> se conecta en el proceso de serialización pasando una instancia de la clase derivada <xref:System.Runtime.Serialization.DataContractResolver> al constructor <xref:System.Runtime.Serialization.DataContractSerializer>, según se muestra en el siguiente ejemplo.

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 En el ejemplo se serializan entonces los tipos CLR según se muestra en el ejemplo de código siguiente.

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

 En el ejemplo se deserializa xsi:types según se muestra en el ejemplo de código siguiente.

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

 Dado que el objeto <xref:System.Runtime.Serialization.DataContractResolver> personalizado se pasa en el constructor <xref:System.Runtime.Serialization.DataContractSerializer>, el método <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> se llama durante la serialización para asignar un tipo CLR a un `xsi:type` equivalente. Al igual que el método <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> se llama durante la deserialización para asignar `xsi:type` a un tipo CLR equivalente. En este ejemplo, <xref:System.Runtime.Serialization.DataContractResolver> se define como se muestra en el ejemplo siguiente.

 El ejemplo de código siguiente es una clase que deriva de <xref:System.Runtime.Serialization.DataContractResolver>.

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

 Como parte del ejemplo, el proyecto de tipos genera el ensamblado con todos los tipos que se utilizan en este ejemplo. Utilice este proyecto para agregar, quitar o modificar los tipos que se serializarán.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2012, abra el archivo de solución Cdrsample. sln.

2. Presione F5 para ejecutar la solución.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a>Vea también

- [Uso de una resolución del contrato de datos](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
