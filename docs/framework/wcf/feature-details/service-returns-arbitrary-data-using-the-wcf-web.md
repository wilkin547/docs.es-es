---
description: 'Más información acerca de cómo: crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF'
title: Procedimiento para crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: aeb03e0dad6c63c463db419027f5556922b2f160
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793537"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="5375f-103">Procedimiento para crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5375f-103">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>

<span data-ttu-id="5375f-104">A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-104">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="5375f-105">Este es el caso cuando una operación de servicio debe devolver datos en un formato no admitido por WCF.</span><span class="sxs-lookup"><span data-stu-id="5375f-105">This is the case when a service operation must return data in a format not supported by WCF.</span></span> <span data-ttu-id="5375f-106">En este tema se describe el uso del modelo de programación WEB HTTP de WCF para crear este tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-106">This topic discusses using the WCF WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="5375f-107">Este servicio tiene una operación que devuelve una secuencia.</span><span class="sxs-lookup"><span data-stu-id="5375f-107">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="5375f-108">Para implementar el contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="5375f-108">To implement the service contract</span></span>  
  
1. <span data-ttu-id="5375f-109">Definir el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="5375f-109">Define the service contract.</span></span> <span data-ttu-id="5375f-110">El contrato se llama `IImageServer` y tiene un método denominado `GetImage` que devuelve <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="5375f-110">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="5375f-111">Dado que el método devuelve <xref:System.IO.Stream> , WCF supone que la operación tiene control total sobre los bytes devueltos por la operación de servicio y no aplica ningún formato a los datos que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="5375f-111">Because the method returns a <xref:System.IO.Stream>, WCF assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2. <span data-ttu-id="5375f-112">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="5375f-112">Implement the service contract.</span></span> <span data-ttu-id="5375f-113">El contrato tiene una sola operación (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="5375f-113">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="5375f-114">Este método genera un mapa de bits y, a continuación, lo guarda en <xref:System.IO.MemoryStream> en formato .jpg.</span><span class="sxs-lookup"><span data-stu-id="5375f-114">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="5375f-115">A continuación, la operación devuelve esa secuencia al llamador.</span><span class="sxs-lookup"><span data-stu-id="5375f-115">The operation then returns that stream to the caller.</span></span>  
  
    ```csharp
    public class Service : IImageServer
    {
        public Stream GetImage(int width, int height)
        {
            Bitmap bitmap = new Bitmap(width, height);
            for (int i = 0; i < bitmap.Width; i++)
            {
                for (int j = 0; j < bitmap.Height; j++)
                {
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);
                }
            }
            MemoryStream ms = new MemoryStream();
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);
            ms.Position = 0;
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";
            return ms;
        }
    }
    ```  
  
     <span data-ttu-id="5375f-116">Observe la antepenúltima línea de código: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="5375f-116">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="5375f-117">Esto establece el encabezado de tipo de contenido en `"image/jpeg"` .</span><span class="sxs-lookup"><span data-stu-id="5375f-117">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="5375f-118">Aunque en este ejemplo se muestra cómo devolver un archivo .jpg, se puede modificar para devolver cualquier tipo de datos que se requiera, en cualquier formato.</span><span class="sxs-lookup"><span data-stu-id="5375f-118">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="5375f-119">La operación debe recuperar o generar los datos y, a continuación, escribirlos en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="5375f-119">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="5375f-120">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="5375f-120">To host the service</span></span>  
  
1. <span data-ttu-id="5375f-121">Cree una aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-121">Create a console application to host the service.</span></span>  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }
    }  
    ```  
  
2. <span data-ttu-id="5375f-122">Cree una variable para contener la dirección base del servicio dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="5375f-122">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. <span data-ttu-id="5375f-123">Cree una instancia de <xref:System.ServiceModel.ServiceHost> para el servicio, especificando la clase y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-123">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. <span data-ttu-id="5375f-124">Agregue un punto final mediante <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5375f-124">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. <span data-ttu-id="5375f-125">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-125">Open the service host.</span></span>  
  
    ```csharp  
    host.Open();  
    ```  
  
6. <span data-ttu-id="5375f-126">Espere hasta que el usuario presione ENTRAR para terminar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5375f-126">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="5375f-127">Para llamar al servicio tal cual mediante Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="5375f-127">To call the raw service using Internet Explorer</span></span>  
  
1. <span data-ttu-id="5375f-128">Ejecute el servicio. Debería aparecer el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="5375f-128">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2. <span data-ttu-id="5375f-129">Abra Internet Explorer y escriba `http://localhost:8000/Service/GetImage?width=50&height=40`. Debería ver un rectángulo amarillo atravesado por una línea diagonal azul.</span><span class="sxs-lookup"><span data-stu-id="5375f-129">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5375f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5375f-130">Example</span></span>  

 <span data-ttu-id="5375f-131">A continuación, se muestra la lista completa del código de este tema.</span><span class="sxs-lookup"><span data-stu-id="5375f-131">The following is a complete listing of the code for this topic.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5375f-132">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5375f-132">Compiling the Code</span></span>  
  
- <span data-ttu-id="5375f-133">Al compilar el código de ejemplo, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="5375f-133">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5375f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5375f-134">See also</span></span>

- [<span data-ttu-id="5375f-135">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5375f-135">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
