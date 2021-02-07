---
description: 'Más información sobre: ejemplo de DataContractJsonSerializer'
title: Ejemplo de DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 258cd38f9ee532e5d750b4cabaa4214366835be7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726356"
---
# <a name="datacontractjsonserializer-sample"></a><span data-ttu-id="a9f17-103">Ejemplo de DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="a9f17-103">DataContractJsonSerializer sample</span></span>

> [!NOTE]
> <span data-ttu-id="a9f17-104">Este ejemplo es para <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="a9f17-104">This sample is for <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="a9f17-105">Para la mayoría de los escenarios que implican la serialización y deserialización de JSON, se recomiendan las API del [System.Text.Jsen el espacio de nombres](../../../standard/serialization/system-text-json-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9f17-105">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="a9f17-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite los mismos tipos que <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a9f17-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="a9f17-107">El formato de datos de JSON es especialmente útil al escribir JavaScript asincrónico y aplicaciones web de estilo XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="a9f17-107">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="a9f17-108">La compatibilidad de AJAX en Windows Communication Foundation (WCF) se ha optimizado para su uso con ASP.NET AJAX a través del control ScriptManager.</span><span class="sxs-lookup"><span data-stu-id="a9f17-108">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="a9f17-109">Para obtener ejemplos de cómo usar Windows Communication Foundation (WCF) con ASP.NET AJAX, vea los [ejemplos de Ajax](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="a9f17-109">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
<span data-ttu-id="a9f17-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="a9f17-110">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
<span data-ttu-id="a9f17-111">El ejemplo utiliza un contrato de datos `Person` para mostrar la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="a9f17-111">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

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

 <span data-ttu-id="a9f17-112">Para serializar una instancia del tipo `Person` a JSON, cree primero <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y utilice el método `WriteObject` para escribir los datos de JSON en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a9f17-112">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="a9f17-113">La secuencia de la memoria contiene los datos de JSON válidos.</span><span class="sxs-lookup"><span data-stu-id="a9f17-113">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="a9f17-114">El ejemplo muestra cómo deserializar a partir de datos de JSON en un objeto.</span><span class="sxs-lookup"><span data-stu-id="a9f17-114">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="a9f17-115">Se rebobina la secuencia y se llama a `ReadObject`.</span><span class="sxs-lookup"><span data-stu-id="a9f17-115">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="a9f17-116">Al examinar el objeto `p2`, se revela que se han deserializado los datos de JSON correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9f17-116">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9f17-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a9f17-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9f17-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a9f17-118">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a9f17-119">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a9f17-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9f17-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a9f17-120">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a9f17-121">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9f17-121">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="a9f17-122">Compile la solución JsonSerialization. sln tal y como se describe en [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a9f17-122">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="a9f17-123">Ejecute la aplicación de consola resultante.</span><span class="sxs-lookup"><span data-stu-id="a9f17-123">Run the resulting console application.</span></span>  
