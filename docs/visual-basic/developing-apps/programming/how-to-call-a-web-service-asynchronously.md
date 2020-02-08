---
title: Procedimiento Llamada a un servicio web de forma asincrónica
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: d288cc1f2991a8f504dc9f1b206bba76fa378b75
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794564"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="bd8db-102">Procedimiento para llamar a un servicio web de forma asincrónica (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd8db-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>

<span data-ttu-id="bd8db-103">En este ejemplo se adjunta un controlador a un evento de controlador asincrónico de servicios web para poder recuperar el resultado de una llamada de método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="bd8db-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="bd8db-104">En este ejemplo se ha usado el servicio web DemoTemperatureService de `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-104">This example used the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span>

<span data-ttu-id="bd8db-105">Cuando se hace referencia a un servicio web en el proyecto en el entorno de desarrollo integrado (IDE) de Visual Studio, dicho servicio se agrega al objeto `My.WebServices` y el IDE genera una clase de proxy de cliente para obtener acceso al servicio web especificado.</span><span class="sxs-lookup"><span data-stu-id="bd8db-105">When you reference a Web service in your project in the Visual Studio Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>

<span data-ttu-id="bd8db-106">La clase de proxy permite llamar sincrónicamente a los métodos de servicio web, mientras la aplicación espera a que la función finalice.</span><span class="sxs-lookup"><span data-stu-id="bd8db-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="bd8db-107">El proxy crea además otros miembros para ayudar a llamar al método asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="bd8db-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="bd8db-108">Por cada función de servicio web, *NombreDeFunciónDeServicioWeb*, el proxy crea una subrutina *NombreDeFunciónDeServicioWeb*`Async`, un evento *NombreDeFunciónDeServicioWeb*`Completed` y una clase *NombreDeFunciónDeServicioWeb*`CompletedEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="bd8db-109">En este ejemplo se muestra cómo usar los miembros asincrónicos para acceder a la función `getTemp` del servicio web DemoTemperatureService.</span><span class="sxs-lookup"><span data-stu-id="bd8db-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>

> [!NOTE]
> <span data-ttu-id="bd8db-110">Este código no funciona en aplicaciones web, ya que ASP.NET no admite el objeto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>

## <a name="call-a-web-service-asynchronously"></a><span data-ttu-id="bd8db-111">Llamada a un servicio web de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="bd8db-111">Call a Web service asynchronously</span></span>

1. <span data-ttu-id="bd8db-112">Haga referencia al servicio web DemoTemperatureService de `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-112">Reference the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span> <span data-ttu-id="bd8db-113">La dirección es</span><span class="sxs-lookup"><span data-stu-id="bd8db-113">The address is</span></span>

    ```http
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. <span data-ttu-id="bd8db-114">Agregue un controlador de eventos para el evento `getTempCompleted`:</span><span class="sxs-lookup"><span data-stu-id="bd8db-114">Add an event handler for the `getTempCompleted` event:</span></span>

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > <span data-ttu-id="bd8db-115">La instrucción `Handles` no se puede usar para asociar un controlador de eventos con los eventos del objeto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>

3. <span data-ttu-id="bd8db-116">Agregue un campo para saber si el controlador de eventos se ha agregado al evento `getTempCompleted`:</span><span class="sxs-lookup"><span data-stu-id="bd8db-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. <span data-ttu-id="bd8db-117">Agregue un método para agregar el controlador de eventos al evento `getTempCompleted` (en caso necesario) y para llamar al método `getTempAsync`:</span><span class="sxs-lookup"><span data-stu-id="bd8db-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsync` method:</span></span>

    ```vb
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

    <span data-ttu-id="bd8db-118">Llame al método `getTemp` para llamar al método web `CallGetTempAsync` asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="bd8db-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="bd8db-119">Cuando el método web finalice, su valor devuelto se pasa al controlador de eventos `getTempCompletedHandler`.</span><span class="sxs-lookup"><span data-stu-id="bd8db-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd8db-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd8db-120">See also</span></span>

- [<span data-ttu-id="bd8db-121">Acceso a los servicios web de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bd8db-121">Accessing Application Web Services</span></span>](accessing-application-web-services.md)
- [<span data-ttu-id="bd8db-122">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="bd8db-122">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
