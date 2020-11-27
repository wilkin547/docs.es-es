---
title: Procedimiento para crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
ms.openlocfilehash: 4ed3e5269be5b636b348ff0efe44c49dae5335e2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253900"
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a>Procedimiento para crear un servicio que devuelva datos arbitrarios mediante el modelo de programación web HTTP de WCF

A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio. Este es el caso cuando una operación de servicio debe devolver datos en un formato no admitido por WCF. En este tema se describe el uso del modelo de programación WEB HTTP de WCF para crear este tipo de servicio. Este servicio tiene una operación que devuelve una secuencia.  
  
### <a name="to-implement-the-service-contract"></a>Para implementar el contrato de servicios  
  
1. Definir el contrato de servicios. El contrato se llama `IImageServer` y tiene un método denominado `GetImage` que devuelve <xref:System.IO.Stream>.  
  
    ```csharp  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     Dado que el método devuelve <xref:System.IO.Stream> , WCF supone que la operación tiene control total sobre los bytes devueltos por la operación de servicio y no aplica ningún formato a los datos que se devuelven.  
  
2. Implemente el contrato de servicios. El contrato tiene una sola operación (`GetImage`). Este método genera un mapa de bits y, a continuación, lo guarda en <xref:System.IO.MemoryStream> en formato .jpg. A continuación, la operación devuelve esa secuencia al llamador.  
  
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
  
     Observe la antepenúltima línea de código: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`  
  
     Esto establece el encabezado de tipo de contenido en `"image/jpeg"` . Aunque en este ejemplo se muestra cómo devolver un archivo .jpg, se puede modificar para devolver cualquier tipo de datos que se requiera, en cualquier formato. La operación debe recuperar o generar los datos y, a continuación, escribirlos en una secuencia.  
  
### <a name="to-host-the-service"></a>Para hospedar el servicio  
  
1. Cree una aplicación de consola para hospedar el servicio.  
  
    ```csharp
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }
    }  
    ```  
  
2. Cree una variable para contener la dirección base del servicio dentro del método `Main`.  
  
    ```csharp
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3. Cree una instancia de <xref:System.ServiceModel.ServiceHost> para el servicio, especificando la clase y la dirección base del servicio.  
  
    ```csharp
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4. Agregue un punto final mediante <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. Abrir el host del servicio.  
  
    ```csharp  
    host.Open();  
    ```  
  
6. Espere hasta que el usuario presione ENTRAR para terminar el servicio.  
  
    ```csharp
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a>Para llamar al servicio tal cual mediante Internet Explorer  
  
1. Ejecute el servicio. Debería aparecer el resultado siguiente. `Service is running Press ENTER to close the host`  
  
2. Abra Internet Explorer y escriba `http://localhost:8000/Service/GetImage?width=50&height=40`. Debería ver un rectángulo amarillo atravesado por una línea diagonal azul.  
  
## <a name="example"></a>Ejemplo  

 A continuación, se muestra la lista completa del código de este tema.  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Al compilar el código de ejemplo, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
