---
title: "Como: Crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e1d808d4daf91b5ff89b05cab8359c90090f293
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="ef3d7-102">Como: Crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="ef3d7-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="ef3d7-103">A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="ef3d7-104">Esto sucede cuando una operación de servicio debe devolver datos en un formato no compatible con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef3d7-104">This is the case when a service operation must return data in a format not supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="ef3d7-105">En este tema se analiza el uso del modelo de programación WEB HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para crear este tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="ef3d7-106">Este servicio tiene una operación que devuelve una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="ef3d7-107">Para implementar el contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="ef3d7-107">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="ef3d7-108">Definir el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-108">Define the service contract.</span></span> <span data-ttu-id="ef3d7-109">El contrato se llama `IImageServer` y tiene un método denominado `GetImage` que devuelve <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="ef3d7-110">Dado que el método devuelve <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asume que la operación tiene el control completo de los bytes que se devuelven desde la operación del servicio y no aplica ningún formato a los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-110">Because the method returns a <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2.  <span data-ttu-id="ef3d7-111">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-111">Implement the service contract.</span></span> <span data-ttu-id="ef3d7-112">El contrato tiene una sola operación (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="ef3d7-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="ef3d7-113">Este método genera un mapa de bits y, a continuación, lo guarda en <xref:System.IO.MemoryStream> en formato .jpg.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="ef3d7-114">A continuación, la operación devuelve esa secuencia al llamador.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-114">The operation then returns that stream to the caller.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="ef3d7-115">Observe la antepenúltima línea de código: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="ef3d7-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="ef3d7-116">Esto establece el encabezado content-type en `"image/jpeg"`.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="ef3d7-117">Aunque en este ejemplo se muestra cómo devolver un archivo .jpg, se puede modificar para devolver cualquier tipo de datos que se requiera, en cualquier formato.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="ef3d7-118">La operación debe recuperar o generar los datos y, a continuación, escribirlos en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="ef3d7-119">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="ef3d7-119">To host the service</span></span>  
  
1.  <span data-ttu-id="ef3d7-120">Cree una aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-120">Create a console application to host the service.</span></span>  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2.  <span data-ttu-id="ef3d7-121">Cree una variable para contener la dirección base del servicio dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="ef3d7-122">Cree una instancia de <xref:System.ServiceModel.ServiceHost> para el servicio, especificando la clase y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="ef3d7-123">Agregue un punto final mediante <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="ef3d7-124">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-124">Open the service host.</span></span>  
  
    ```  
    host.Open()  
    ```  
  
6.  <span data-ttu-id="ef3d7-125">Espere hasta que el usuario presione ENTRAR para terminar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="ef3d7-126">Para llamar al servicio tal cual mediante Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ef3d7-126">To call the raw service using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="ef3d7-127">Ejecute el servicio. Debería aparecer el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2.  <span data-ttu-id="ef3d7-128">Abra Internet Explorer y escriba `http://localhost:8000/Service/GetImage?width=50&height=40`. Debería ver un rectángulo amarillo atravesado por una línea diagonal azul.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef3d7-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef3d7-129">Example</span></span>  
 <span data-ttu-id="ef3d7-130">A continuación, se muestra la lista completa del código de este tema.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-130">The following is a complete listing of the code for this topic.</span></span>  
  
```  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef3d7-131">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ef3d7-131">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ef3d7-132">Al compilar el código de ejemplo, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="ef3d7-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3d7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef3d7-133">See Also</span></span>  
 [<span data-ttu-id="ef3d7-134">Modelo de programación Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="ef3d7-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
