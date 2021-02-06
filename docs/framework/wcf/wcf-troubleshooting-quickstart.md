---
description: 'Más información acerca de: Inicio rápido de solución de problemas de WCF'
title: Inicio rápido de solución de problemas de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: 686b008752704ed54700d9c49e2df71f9fc3fd98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631663"
---
# <a name="wcf-troubleshooting-quickstart"></a><span data-ttu-id="30282-103">Inicio rápido de solución de problemas de WCF</span><span class="sxs-lookup"><span data-stu-id="30282-103">WCF Troubleshooting Quickstart</span></span>

<span data-ttu-id="30282-104">En este tema se enumeran muchos problemas conocidos que los clientes han detectado al desarrollar clientes y servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="30282-104">This topic lists a number of known issues customers have run into while developing WCF clients and services.</span></span> <span data-ttu-id="30282-105">Si el problema que tiene no aparece en esta lista, se recomienda que configure la traza del servicio.</span><span class="sxs-lookup"><span data-stu-id="30282-105">If the issue you are running into is not in this list, we recommend you configure tracing for your service.</span></span> <span data-ttu-id="30282-106">De esta forma, se genera un archivo de seguimiento que puede ver con el visor de archivos de seguimiento y obtiene información detallada sobre las excepciones que se pueden producir en el servicio.</span><span class="sxs-lookup"><span data-stu-id="30282-106">This will generate a trace file that you can view with the trace file viewer and get detailed information about exceptions that may be occurring within the service.</span></span> <span data-ttu-id="30282-107">Para obtener más información sobre la configuración del seguimiento, consulte [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="30282-107">For more information on configuring tracing, see: [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="30282-108">Para obtener más información sobre cómo usar el visor de archivos de seguimiento, consulte [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="30282-108">For more information on the trace file viewer, see: [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span></span>  
  
1. [<span data-ttu-id="30282-109">Después de instalar Windows 7 e IIS, cuando intente explorar un servicio WCF puede obtener el mensaje de error siguiente: HTTP Error 404.3 – no encontrado</span><span class="sxs-lookup"><span data-stu-id="30282-109">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>](#bkmk_0)  
  
     <span data-ttu-id="30282-110">Error HTTP 404.3 – No encontrada. La página que solicita no puede presentarse debido a la configuración de la extensión.</span><span class="sxs-lookup"><span data-stu-id="30282-110">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="30282-111">Si la página es un script, agregue un controlador.</span><span class="sxs-lookup"><span data-stu-id="30282-111">If the page is a script, add a handler.</span></span> <span data-ttu-id="30282-112">Si se descarga el archivo, agregue un mapa MIME.</span><span class="sxs-lookup"><span data-stu-id="30282-112">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="30282-113">Error detallado InformationModule StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="30282-113">Detailed Error InformationModule StaticFileModule.</span></span>  
  
2. [<span data-ttu-id="30282-114">A veces, recibo un MessageSecurityException en la segunda solicitud si el cliente está inactivo durante un tiempo después de la primera solicitud. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-114">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request. What is happening?</span></span>](#BKMK_q1)  
  
3. [<span data-ttu-id="30282-115">Mi servicio empieza a rechazar nuevos clientes después de que unos 10 clientes interactúen con él. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-115">My service starts to reject new clients after about 10 clients are interacting with it. What is happening?</span></span>](#BKMK_q2)  
  
4. [<span data-ttu-id="30282-116">¿Puedo cargar mi configuración de servicio desde otra parte que no sea el archivo de configuración de la aplicación WCF?</span><span class="sxs-lookup"><span data-stu-id="30282-116">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>](#BKMK_q3)  
  
5. [<span data-ttu-id="30282-117">Mi servicio y cliente funcionan bien, pero no puedo conseguir que funcionen cuando el cliente está en otro equipo. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-117">My service and client work great, but I can’t get them to work when the client is on another computer? What’s happening?</span></span>](#BKMK_q4)  
  
6. [<span data-ttu-id="30282-118">Cuando se inicia una FaultException \<Exception> en la que el tipo es una excepción, siempre se recibe un tipo de FaultException general en el cliente y no el tipo genérico. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-118">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type. What’s happening?</span></span>](#BKMK_q5)  
  
7. [<span data-ttu-id="30282-119">Parece que las operaciones unidireccionales y de solicitud-respuesta devuelven aproximadamente la misma velocidad cuando la respuesta no contiene datos. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-119">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data. What's happening?</span></span>](#BKMK_q6)  
  
8. [<span data-ttu-id="30282-120">Estoy usando un certificado X. 509 con mi servicio y obtengo System. Security. Cryptography. CryptographicException. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-120">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException. What’s happening?</span></span>](#BKMK_q77)  
  
9. [<span data-ttu-id="30282-121">He cambiado el primer parámetro de una operación de mayúsculas a minúsculas; ahora mi cliente produce una excepción. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-121">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception. What's happening?</span></span>](#BKMK_q88)  
  
10. [<span data-ttu-id="30282-122">Estoy usando una de las herramientas de seguimiento y obtengo un EndpointNotFoundException. ¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-122">I’m using one of my tracing tools and I get an EndpointNotFoundException. What’s happening?</span></span>](#BKMK_q99)  
  
11. [<span data-ttu-id="30282-123">Al llamar a una aplicación web HTTP de WCF desde una aplicación SOAP de WCF, el servicio devuelve el siguiente error: 405 Método no permitido</span><span class="sxs-lookup"><span data-stu-id="30282-123">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>](#BK_MK99)  
  
 [<span data-ttu-id="30282-124">¿Cuál es la dirección base? ¿Cómo se relaciona con una dirección de extremo?</span><span class="sxs-lookup"><span data-stu-id="30282-124">What is the base address? How does it relate to an endpoint address?</span></span>](#BKMK_q10)  
  
<a name="bkmk_0"></a>

## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a><span data-ttu-id="30282-125">Después de instalar Windows 7 e IIS, cuando intente explorar un servicio WCF puede obtener el mensaje de error siguiente: HTTP Error 404.3 – no encontrado</span><span class="sxs-lookup"><span data-stu-id="30282-125">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>  

 <span data-ttu-id="30282-126">El mensaje de error completo es:</span><span class="sxs-lookup"><span data-stu-id="30282-126">The full error message is:</span></span>  
  
 <span data-ttu-id="30282-127">Error HTTP 404.3 – No encontrada. La página que solicita no puede presentarse debido a la configuración de la extensión.</span><span class="sxs-lookup"><span data-stu-id="30282-127">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="30282-128">Si la página es un script, agregue un controlador.</span><span class="sxs-lookup"><span data-stu-id="30282-128">If the page is a script, add a handler.</span></span> <span data-ttu-id="30282-129">Si se descarga el archivo, agregue un mapa MIME.</span><span class="sxs-lookup"><span data-stu-id="30282-129">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="30282-130">Error detallado InformationModule StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="30282-130">Detailed Error InformationModule StaticFileModule.</span></span>  
  
 <span data-ttu-id="30282-131">Este mensaje de error se produce cuando "Windows Communication Foundation activación HTTP" no se establece explícitamente en el panel de control.</span><span class="sxs-lookup"><span data-stu-id="30282-131">This error message occurs when "Windows Communication Foundation HTTP Activation" is not explicitly set in the Control Panel.</span></span> <span data-ttu-id="30282-132">Para establecer esta configuración, vaya al panel de control y haga clic en programas en la esquina inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="30282-132">To set this go to the Control Panel, click Programs in the lower left-hand corner of the window.</span></span> <span data-ttu-id="30282-133">Haga clic en Activar o desactivar las características de Windows.</span><span class="sxs-lookup"><span data-stu-id="30282-133">Click Turn Windows features on or off.</span></span> <span data-ttu-id="30282-134">Expanda el elemento con la etiqueta Microsoft .NET Framework 3.5.1, seleccione Activación HTTP de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="30282-134">Expand Microsoft .NET Framework 3.5.1 and select Windows Communication Foundation HTTP Activation.</span></span>  
  
<a name="BKMK_q1"></a>

## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a><span data-ttu-id="30282-135">A veces recibo una excepción MessageSecurityException en la segunda solicitud si mi cliente está inactivo durante algún tiempo después de la primera solicitud.</span><span class="sxs-lookup"><span data-stu-id="30282-135">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request.</span></span> <span data-ttu-id="30282-136">¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-136">What is happening?</span></span>  

 <span data-ttu-id="30282-137">Se puede producir un error en la segunda solicitud principalmente por dos razones: (1) se ha agotado de tiempo de espera de la sesión o (2) se recicla el servidor web que está hospedando el servicio.</span><span class="sxs-lookup"><span data-stu-id="30282-137">The second request can fail primarily for two reasons: (1) the session has timed out or (2) the Web server that is hosting the service is recycled.</span></span> <span data-ttu-id="30282-138">En el primer caso, la sesión es válida hasta que se agota el tiempo de espera del servicio. Cuando el servicio no recibe una solicitud del cliente dentro del período de tiempo especificado en el enlace del servicio ( <xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A> ), el servicio finaliza la sesión de seguridad.</span><span class="sxs-lookup"><span data-stu-id="30282-138">In the first case, the session is valid until the service times out. When the service does not receive a request from the client within the period of time specified in the service's binding (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), the service terminates the security session.</span></span> <span data-ttu-id="30282-139">Los siguientes mensajes del cliente producen <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="30282-139">Subsequent client messages result in the <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="30282-140">El cliente debe restablecer una sesión segura con el servicio para enviar los futuros mensajes o utilizar un token de contexto de seguridad con estado.</span><span class="sxs-lookup"><span data-stu-id="30282-140">The client must re-establish a secure session with the service to send future messages or use a stateful security context token.</span></span> <span data-ttu-id="30282-141">Los tokens de contexto de seguridad con estado también permiten que una sesión segura sobreviva a un servidor web que se recicla.</span><span class="sxs-lookup"><span data-stu-id="30282-141">Stateful security context tokens also allow a secure session to survive a Web server being recycled.</span></span> <span data-ttu-id="30282-142">Para obtener más información sobre el uso de tokens de contexto seguro con estado en una sesión segura, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="30282-142">For more information about using stateful secure context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span> <span data-ttu-id="30282-143">También puede deshabilitar las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="30282-143">Alternatively, you can disable secure sessions.</span></span> <span data-ttu-id="30282-144">Al usar el [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) enlace, puede establecer la `establishSecurityContext` propiedad en `false` para deshabilitar las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="30282-144">When you use the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) binding, you can set the `establishSecurityContext` property to `false` to disable secure sessions.</span></span> <span data-ttu-id="30282-145">Para deshabilitar las sesiones seguras para otros enlaces, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="30282-145">To disable secure sessions for other bindings, you must create a custom binding.</span></span> <span data-ttu-id="30282-146">Para obtener más información sobre cómo crear un enlace personalizado, consulte [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="30282-146">For details about creating a custom binding, see [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="30282-147">Antes de aplicar cualquiera de estas opciones, debe entender los requisitos de seguridad de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="30282-147">Before you apply any of these options, you must understand your application's security requirements.</span></span>  
  
<a name="BKMK_q2"></a>

## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a><span data-ttu-id="30282-148">Mi servicio empieza a rechazar nuevos clientes cuando interactúa con unos 10 clientes.</span><span class="sxs-lookup"><span data-stu-id="30282-148">My service starts to reject new clients after about 10 clients are interacting with it.</span></span> <span data-ttu-id="30282-149">¿Qué pasa?</span><span class="sxs-lookup"><span data-stu-id="30282-149">What is happening?</span></span>  

 <span data-ttu-id="30282-150">De forma predeterminada, los servicios pueden tener solo 10 sesiones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="30282-150">By default, services can have only 10 concurrent sessions.</span></span> <span data-ttu-id="30282-151">Por tanto, si los enlaces del servicio utilizan sesiones, el servicio acepta nuevas conexiones de cliente hasta que alcance ese numero, después del cual rechaza nuevas conexiones de cliente hasta que finaliza una de las sesiones actuales.</span><span class="sxs-lookup"><span data-stu-id="30282-151">Therefore, if the service bindings use sessions, the service accepts new client connections until it reaches that number, after which it refuses new client connections until one of the current sessions ends.</span></span> <span data-ttu-id="30282-152">Puede admitir más clientes de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="30282-152">You can support more clients in a number of ways.</span></span> <span data-ttu-id="30282-153">Si su servicio no requiere sesiones, no utilice un enlace con sesión.</span><span class="sxs-lookup"><span data-stu-id="30282-153">If your service does not require sessions, do not use a sessionful binding.</span></span> <span data-ttu-id="30282-154">(Para obtener más información, consulte [uso de sesiones](using-sessions.md)). Otra opción es aumentar el límite de sesión cambiando el valor de la <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> propiedad al número adecuado para su circunstancia.</span><span class="sxs-lookup"><span data-stu-id="30282-154">(For more information, see [Using Sessions](using-sessions.md).) Another option is to increase the session limit by changing the value of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> property to the number appropriate to your circumstance.</span></span>  
  
<a name="BKMK_q3"></a>

## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a><span data-ttu-id="30282-155">¿Puedo cargar mi configuración de servicio desde otra parte que no sea el archivo de configuración de la aplicación WCF?</span><span class="sxs-lookup"><span data-stu-id="30282-155">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>  

 <span data-ttu-id="30282-156">Sí, sin embargo, tiene que crear una clase <xref:System.ServiceModel.ServiceHost> personalizada que invalide el método <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="30282-156">Yes, however, you have to create a custom <xref:System.ServiceModel.ServiceHost> class that overrides the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method.</span></span> <span data-ttu-id="30282-157">Dentro de ese método, puede llamar a la base para cargar primero la configuración (si desea también cargar la información de configuración estándar), pero también puede reemplazar completamente el sistema de carga de configuración.</span><span class="sxs-lookup"><span data-stu-id="30282-157">Inside that method, you can call the base to load configuration first (if you want to load the standard configuration information as well) but you can also entirely replace the configuration loading system.</span></span> <span data-ttu-id="30282-158">Si desea cargar la configuración desde un archivo de configuración diferente del archivo de configuración de la aplicación, debe analizar el archivo de configuración y cargar la configuración.</span><span class="sxs-lookup"><span data-stu-id="30282-158">If you want to load configuration from a configuration file that is different from the application configuration file, you must parse the configuration file yourself and load the configuration.</span></span>  
  
 <span data-ttu-id="30282-159">El siguiente ejemplo de código muestra cómo invalidar el método <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> y configurar directamente un extremo.</span><span class="sxs-lookup"><span data-stu-id="30282-159">The following code example shows how to override the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method and directly configure an endpoint.</span></span>  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>

## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a><span data-ttu-id="30282-160">Mi servicio y cliente funcionan muy bien, pero no puedo conseguir que funcionen cuando el cliente está en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="30282-160">My service and client work great, but I can’t get them to work when the client is on another computer?</span></span> <span data-ttu-id="30282-161">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-161">What’s happening?</span></span>  

 <span data-ttu-id="30282-162">Dependiendo de la excepción, puede haber varios problemas:</span><span class="sxs-lookup"><span data-stu-id="30282-162">Depending upon the exception, there may be several issues:</span></span>  
  
- <span data-ttu-id="30282-163">Puede que necesite cambiar las direcciones de extremo del cliente al nombre de host y no el "localhost".</span><span class="sxs-lookup"><span data-stu-id="30282-163">You might need to change the client endpoint addresses to the host name and not "localhost".</span></span>  
  
- <span data-ttu-id="30282-164">Puede que necesite abrir el puerto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30282-164">You might need to open the port to the application.</span></span> <span data-ttu-id="30282-165">Para obtener más información, consulte [Firewall Instructions](./samples/firewall-instructions.md) en los ejemplos de SDK.</span><span class="sxs-lookup"><span data-stu-id="30282-165">For details, see [Firewall Instructions](./samples/firewall-instructions.md) from the SDK samples.</span></span>  
  
- <span data-ttu-id="30282-166">Para otros posibles problemas, vea el tema ejemplos en [el que se ejecutan los ejemplos de Windows Communication Foundation](./samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30282-166">For other possible issues, see the samples topic [Running the Windows Communication Foundation Samples](./samples/running-the-samples.md).</span></span>  
  
- <span data-ttu-id="30282-167">Si su cliente está utilizando las credenciales de Windows y la excepción es <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="30282-167">If your client is using Windows credentials and the exception is a <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos as follows.</span></span>  
  
    1. <span data-ttu-id="30282-168">Agregue las credenciales de identidad al elemento de extremo en el archivo del cliente App.config:</span><span class="sxs-lookup"><span data-stu-id="30282-168">Add the identity credentials to the endpoint element in the client’s App.config file:</span></span>  
  
        ```xml
        <endpoint
          address="http://MyServer:8000/MyService/"
          binding="wsHttpBinding"
          bindingConfiguration="WSHttpBinding_IServiceExample"
          contract="IServiceExample"
          behaviorConfiguration="ClientCredBehavior"
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. <span data-ttu-id="30282-169">Ejecute el servicio autohospedado con la cuenta System o NetworkService.</span><span class="sxs-lookup"><span data-stu-id="30282-169">Run the self-hosted service under the System or NetworkService account.</span></span> <span data-ttu-id="30282-170">Puede ejecutar este comando para crear una ventana de comandos bajo la cuenta del sistema:</span><span class="sxs-lookup"><span data-stu-id="30282-170">You can run this command to create a command window under the System account:</span></span>  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. <span data-ttu-id="30282-171">Hospede el servicio bajo IIS (Servicios de Internet Information Services) (IIS) que, de forma predeterminada, utiliza la cuenta del nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="30282-171">Host the service under Internet Information Services (IIS), which, by default, uses the service principal name (SPN) account.</span></span>  
  
    4. <span data-ttu-id="30282-172">Registre un nuevo SPN con el dominio utilizando SetSPN.</span><span class="sxs-lookup"><span data-stu-id="30282-172">Register a new SPN with the domain using SetSPN.</span></span> <span data-ttu-id="30282-173">Para ello, debe ser un administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="30282-173">You need to be a domain administrator in order to do this.</span></span>  
  
 <span data-ttu-id="30282-174">Para obtener más información acerca del protocolo Kerberos, vea [conceptos de seguridad usados en WCF](./feature-details/security-concepts-used-in-wcf.md) y:</span><span class="sxs-lookup"><span data-stu-id="30282-174">For more information about the Kerberos protocol, see [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) and:</span></span>  
  
- [<span data-ttu-id="30282-175">Depuración de errores de autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="30282-175">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)  
  
- <span data-ttu-id="30282-176">[Registrar nombres principales de servicio de Kerberos mediante Http.sys](/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="30282-176">[Registering Kerberos Service Principal Names by Using Http.sys](/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span></span>  
  
- <span data-ttu-id="30282-177">[Kerberos Explained (Kerberos en detalle)](/previous-versions/windows/it-pro/windows-2000-server/bb742516(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="30282-177">[Kerberos Explained](/previous-versions/windows/it-pro/windows-2000-server/bb742516(v=technet.10))</span></span>  
  
<a name="BKMK_q5"></a>

## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a><span data-ttu-id="30282-178">Cuando se inicia una FaultException \<Exception> en la que el tipo es una excepción, siempre se recibe un tipo de FaultException general en el cliente y no el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="30282-178">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type.</span></span> <span data-ttu-id="30282-179">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-179">What’s happening?</span></span>  

 <span data-ttu-id="30282-180">Es muy recomendable que cree su propio tipo de datos de error personalizado y lo declare como tipo detallado en el contrato de error.</span><span class="sxs-lookup"><span data-stu-id="30282-180">It is highly recommended that you create your own custom error data type and declare that as the detail type in your fault contract.</span></span> <span data-ttu-id="30282-181">La razón es que utilizando los tipos de excepción proporcionados por el sistema:</span><span class="sxs-lookup"><span data-stu-id="30282-181">The reason is that using system-provided exception types:</span></span>  
  
- <span data-ttu-id="30282-182">Crea una dependencia de tipo que quita uno de los puntos fuertes más grandes de las aplicaciones orientadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="30282-182">Creates a type dependency that removes one of the biggest strengths of service-oriented applications.</span></span>  
  
- <span data-ttu-id="30282-183">No se puede esperar que las excepciones se serialicen de una manera estándar.</span><span class="sxs-lookup"><span data-stu-id="30282-183">Cannot depend upon exceptions serializing in a standard way.</span></span> <span data-ttu-id="30282-184">Puede que algunas, como <xref:System.Security.SecurityException>no se puedan serializar en absoluto.</span><span class="sxs-lookup"><span data-stu-id="30282-184">Some—like <xref:System.Security.SecurityException>—may not be serializable at all.</span></span>  
  
- <span data-ttu-id="30282-185">Expone los detalles internos de la implementación a los clientes.</span><span class="sxs-lookup"><span data-stu-id="30282-185">Exposes internal implementation details to clients.</span></span> <span data-ttu-id="30282-186">Para obtener más información, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="30282-186">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
 <span data-ttu-id="30282-187">Si está depurando una aplicación, sin embargo, puede serializar información de excepción y devolverla al cliente utilizando la clase <xref:System.ServiceModel.Description.ServiceDebugBehavior> .</span><span class="sxs-lookup"><span data-stu-id="30282-187">If you are debugging an application, however, you can serialize exception information and return it to the client by using the <xref:System.ServiceModel.Description.ServiceDebugBehavior> class.</span></span>  
  
<a name="BKMK_q6"></a>

## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a><span data-ttu-id="30282-188">Parece que las operaciones unidireccionales y las operaciones solicitud-respuesta se devuelven aproximadamente a la misma velocidad cuando la respuesta no contiene datos.</span><span class="sxs-lookup"><span data-stu-id="30282-188">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data.</span></span> <span data-ttu-id="30282-189">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-189">What's happening?</span></span>  

 <span data-ttu-id="30282-190">Especificando que una operación es unidireccional solo significa que el contrato de operación acepta un mensaje de entrada y no devuelve un mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="30282-190">Specifying that an operation is one way means only that the operation contract accepts an input message and does not return an output message.</span></span> <span data-ttu-id="30282-191">En WCF, todas las invocaciones de cliente devuelven cuando los datos de salida se han escrito en la conexión o se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="30282-191">In WCF, all client invocations return when the outbound data has been written to the wire or an exception is thrown.</span></span> <span data-ttu-id="30282-192">Las operaciones unidireccionales funcionan de la misma manera y se pueden iniciar si el servicio no se puede localizar o se pueden bloquear si el servicio no está preparado para aceptar los datos de la red.</span><span class="sxs-lookup"><span data-stu-id="30282-192">One-way operations work the same way, and they can throw if the service cannot be located or block if the service is not prepared to accept the data from the network.</span></span> <span data-ttu-id="30282-193">Normalmente, en WCF, esto da como resultado llamadas unidireccionales que vuelven al cliente más rápidamente que la solicitud-respuesta; sin embargo, las condiciones que ralentizan el envío de los datos salientes a través de la red ralentizan las operaciones unidireccionales, así como las operaciones de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="30282-193">Typically in WCF, this results in one-way calls returning to the client more quickly than request-reply; but any condition that slows the sending of the outbound data over the network slows one-way operations as well as request-reply operations.</span></span> <span data-ttu-id="30282-194">Para obtener más información, vea [servicios unidireccionales](./feature-details/one-way-services.md) y [acceso a servicios mediante un cliente WCF](./feature-details/accessing-services-using-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="30282-194">For more information, see [One-Way Services](./feature-details/one-way-services.md) and [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md).</span></span>  
  
<a name="BKMK_q77"></a>

## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a><span data-ttu-id="30282-195">Estoy usando un certificado X.509 con mi servicio y obtengo una excepción System.Security.Cryptography.CryptographicException.</span><span class="sxs-lookup"><span data-stu-id="30282-195">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException.</span></span> <span data-ttu-id="30282-196">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-196">What’s happening?</span></span>  

 <span data-ttu-id="30282-197">Esto se produce normalmente después de cambiar la cuenta de usuario bajo la cual se ejecuta el proceso de trabajo de IIS.</span><span class="sxs-lookup"><span data-stu-id="30282-197">This commonly occurs after changing the user account under which the IIS worker process runs.</span></span> <span data-ttu-id="30282-198">Por ejemplo, en Windows XP, si cambia la cuenta de usuario predeterminada en la que se ejecuta la Aspnet_wp.exe de ASPNET a una cuenta de usuario personalizada, puede ver este error.</span><span class="sxs-lookup"><span data-stu-id="30282-198">For example, in Windows XP, if you change the default user account that the Aspnet_wp.exe runs under from ASPNET to a custom user account, you may see this error.</span></span> <span data-ttu-id="30282-199">Si utiliza una clave privada, el proceso que utiliza necesitará tener los permisos para tener acceso al archivo que almacena esa clave.</span><span class="sxs-lookup"><span data-stu-id="30282-199">If using a private key, the process that uses it will need to have permissions to access the file storing that key.</span></span>  
  
 <span data-ttu-id="30282-200">Si éste es el caso, debe dar los privilegios de acceso de lectura a la cuenta del proceso para el archivo que contiene la clave privada.</span><span class="sxs-lookup"><span data-stu-id="30282-200">If this is the case, you must give read access privileges to the process's account for the file containing the private key.</span></span> <span data-ttu-id="30282-201">Por ejemplo, si el proceso de trabajo de IIS se está ejecutando bajo la cuenta Bob, entonces, necesitará proporcionar a Bob el acceso de lectura al archivo que contiene la clave privada.</span><span class="sxs-lookup"><span data-stu-id="30282-201">For example, if the IIS worker process is running under the Bob account, then you will need to give Bob read access to the file containing the private key.</span></span>  
  
 <span data-ttu-id="30282-202">Para obtener más información acerca de cómo proporcionar a la cuenta de usuario correcta acceso al archivo que contiene la clave privada para un certificado X. 509 concreto, consulte [Cómo: hacer que los certificados x. 509 estén accesibles para WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="30282-202">For more information about how to give the correct user account access to the file that contains the private key for a specific X.509 certificate, see [How to: Make X.509 Certificates Accessible to WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span></span>  
  
<a name="BKMK_q88"></a>

## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a><span data-ttu-id="30282-203">He cambiado el primer parámetro de una operación de mayúsculas a minúsculas; ahora mi cliente produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="30282-203">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception.</span></span> <span data-ttu-id="30282-204">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-204">What's happening?</span></span>  

 <span data-ttu-id="30282-205">Los valores de los nombres de parámetro en la firma de la operación forman parte del contrato y distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="30282-205">The values of the parameter names in the operation signature are part of the contract and are case-sensitive.</span></span> <span data-ttu-id="30282-206">Utilice el atributo <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> cuando necesite distinguir entre el nombre de parámetro local y los metadatos que describen la operación para las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="30282-206">Use the <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> attribute when you need to distinguish between the local parameter name and the metadata that describes the operation for client applications.</span></span>  
  
<a name="BKMK_q99"></a>

## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a><span data-ttu-id="30282-207">Estoy utilizando una de mis herramientas de traza y obtengo la excepción EndpointNotFoundException.</span><span class="sxs-lookup"><span data-stu-id="30282-207">I’m using one of my tracing tools and I get an EndpointNotFoundException.</span></span> <span data-ttu-id="30282-208">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="30282-208">What’s happening?</span></span>  

 <span data-ttu-id="30282-209">Si usa una herramienta de seguimiento que no es el mecanismo de seguimiento de WCF proporcionado por el sistema y recibe un mensaje <xref:System.ServiceModel.EndpointNotFoundException> que indica que se ha producido un error de coincidencia de filtro de direcciones, debe utilizar la <xref:System.ServiceModel.Description.ClientViaBehavior> clase para dirigir los mensajes a la utilidad de seguimiento y hacer que la utilidad redirija esos mensajes a la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="30282-209">If you are using a tracing tool that is not the system-provided WCF tracing mechanism and you receive an <xref:System.ServiceModel.EndpointNotFoundException> that indicates that there was an address filter mismatch, you need to use the <xref:System.ServiceModel.Description.ClientViaBehavior> class to direct the messages to the tracing utility and have the utility redirect those messages to the service address.</span></span> <span data-ttu-id="30282-210">La clase <xref:System.ServiceModel.Description.ClientViaBehavior> modifica `Via` que dirige el encabezado para especificar la siguiente dirección de red de forma independiente con respecto al receptor último, indicado por `To` que dirige el encabezado.</span><span class="sxs-lookup"><span data-stu-id="30282-210">The <xref:System.ServiceModel.Description.ClientViaBehavior> class alters the `Via` addressing header to specify the next network address separately from the ultimate receiver, indicated by the `To` addressing header.</span></span> <span data-ttu-id="30282-211">Cuando haga esto, sin embargo, no cambie la dirección del extremo, la cual se utiliza para establecer el valor `To` .</span><span class="sxs-lookup"><span data-stu-id="30282-211">When doing this, however, do not change the endpoint address, which is used to establish the `To` value.</span></span>  
  
 <span data-ttu-id="30282-212">El ejemplo de código siguiente muestra un ejemplo de archivo de configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="30282-212">The following code example shows an example client configuration file.</span></span>  
  
```xml
<endpoint
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"
  contract="IMyContract"
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>

## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a><span data-ttu-id="30282-213">¿Cuál es la dirección base?</span><span class="sxs-lookup"><span data-stu-id="30282-213">What is the base address?</span></span> <span data-ttu-id="30282-214">¿Cómo se relaciona con una dirección de extremo?</span><span class="sxs-lookup"><span data-stu-id="30282-214">How does it relate to an endpoint address?</span></span>  

 <span data-ttu-id="30282-215">Una dirección base es la dirección de raíz para una clase <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="30282-215">A base address is the root address for a <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="30282-216">De forma predeterminada, si agrega una clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en su configuración de servicio, el lenguaje de descripción de servicios Web (WSDL) para todos los extremos que publica el host se recupera de la dirección base de HTTP, más cualquier dirección relativa proporcionada al comportamiento de los metadatos, más "? wsdl".</span><span class="sxs-lookup"><span data-stu-id="30282-216">By default, if you add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class into your service configuration, the Web Services Description Language (WSDL) for all endpoints the host publishes are retrieved from the HTTP base address, plus any relative address provided to the metadata behavior, plus "?wsdl".</span></span> <span data-ttu-id="30282-217">Si está familiarizado con ASP.NET e IIS, la dirección base es equivalente al directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="30282-217">If you are familiar with ASP.NET and IIS, the base address is equivalent to the virtual directory.</span></span>  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a><span data-ttu-id="30282-218">Compartir un puerto entre un extremo de servicio y un extremo mex mediante NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="30282-218">Sharing a port between a service endpoint and a mex endpoint using the NetTcpBinding</span></span>  

 <span data-ttu-id="30282-219">Si especifica la dirección base para un servicio como net.tcp://MyServer:8080/MyService y agrega los siguientes extremos:</span><span class="sxs-lookup"><span data-stu-id="30282-219">If you specify the base address for a service as net.tcp://MyServer:8080/MyService and add the following endpoints:</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="30282-220">Y si modifica uno de los valores de NetTcpBinding como se muestra en el siguiente fragmento de código de configuración:</span><span class="sxs-lookup"><span data-stu-id="30282-220">And if you modify one of the NetTcpBinding settings as shown in the following configuration snippet:</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="30282-221">Verá un error como el siguiente: Excepción no controlada: System.ServiceModel.AddressAlreadyInUseException: Ya hay una escucha en el extremo IP0.0.0.0:9000. Para solucionar este error, especifique una dirección URL completa con un puerto diferente para el extremo MEX, como se muestra en el siguiente fragmento de código de configuración:</span><span class="sxs-lookup"><span data-stu-id="30282-221">You will see an error like the following: Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000 You can work around this error by specifying a fully qualified URL with a different port for the MEX endpoint as shown in the following configuration snippet:</span></span>  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>

## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a><span data-ttu-id="30282-222">Al llamar a una aplicación web HTTP de WCF desde una aplicación SOAP de WCF, el servicio devuelve el siguiente error: 405 Método no permitido</span><span class="sxs-lookup"><span data-stu-id="30282-222">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>  

 <span data-ttu-id="30282-223">Llamar a una aplicación Web HTTP de WCF (un servicio que usa <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior> ) desde un servicio WCF puede generar la siguiente excepción: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` esta excepción se produce porque WCF sobrescribe el saliente <xref:System.ServiceModel.OperationContext> con el de entrada <xref:System.ServiceModel.OperationContext> .</span><span class="sxs-lookup"><span data-stu-id="30282-223">Calling a WCF Web HTTP application (a service that uses the <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior>) from a WCF service may generate the following exception: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` This exception occurs because WCF overwrites the outgoing <xref:System.ServiceModel.OperationContext> with the incoming <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="30282-224">Para solucionar este problema, cree un <xref:System.ServiceModel.OperationContextScope> dentro de la operación del servicio Web http de WCF.</span><span class="sxs-lookup"><span data-stu-id="30282-224">To solve this problem, create an <xref:System.ServiceModel.OperationContextScope> within the WCF Web HTTP service operation.</span></span> <span data-ttu-id="30282-225">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="30282-225">For example:</span></span>  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="30282-226">Vea también</span><span class="sxs-lookup"><span data-stu-id="30282-226">See also</span></span>

- [<span data-ttu-id="30282-227">Depuración de errores de autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="30282-227">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)
