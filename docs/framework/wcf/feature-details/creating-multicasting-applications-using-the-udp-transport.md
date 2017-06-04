---
title: "Crear aplicaciones de multidifusi&#243;n mediante el transporte UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Crear aplicaciones de multidifusi&#243;n mediante el transporte UDP
Las aplicaciones de multidifusión envían pequeños mensajes a un gran número de destinatarios al mismo tiempo sin necesidad de establecer conexiones punto a punto.El énfasis de esas aplicaciones es la velocidad sobre la confiabilidad.Es decir es más importante enviar datos puntualmente que asegurarse de que cualquier mensaje concreto se reciba realmente.WCF admite ahora la escritura de aplicaciones de multidifusión mediante <xref:System.ServiceModel.UdpBinding>.Este transporte es útil en escenarios donde un servicio necesita enviar pequeños mensajes a varios clientes simultáneamente.Una aplicación de cotización bursátil es un ejemplo de este tipo de servicio.  
  
## Implementar una aplicación de multidifusión  
 Para implementar una aplicación de multidifusión, defina un contrato de servicio y para cada componente de software que necesite responder a los mensajes de multidifusión, implemente el contrato de servicio.Por ejemplo, una aplicación de cotización bursátil podría definir un contrato de servicio:  
  
```  
// Shared contracts between the client and the service  
    [ServiceContract]  
    interface IStockTicker  
    {  
        [OperationContract(IsOneWay = true)]  
        void SendStockInfo(StockInfo[] stockInfo);  
    }  
  
    [DataContract]  
    class StockInfo  
    {  
        [DataMember]  
        public string Symbol;  
  
        [DataMember]  
        public float Price;  
  
        public StockInfo(string symbol, float price)  
        {  
            this.Symbol = symbol;  
            this.Price = price;  
        }  
    }  
  
```  
  
 Cada aplicación que desea recibir mensajes de multidifusión debe hospedar un servicio que expone esta interfaz.Por ejemplo, aquí tiene un ejemplo de código que muestra cómo recibir mensajes de multidifusión:  
  
```  
// Service Address  
            string serviceAddress = "soap.udp://224.0.0.1:40000";  
            // Binding  
            UdpBinding myBinding = new UdpBinding();  
            // Host  
            ServiceHost host = new ServiceHost(typeof  
                (StockTickerService), new Uri(serviceAddress));  
            // Add service endpoint  
            host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);  
            // Openup the service host  
            host.Open();  
  
            Console.WriteLine("Start receiving stock information");  
            Console.ReadLine();  
  
```  
  
 La aplicación especifica la dirección UDP en la que todos los servicios escucharán.Se crea un nuevo <xref:System.ServiceModel.ServiceHost> y se expone un extremo de servicio mediante <xref:System.ServiceModel.UdpBinding>.<xref:System.ServiceModel.ServiceHost> se abre y empezará a escuchar los mensajes entrantes.  
  
 En este tipo de escenario es el cliente quien envía realmente mensajes de multidifusión.Cada servicio que está escuchando en la dirección UDP correcta recibirá los mensajes de multidifusión.A continuación se muestra un ejemplo de un cliente que envía mensajes de multidifusión:  
  
```  
// Multicast Address  
            string serviceAddress = "soap.udp://224.0.0.1:40000";  
  
            // Binding  
            UdpBinding myBinding = new UdpBinding();  
  
            // Channel factory  
            ChannelFactory<IStockTicker> factory  
                = new ChannelFactory<IStockTicker>(myBinding,  
                            new EndpointAddress(serviceAddress));  
  
            // Call service  
            IStockTicker proxy = factory.CreateChannel();  
  
            while (true)  
            {  
                // This will continue to mulicast stock information   
                proxy.SendStockInfo(GetStockInfo());  
                Console.WriteLine(String.Format("sent stock info at {0}", DateTime.Now));  
                // Wait for one second before sending another update  
                System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));  
            }  
  
```  
  
 Este código genera información bursátil y usa el contrato de servicio IStockTicker para enviar mensajes de multidifusión para llamar a servicios que escuchan en la dirección UDP correcta.  
  
### Mensajería UDP y de confianza  
 El enlace UDP no admite mensajería de confianza debido a la naturaleza ligera del protocolo UDP.Si necesita confirmar que los mensajes son recibidos por un extremo remoto, use un transporte que admita mensajería de confianza como HTTP o TCP.Para obtener más información sobre la mensajería confiable, vea http:\/\/go.microsoft.com\/fwlink\/?LinkId\=231830.  
  
### Mensajería bidireccional de multidifusión  
 Mientras que los mensajes de multidifusión suelen ser unidireccionales, el UdpBinding admite intercambio de mensajes de solicitud y respuesta.Los mensajes enviados mediante el transporte UDP contienen direcciones From y To.Se ha de tener cuidado al usar la dirección From porque podría cambiarse malintencionadamente en la ruta.La dirección se puede comprobar mediante el código siguiente:  
  
```  
if (address.AddressFamily == AddressFamily.InterNetwork)  
          {  
              // IPv4  
              byte[] addressBytes = address.GetAddressBytes();  
              return ((addressBytes[0] & 0xE0) == 0xE0);  
          }  
          else  
          {  
              // IPv6   
              return address.IsIPv6Multicast;  
          }  
  
```  
  
 Este código comprueba el primer byte de la dirección From para ver si contiene 0xE0, lo que significa que la dirección es una dirección de multidifusión.  
  
### Consideraciones de seguridad  
 Al escuchar mensajes de multidifusión se envía un paquete ICMP al enrutador para notificarle que está escuchando en la dirección de multidifusión.Cualquier usuario de la subred local que tenga permisos podría escuchar estos tipos de paquetes y determinar en qué dirección de multidifusión y puerto se está escuchando.  
  
 No use la dirección IP del remitente para ningún propósito de seguridad.Esta información se puede suplantar y puede hacer que una aplicación envíe respuestas al equipo incorrecto.Una manera de resolver esta amenaza es habilitar la seguridad de nivel de mensaje.En el nivel de red también se puede usar IPsec \(protocolo de seguridad de Internet\) o NAP \(Protección de acceso a redes\).