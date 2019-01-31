---
title: Procedimiento para llamar a un servicio web de forma asincrónica (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: 9127b0edce029f8b2944ddf692e85166ee8c89b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616152"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Procedimiento para llamar a un servicio web de forma asincrónica (Visual Basic)
En este ejemplo se adjunta un controlador a un evento de controlador asincrónico de servicios web para poder recuperar el resultado de una llamada de método asincrónico. En este ejemplo se ha usado el servicio web DemoTemperatureService de `http://www.xmethods.net`.  
  
 Cuando se hace referencia a un servicio web en el proyecto en el entorno de desarrollo integrado (IDE) de Visual Studio, dicho servicio se agrega al objeto `My.WebServices` y el IDE genera una clase de proxy de cliente para obtener acceso al servicio web especificado.  
  
 La clase de proxy permite llamar sincrónicamente a los métodos de servicio web, mientras la aplicación espera a que la función finalice. El proxy crea además otros miembros para ayudar a llamar al método asincrónicamente. Por cada función de servicio web, *NombreDeFunciónDeServicioWeb*, el proxy crea una subrutina *NombreDeFunciónDeServicioWeb*`Async`, un evento *NombreDeFunciónDeServicioWeb*`Completed` y una clase *NombreDeFunciónDeServicioWeb*`CompletedEventArgs`. En este ejemplo se muestra cómo usar los miembros asincrónicos para acceder a la función `getTemp` del servicio web DemoTemperatureService.  
  
> [!NOTE]
>  Este código no funciona en aplicaciones web, ya que ASP.NET no admite el objeto `My.WebServices`.  
  
### <a name="to-call-a-web-service-asynchronously"></a>Para llamar a un servicio web asincrónicamente  
  
1.  Haga referencia al servicio web DemoTemperatureService de `http://www.xmethods.net`. La dirección es  
  
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
  
4.  Agregue un método para agregar el controlador de eventos al evento `getTempCompleted` (en caso necesario) y para llamar al método `getTempAsynch`:  
  
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
  
     Llame al método `getTemp` para llamar al método web `CallGetTempAsync` asincrónicamente. Cuando el método web finalice, su valor devuelto se pasa al controlador de eventos `getTempCompletedHandler`.  
  
## <a name="see-also"></a>Vea también
- [Acceso a los servicios web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
- [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
