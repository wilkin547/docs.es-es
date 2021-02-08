---
description: 'Más información acerca de cómo: crear un servicio que acepte datos arbitrarios mediante el modelo de programación REST de WCF'
title: Procedimiento para crear un servicio que acepte datos arbitrarios mediante el modelo de programación REST de WCF
ms.date: 03/30/2017
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
ms.openlocfilehash: a08e611b51d92e070f18620d61a2b95de2cd6cfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780328"
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a>Procedimiento para crear un servicio que acepte datos arbitrarios mediante el modelo de programación REST de WCF

A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio. Este es el caso cuando una operación de servicio debe devolver datos en un formato no admitido byWCF. En este tema se describe el uso del modelo de programación REST de WCF para crear un servicio que recibe datos arbitrarios.  
  
### <a name="to-implement-the-service-contract"></a>Para implementar el contrato de servicios  
  
1. Definir el contrato de servicios. La operación que recibe los datos arbitrarios debe tener un parámetro de tipo <xref:System.IO.Stream>. Además, este parámetro debe ser el único parámetro pasado en el cuerpo de la solicitud. La operación descrita en este ejemplo también toma un parámetro de nombre de archivo. Este parámetro se pasa dentro de la dirección URL de la solicitud. Puede indicar que se pase un parámetro en la dirección URL si especifica una <xref:System.UriTemplate> en <xref:System.ServiceModel.Web.WebInvokeAttribute>. En este caso, el URI usado para llamar a este método finaliza en "UploadFile/some-filename". La parte "{filename}" de la plantilla URI especifica que el parámetro FILENAME de la operación se pasa dentro del URI utilizado para llamar a la operación.  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2. Implemente el contrato de servicios. El contrato tiene un solo método, `UploadFile`, que recibe un archivo de datos arbitrarios en una secuencia. La operación lee la secuencia contando el número de bytes leídos y, después, muestra el nombre de archivo y dicho número.  
  
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
  
3. Cree una instancia de <xref:System.ServiceModel.ServiceHost> para el servicio que especifique la clase y la dirección base del servicio.  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4. Agregue un punto de conexión que especifique el contrato, <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5. Abrir el host del servicio. El servicio ya está listo para recibir solicitudes.  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a>Para llamar al servicio mediante programación  
  
1. Cree una <xref:System.Net.HttpWebRequest> con el URI que se usó para llamar al servicio. En este código, la dirección base se combina con `"/UploadFile/Text"`. La parte `"UploadFile"` del URI especifica la operación que se va a llamar. La parte `"Test.txt"` del URI especifica el parámetro de nombre de archivo que se va a pasar a la operación `UploadFile`. Ambos elementos se asignan a la <xref:System.UriTemplate> que se aplicó al contrato de la operación.  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2. Establezca la propiedad <xref:System.Net.HttpWebRequest.Method%2A> de <xref:System.Net.HttpWebRequest> en `POST` y la propiedad <xref:System.Net.HttpWebRequest.ContentType%2A> en `"text/plain"`. Esto indica al servicio que el código está enviando los datos y que están en texto sin formato.  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3. Llame a <xref:System.Net.HttpWebRequest.GetRequestStream%2A> para obtener la secuencia de la solicitud, cree los datos que se van a enviar, escriba esos datos en la secuencia de la solicitud y cierre la secuencia.  
  
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
  
4. Obtenga la respuesta del servicio mediante una llamada a <xref:System.Net.HttpWebRequest.GetResponse%2A> y muestre los datos de la respuesta en la consola.  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5. Cierre el host de servicio.  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a>Ejemplo  

 A continuación, se muestra la lista completa del código de este ejemplo.  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Al compilar el código, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vea también

- [UriTemplate y UriTemplateTable](uritemplate-and-uritemplatetable.md)
- [Modelo de programación de web HTTP de WCF](wcf-web-http-programming-model.md)
- [Información general del modelo de programación web HTTP de WCF](wcf-web-http-programming-model-overview.md)
