---
title: Serialización de JSON
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 02e81fe8d75ae7b752641d1f9a650fcfe5873141
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384489"
---
# <a name="json-serialization"></a><span data-ttu-id="ac5bd-102">Serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="ac5bd-102">JSON Serialization</span></span>
<span data-ttu-id="ac5bd-103">Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> para serializar y deserializar los datos en el formato de notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="ac5bd-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="ac5bd-104">Este motor de serialización convierte los datos de JSON en instancias de tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y de nuevo en datos de JSON.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-104">This serialization engine converts JSON data into instances of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and back into JSON data.</span></span> <span data-ttu-id="ac5bd-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite los mismos tipos que <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="ac5bd-106">El formato de datos de JSON es especialmente útil al escribir JavaScript asincrónico y aplicaciones web de estilo XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="ac5bd-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="ac5bd-107">Compatibilidad con AJAX en Windows Communication Foundation (WCF) está optimizado para su uso con ASP.NET AJAX a través del control ScriptManager.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="ac5bd-108">Para obtener ejemplos de cómo usar Windows Communication Foundation (WCF) con ASP.NET AJAX, vea el [muestras de AJAX](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="ac5bd-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5bd-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac5bd-110">El ejemplo utiliza un contrato de datos `Person` para mostrar la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

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

 <span data-ttu-id="ac5bd-111">Para serializar una instancia del tipo `Person` a JSON, cree primero <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y utilice el método `WriteObject` para escribir los datos de JSON en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="ac5bd-112">La secuencia de la memoria contiene los datos de JSON válidos.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="ac5bd-113">El ejemplo muestra cómo deserializar a partir de datos de JSON en un objeto.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="ac5bd-114">Se rebobina la secuencia y se llama a `ReadObject`.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="ac5bd-115">Al examinar el objeto `p2`, se revela que se han deserializado los datos de JSON correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac5bd-116">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac5bd-117">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac5bd-118">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac5bd-119">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac5bd-120">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac5bd-120">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="ac5bd-121">Compile la solución jsonSerialization.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac5bd-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="ac5bd-122">Ejecute la aplicación de consola resultante.</span><span class="sxs-lookup"><span data-stu-id="ac5bd-122">Run the resulting console application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5bd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac5bd-123">See Also</span></span>
