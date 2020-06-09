---
title: Procedimiento para crear un servicio que acepte datos arbitrarios mediante el modelo de programación REST de WCF
ms.date: 03/30/2017
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
ms.openlocfilehash: d908651f7815c102b45ea106f5bec4c07d869950
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601340"
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="c3413-102">Procedimiento para crear un servicio que acepte datos arbitrarios mediante el modelo de programación REST de WCF</span><span class="sxs-lookup"><span data-stu-id="c3413-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>
<span data-ttu-id="c3413-103">A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="c3413-104">Este es el caso cuando una operación de servicio debe devolver datos en un formato no admitido byWCF.</span><span class="sxs-lookup"><span data-stu-id="c3413-104">This is the case when a service operation must return data in a format not supported byWCF.</span></span> <span data-ttu-id="c3413-105">En este tema se describe el uso del modelo de programación REST de WCF para crear un servicio que recibe datos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="c3413-105">This topic discusses using the WCF REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="c3413-106">Para implementar el contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="c3413-106">To implement the service contract</span></span>  
  
1. <span data-ttu-id="c3413-107">Definir el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="c3413-107">Define the service contract.</span></span> <span data-ttu-id="c3413-108">La operación que recibe los datos arbitrarios debe tener un parámetro de tipo <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="c3413-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="c3413-109">Además, este parámetro debe ser el único parámetro pasado en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c3413-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="c3413-110">La operación descrita en este ejemplo también toma un parámetro de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="c3413-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="c3413-111">Este parámetro se pasa dentro de la dirección URL de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c3413-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="c3413-112">Puede indicar que se pase un parámetro en la dirección URL si especifica una <xref:System.UriTemplate> en <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c3413-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="c3413-113">En este caso, el URI usado para llamar a este método finaliza en "UploadFile/some-filename".</span><span class="sxs-lookup"><span data-stu-id="c3413-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="c3413-114">La parte "{filename}" de la plantilla URI especifica que el parámetro FILENAME de la operación se pasa dentro del URI utilizado para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="c3413-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2. <span data-ttu-id="c3413-115">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="c3413-115">Implement the service contract.</span></span> <span data-ttu-id="c3413-116">El contrato tiene un solo método, `UploadFile`, que recibe un archivo de datos arbitrarios en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c3413-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="c3413-117">La operación lee la secuencia contando el número de bytes leídos y, después, muestra el nombre de archivo y dicho número.</span><span class="sxs-lookup"><span data-stu-id="c3413-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a><span data-ttu-id="c3413-118">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="c3413-118">To host the service</span></span>  
  
1. <span data-ttu-id="c3413-119">Cree una aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2. <span data-ttu-id="c3413-120">Cree una variable para contener la dirección base del servicio dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="c3413-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="c3413-121">Cree una instancia de <xref:System.ServiceModel.ServiceHost> para el servicio que especifique la clase y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="c3413-122">Agregue un punto de conexión que especifique el contrato, <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="c3413-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="c3413-123">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-123">Open the service host.</span></span> <span data-ttu-id="c3413-124">El servicio ya está listo para recibir solicitudes.</span><span class="sxs-lookup"><span data-stu-id="c3413-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="c3413-125">Para llamar al servicio mediante programación</span><span class="sxs-lookup"><span data-stu-id="c3413-125">To call the service programmatically</span></span>  
  
1. <span data-ttu-id="c3413-126">Cree una <xref:System.Net.HttpWebRequest> con el URI que se usó para llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="c3413-127">En este código, la dirección base se combina con `"/UploadFile/Text"`.</span><span class="sxs-lookup"><span data-stu-id="c3413-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="c3413-128">La parte `"UploadFile"` del URI especifica la operación que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="c3413-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="c3413-129">La parte `"Test.txt"` del URI especifica el parámetro de nombre de archivo que se va a pasar a la operación `UploadFile`.</span><span class="sxs-lookup"><span data-stu-id="c3413-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="c3413-130">Ambos elementos se asignan a la <xref:System.UriTemplate> que se aplicó al contrato de la operación.</span><span class="sxs-lookup"><span data-stu-id="c3413-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2. <span data-ttu-id="c3413-131">Establezca la propiedad <xref:System.Net.HttpWebRequest.Method%2A> de <xref:System.Net.HttpWebRequest> en `POST` y la propiedad <xref:System.Net.HttpWebRequest.ContentType%2A> en `"text/plain"`.</span><span class="sxs-lookup"><span data-stu-id="c3413-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="c3413-132">Esto indica al servicio que el código está enviando los datos y que están en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="c3413-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3. <span data-ttu-id="c3413-133">Llame a <xref:System.Net.HttpWebRequest.GetRequestStream%2A> para obtener la secuencia de la solicitud, cree los datos que se van a enviar, escriba esos datos en la secuencia de la solicitud y cierre la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c3413-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4. <span data-ttu-id="c3413-134">Obtenga la respuesta del servicio mediante una llamada a <xref:System.Net.HttpWebRequest.GetResponse%2A> y muestre los datos de la respuesta en la consola.</span><span class="sxs-lookup"><span data-stu-id="c3413-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5. <span data-ttu-id="c3413-135">Cierre el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c3413-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="c3413-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3413-136">Example</span></span>  
 <span data-ttu-id="c3413-137">A continuación, se muestra la lista completa del código de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c3413-137">The following is a complete listing of the code for this example.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c3413-138">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c3413-138">Compiling the Code</span></span>  
  
- <span data-ttu-id="c3413-139">Al compilar el código, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="c3413-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3413-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3413-140">See also</span></span>

- [<span data-ttu-id="c3413-141">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c3413-141">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="c3413-142">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="c3413-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="c3413-143">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="c3413-143">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
