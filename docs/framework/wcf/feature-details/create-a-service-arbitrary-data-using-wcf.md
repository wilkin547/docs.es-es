---
title: "C&#243;mo: Crear un servicio que acepte datos arbitrarios mediante el modelo de programaci&#243;n REST de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Crear un servicio que acepte datos arbitrarios mediante el modelo de programaci&#243;n REST de WCF
A veces los programadores deben tener un control absoluto de la forma en que se devuelven los datos desde una operación de un servicio. Así es cuando una operación de un servicio debe devolver los datos en un formato no admitido por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. En este tema se analiza el uso del modelo de programación REST de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para crear un servicio que recibe datos arbitrarios.  
  
### <a name="to-implement-the-service-contract"></a>Para implementar el contrato de servicios  
  
1.  Definir el contrato de servicios. La operación que recibe los datos arbitrarios debe tener un parámetro de tipo <xref:System.IO.Stream>. Además, este parámetro debe ser el único parámetro pasado en el cuerpo de la solicitud. La operación descrita en este ejemplo también toma un parámetro de nombre de archivo. Este parámetro se pasa dentro de la dirección URL de la solicitud. Puede especificar que un parámetro se pasa en la dirección URL mediante la especificación de un <xref:System.UriTemplate> en el <xref:System.ServiceModel.Web.WebInvokeAttribute>. En este caso, el URI usado para llamar a este método termina en “UploadFile/Some-Filename”. La parte “{filename}” de la plantilla de URI especifica que el parámetro de nombre de archivo para la operación se pasa dentro del URI que se usa para llamar a la operación.  
  
    ```  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  Implemente el contrato de servicios. El contrato tiene un solo método, `UploadFile`, que recibe un archivo de datos arbitrarios en una secuencia. La operación lee la secuencia contando el número de bytes leídos y, después, muestra el nombre de archivo y dicho número.  
  
    ```  
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
  
1.  Cree una aplicación de consola para hospedar el servicio.  
  
    ```  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
  
    ```  
  
2.  Cree una variable para contener la dirección base del servicio dentro del método `Main`.  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  Crear un <xref:System.ServiceModel.ServiceHost> instancia para el servicio que especifica la clase de servicio y la dirección base.  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  Agregue un extremo que especifica el contrato <xref:System.ServiceModel.WebHttpBinding>, y <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
    ```  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  Abrir el host del servicio. El servicio ya está listo para recibir solicitudes.  
  
    ```  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a>Para llamar al servicio mediante programación  
  
1.  Crear un <xref:System.Net.HttpWebRequest> con el URI que se usa para llamar al servicio. En este código, la dirección base se combina con `“/UploadFile/Text”`. La parte `“UploadFile”` del URI especifica la operación que se va a llamar. La parte `“Test.txt”` del URI especifica el parámetro de nombre de archivo que se va a pasar a la operación `UploadFile`. Ambos de estos elementos se asignan a la <xref:System.UriTemplate> aplicado al contrato de operación.  
  
    ```  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
  
    ```  
  
2.  Establecer el <xref:System.Net.HttpWebRequest.Method%2A> propiedad de la <xref:System.Net.HttpWebRequest> a `POST` y el <xref:System.Net.HttpWebRequest.ContentType%2A> propiedad `“text/plain”`. Esto indica al servicio que el código está enviando los datos y que están en texto sin formato.  
  
    ```  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  Llame a <xref:System.Net.HttpWebRequest.GetRequestStream%2A> para obtener la secuencia de solicitud, crear los datos para enviar, escribir esos datos en la secuencia de solicitud y cerrar la secuencia.  
  
    ```  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  Obtener la respuesta del servicio mediante una llamada a <xref:System.Net.HttpWebRequest.GetResponse%2A> y mostrar los datos de respuesta en la consola.  
  
    ```  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
  
    ```  
  
5.  Cierre el host de servicio.  
  
    ```  
    host.Close();  
    ```  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra la lista completa del código de este ejemplo.  
  
```  
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
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Al compilar el código, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vea también  
 [UriTemplate y UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)   
 [Modelo de programación Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [Información general del modelo de programación Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)