---
title: Ejemplo de DataContractSerializer
ms.date: 03/30/2017
helpviewer_keywords:
- XML Formatter
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
ms.openlocfilehash: 59bbeb4091c101efeac4e0562f0e3cbd5a8b5f79
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716361"
---
# <a name="datacontractserializer-sample"></a><span data-ttu-id="cbec3-102">Ejemplo de DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="cbec3-102">DataContractSerializer Sample</span></span>
<span data-ttu-id="cbec3-103">El ejemplo de DataContractSerializer muestra el <xref:System.Runtime.Serialization.DataContractSerializer>, que realiza la serialización general y los servicios de deserialización para las clases de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="cbec3-103">The DataContractSerializer sample demonstrates the <xref:System.Runtime.Serialization.DataContractSerializer>, which performs general serialization and deserialization services for the data contract classes.</span></span> <span data-ttu-id="cbec3-104">El ejemplo crea un objeto `Record`, lo serializa en una secuencia de memoria y deserializa la secuencia de memoria a otro objeto `Record` para mostrar el uso de la <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cbec3-104">The sample creates a `Record` object, serializes it to a memory stream and deserializes the memory stream back to another `Record` object to demonstrate the use of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="cbec3-105">El ejemplo serializa a continuación el objeto `Record` utilizando un sistema de escritura binario para mostrar cómo el sistema de escritura afecta a la serialización.</span><span class="sxs-lookup"><span data-stu-id="cbec3-105">The sample then serializes the `Record` object using a binary writer to demonstrate how the writer affects serialization.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbec3-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="cbec3-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cbec3-107">El contrato de datos para `Record` se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="cbec3-107">The data contract for `Record` is shown in the following sample code.</span></span>  
  
```csharp  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return $"Record: {n1} {operation} {n2} = {result}";
    }  
}  
```  
  
 <span data-ttu-id="cbec3-108">El código muestra crea un objeto `Record` denominado `record1` y, a continuación, muestra el objeto.</span><span class="sxs-lookup"><span data-stu-id="cbec3-108">The sample code creates a `Record` object named `record1` then displays the object.</span></span>  
  
```csharp
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
```  
  
 <span data-ttu-id="cbec3-109">El ejemplo utiliza la continuación <xref:System.Runtime.Serialization.DataContractSerializer> para serializar `record1` en una secuencia de la memoria.</span><span class="sxs-lookup"><span data-stu-id="cbec3-109">The sample then uses the <xref:System.Runtime.Serialization.DataContractSerializer> to serialize `record1` into a memory stream.</span></span>  
  
```csharp  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
```  
  
 <span data-ttu-id="cbec3-110">Luego, el ejemplo utiliza <xref:System.Runtime.Serialization.DataContractSerializer> para deserializar la secuencia de la memoria en un nuevo objeto `Record` y lo muestra.</span><span class="sxs-lookup"><span data-stu-id="cbec3-110">Next, the sample uses the <xref:System.Runtime.Serialization.DataContractSerializer> to deserialize the memory stream back into a new `Record` object and displays it.</span></span>  
  
```csharp  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
```  
  
 <span data-ttu-id="cbec3-111">De forma predeterminada, `DataContractSerializer` codifica los objetos en una secuencia utilizando una representación textual de XML.</span><span class="sxs-lookup"><span data-stu-id="cbec3-111">By default, the `DataContractSerializer` encodes objects into a stream using a textual representation of XML.</span></span> <span data-ttu-id="cbec3-112">Sin embargo, puede influir en la codificación del XML pasando un sistema de escritura diferente.</span><span class="sxs-lookup"><span data-stu-id="cbec3-112">However, you can influence the encoding of the XML by passing in a different writer.</span></span> <span data-ttu-id="cbec3-113">El ejemplo crea un sistema de escritura binario llamando <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbec3-113">The sample creates a binary writer by calling <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span></span> <span data-ttu-id="cbec3-114">Pasa a continuación el sistema de escritura y el objeto de registro al serializador cuando llama <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbec3-114">It then passes the writer and the record object to the serializer when it calls <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span></span> <span data-ttu-id="cbec3-115">Finalmente, el ejemplo vacía el sistema de escritura e informa de la longitud de las secuencias.</span><span class="sxs-lookup"><span data-stu-id="cbec3-115">Finally, the sample flushes the writer and reports on the length of the streams.</span></span>  
  
```csharp  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 <span data-ttu-id="cbec3-116">Al ejecutarse el ejemplo, se muestra el registro original y el registro deserializado, seguido por la comparación entre la longitud de la codificación de texto y la codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="cbec3-116">When you run the sample, the original record and the deserialized record are displayed, followed by the comparison between the length of the text encoding and the binary encoding.</span></span> <span data-ttu-id="cbec3-117">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="cbec3-117">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cbec3-118">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbec3-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cbec3-119">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cbec3-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cbec3-120">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cbec3-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="cbec3-121">Para ejecutar el ejemplo, inicie el cliente desde el símbolo del sistema escribiendo client\bin\client.exe.</span><span class="sxs-lookup"><span data-stu-id="cbec3-121">To run the sample, start the client from the command prompt by typing client\bin\client.exe.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cbec3-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="cbec3-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbec3-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cbec3-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="cbec3-124">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbec3-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbec3-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="cbec3-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
