---
title: "C&#243;mo: Llamar a un servicio Web de forma asincr&#243;nica (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "llamadas asincrónicas"
  - "servicios Web, obtener acceso"
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Llamar a un servicio Web de forma asincr&#243;nica (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este ejemplo se adjunta un controlador a un evento de controlador asincrónico de servicios web para poder recuperar el resultado de una llamada de método asincrónico.  En este ejemplo se ha utilizado el servicio web DemoTemperatureService de http:\/\/www.xmethods.  net.  
  
 Cuando se hace referencia a un servicio web en el proyecto en el entorno de desarrollo integrado \(IDE\) de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], dicho servicio se agrega al objeto `My.WebServices` y el IDE genera una clase de proxy de cliente para acceder al servicio web especificado.  
  
 La clase de proxy permite llamar sincrónicamente a los métodos de servicio web, mientras la aplicación espera a que la función finalice.  El proxy crea además otros miembros para ayudar a llamar al método asincrónicamente.  Por cada función de servicio web, *NombreDeFunciónDeServicioWeb*, el proxy crea una subrutina *NombreDeFunciónDeServicioWeb*`Async`, un evento *NombreDeFunciónDeServicioWeb*`Completed` y una clase *NombreDeFunciónDeServicioWeb*`CompletedEventArgs`.  En este ejemplo se muestra cómo usar los miembros asincrónicos para acceder a la función `getTemp` del servicio web DemoTemperatureService.  
  
> [!NOTE]
>  Este código no funciona en aplicaciones web, ya que ASP.NET no admite el objeto `My.WebServices`.  
  
### Para llamar a un servicio web asincrónicamente  
  
1.  Haga referencia al servicio web DemoTemperatureService de http:\/\/www.xmethods.  net.  La dirección es  
  
    ```  
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl  
    ```  
  
2.  Agregue un controlador de eventos para el evento `getTempCompleted`:  
  
    ```  
    Private Sub getTempCompletedHandler(ByVal sender As Object,   
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)  
  
        MsgBox("Temperature: " & e.Result)  
    End Sub  
    ```  
  
    > [!NOTE]
    >  La instrucción `Handles` no se puede usar para asociar un controlador de eventos con los eventos del objeto `My.WebServices`.  
  
3.  Agregue un campo para saber si el controlador de eventos se ha agregado al evento `getTempCompleted`:  
  
    ```  
    Private handlerAttached As Boolean = False  
    ```  
  
4.  Agregue un método para agregar el controlador de eventos al evento `getTempCompleted` \(en caso necesario\) y para llamar al método `getTempAsynch`:  
  
    ```  
    Sub CallGetTempAsync(ByVal zipCode As Integer)  
        If Not handlerAttached Then  
            AddHandler My.WebServices.  
                TemperatureService.getTempCompleted,   
                AddressOf Me.TS_getTempCompleted  
            handlerAttached = True  
        End If  
        My.WebServices.TemperatureService.getTempAsync(zipCode)  
    End Sub  
    ```  
  
     Llame al método `CallGetTempAsync` para llamar al método web `getTemp` asincrónicamente.  Cuando el método web finalice, su valor devuelto se pasa al controlador de eventos `getTempCompletedHandler`.  
  
## Vea también  
 [Acceso a los servicios Web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)   
 [My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)