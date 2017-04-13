---
title: "DataContractResolver | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# DataContractResolver
Este ejemplo muestra cómo se pueden personalizar los procesos de deserialización y serialización utilizando la clase <xref:System.Runtime.Serialization.DataContractResolver>.En este ejemplo muestra cómo usar DataContractResolver para asignar los tipos CLR entre una representación xsi:type durante la serialización y la deserialización.  
  
## Detalles del ejemplo  
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
  
 El ejemplo carga el ensamblado, extrae cada uno de estos tipos y, a continuación, los serializa y los deserializa.El objeto <xref:System.Runtime.Serialization.DataContractResolver> se conecta en el proceso de serialización pasando una instancia de la clase derivada <xref:System.Runtime.Serialization.DataContractResolver> al constructor <xref:System.Runtime.Serialization.DataContractSerializer>, según se muestra en el siguiente ejemplo.  
  
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
  
 Dado que el objeto <xref:System.Runtime.Serialization.DataContractResolver> personalizado se pasa en el constructor <xref:System.Runtime.Serialization.DataContractSerializer>, el método <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> se llama durante la serialización para asignar un tipo CLR a un `xsi:type` equivalente.Al igual que el método <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> se llama durante la deserialización para asignar `xsi:type` a un tipo CLR equivalente.En este ejemplo, <xref:System.Runtime.Serialization.DataContractResolver> se define como se muestra en el ejemplo siguiente.  
  
 El ejemplo de código siguiente es una clase que deriva de <xref:System.Runtime.Serialization.DataContractResolver>.  
  
```  
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
  
 Como parte del ejemplo, el proyecto de tipos genera el ensamblado con todos los tipos que se utilizan en este ejemplo.Utilice este proyecto para agregar, quitar o modificar los tipos que se serializarán.  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de CDRSample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## Vea también  
 [Utilizar una resolución del contrato de datos](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)