---
description: 'Más información acerca de: servicio de fachada de confianza'
title: Servicio de fachada confiable
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: aebfa89c47d5e8ea37e210b2d7b19afbe204a1a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685483"
---
# <a name="trusted-facade-service"></a><span data-ttu-id="7eba8-103">Servicio de fachada confiable</span><span class="sxs-lookup"><span data-stu-id="7eba8-103">Trusted Facade Service</span></span>

<span data-ttu-id="7eba8-104">Este ejemplo de escenario muestra cómo fluir la información de identidad del llamador de un servicio a otro utilizando la infraestructura de seguridad de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7eba8-104">This scenario sample demonstrates how to flow caller's identity information from one service to another using Windows Communication Foundation (WCF) security infrastructure.</span></span>  
  
 <span data-ttu-id="7eba8-105">Es un patrón de diseño común para exponer la funcionalidad proporcionada por un servicio a la red pública utilizando un servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-105">It is a common design pattern to expose the functionality provided by a service to the public network using a façade service.</span></span> <span data-ttu-id="7eba8-106">El servicio de fachada reside normalmente en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada) y se comunica con un servicio back-end que implementa la lógica comercial y tiene acceso a datos internos.</span><span class="sxs-lookup"><span data-stu-id="7eba8-106">The façade service typically resides in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet) and communicates with a backend service that implements the business logic and has access to internal data.</span></span> <span data-ttu-id="7eba8-107">El canal de comunicación entre el servicio de la fachada y el servicio back-end va a través de un firewall y se limita normalmente solo para un único propósito.</span><span class="sxs-lookup"><span data-stu-id="7eba8-107">The communication channel between the façade service and the backend service goes through a firewall and is usually limited for a single purpose only.</span></span>  
  
 <span data-ttu-id="7eba8-108">Este ejemplo consta de los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="7eba8-108">This sample consists of the following components:</span></span>  
  
- <span data-ttu-id="7eba8-109">Cliente de la calculadora</span><span class="sxs-lookup"><span data-stu-id="7eba8-109">Calculator client</span></span>  
  
- <span data-ttu-id="7eba8-110">Servicio de fachada de calculadora</span><span class="sxs-lookup"><span data-stu-id="7eba8-110">Calculator façade service</span></span>  
  
- <span data-ttu-id="7eba8-111">Servicio back-end de calculadora.</span><span class="sxs-lookup"><span data-stu-id="7eba8-111">Calculator backend service</span></span>  
  
 <span data-ttu-id="7eba8-112">El servicio de la fachada es responsable de validar la solicitud y autenticar el llamador.</span><span class="sxs-lookup"><span data-stu-id="7eba8-112">The façade service is responsible for validating the request and authenticating the caller.</span></span> <span data-ttu-id="7eba8-113">Después de la autenticación y validación correctas, reenvía la solicitud al servicio back-end utilizando el canal de comunicación controlado de la red perimetral a la red interna.</span><span class="sxs-lookup"><span data-stu-id="7eba8-113">After successful authentication and validation, it forwards the request to the backend service using the controlled communication channel from the perimeter network to the internal network.</span></span> <span data-ttu-id="7eba8-114">Como parte de la solicitud reenviada, el servicio de fachada incluye información sobre la identidad del llamador para que el servicio back-end pueda utilizar esta información en su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7eba8-114">As a part of the forwarded request, the façade service includes information about the caller's identity so that the backend service can use this information in its processing.</span></span> <span data-ttu-id="7eba8-115">La identidad del llamador se transmite utilizando un token de seguridad `Username` dentro del encabezado `Security` del mensaje .</span><span class="sxs-lookup"><span data-stu-id="7eba8-115">The caller's identity is transmitted using a `Username` security token inside the message `Security` header.</span></span> <span data-ttu-id="7eba8-116">El ejemplo utiliza la infraestructura de seguridad de WCF para transmitir y extraer esta información del `Security` encabezado.</span><span class="sxs-lookup"><span data-stu-id="7eba8-116">The sample uses the WCF security infrastructure to transmit and extract this information from the `Security` header.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7eba8-117">El servicio back-end confia en el servicio de fachada para autenticar el llamador.</span><span class="sxs-lookup"><span data-stu-id="7eba8-117">The backend service trusts the façade service to authenticate the caller.</span></span> <span data-ttu-id="7eba8-118">Debido a esto, el servicio back-end no autentica de nuevo el llamador; utiliza la información de identidad proporcionada por el servicio de fachada en la solicitud reenviada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-118">Because of this, the backend service does not authenticate the caller again; it uses the identity information provided by the façade service in the forwarded request.</span></span> <span data-ttu-id="7eba8-119">Debido a esta relación de confianza, el servicio back-end debe autenticar el servicio de fachada para asegurarse de que el mensaje reenviado procede de una fuente de confianza, en este caso el servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-119">Because of this trust relationship, the backend service must authenticate the façade service to ensure that the forwarded message comes from a trusted source - in this case, the façade service.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="7eba8-120">Implementación</span><span class="sxs-lookup"><span data-stu-id="7eba8-120">Implementation</span></span>  

 <span data-ttu-id="7eba8-121">Hay dos rutas de comunicación en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eba8-121">There are two communication paths in this sample.</span></span> <span data-ttu-id="7eba8-122">El primero se da entre el cliente y el servicio de fachada, el segundo entre el servicio de fachada y el servicio back-end.</span><span class="sxs-lookup"><span data-stu-id="7eba8-122">First is between the client and the façade service, the second is between the façade service and the backend service.</span></span>  
  
### <a name="communication-path-between-client-and-faade-service"></a><span data-ttu-id="7eba8-123">Ruta de acceso de comunicación entre Cliente y Servicio de Fachada</span><span class="sxs-lookup"><span data-stu-id="7eba8-123">Communication Path between Client and Façade Service</span></span>  

 <span data-ttu-id="7eba8-124">El cliente a la ruta de comunicación de servicio de fachada utiliza `wsHttpBinding` con un tipo de credencial de cliente `UserName` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-124">The client to the façade service communication path uses `wsHttpBinding` with a `UserName` client credential type.</span></span> <span data-ttu-id="7eba8-125">Esto significa que el cliente utiliza nombre de usuario y contraseña para autenticarse al servicio de fachada y el servicio de fachada utiliza el certificado X.509 para autenticarse al cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-125">This means that the client uses username and password to authenticate to the façade service and the façade service uses X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="7eba8-126">El archivo de configuración de enlace se parece al siguiente ejemplo.:</span><span class="sxs-lookup"><span data-stu-id="7eba8-126">The binding configuration looks like the following example.</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="7eba8-127">El servicio de fachada autentica el llamador mediante la implementación `UserNamePasswordValidator` personalizada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-127">The façade service authenticates the caller using custom `UserNamePasswordValidator` implementation.</span></span> <span data-ttu-id="7eba8-128">Durante la demostración, la autenticación solo asegura que el nombre de usuario del llamador coincide con la contraseña presentada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-128">For demonstration purposes, the authentication only ensures that the caller's username matches the presented password.</span></span> <span data-ttu-id="7eba8-129">En una situación real, el usuario se autentica probablemente utilizando Active Directory o el proveedor de suscripciones de ASP.NET personalizado.</span><span class="sxs-lookup"><span data-stu-id="7eba8-129">In the real world situation, the user is probably authenticated using Active Directory or custom ASP.NET Membership provider.</span></span> <span data-ttu-id="7eba8-130">La implementación del validador reside en el archivo `FacadeService.cs` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-130">The validator implementation resides in `FacadeService.cs` file.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="7eba8-131">El validador personalizado se configura para ser utilizado dentro del comportamiento `serviceCredentials` en el archivo de configuración de servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-131">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span> <span data-ttu-id="7eba8-132">Este comportamiento también se utiliza para configurar el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="7eba8-132">This behavior is also used to configure the service's X.509 certificate.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a><span data-ttu-id="7eba8-133">Ruta de acceso de comunicación entre el Servicio de Fachada y el Servicio Back-end</span><span class="sxs-lookup"><span data-stu-id="7eba8-133">Communication Path between Façade Service and Backend Service</span></span>  

 <span data-ttu-id="7eba8-134">La ruta de comunicación entre el servicio de fachada y el servicio back-end utiliza `customBinding` que está compuesto por varios elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="7eba8-134">The façade service to the backend service communication path uses a `customBinding` that consists of several binding elements.</span></span> <span data-ttu-id="7eba8-135">Este enlace logra dos cosas.</span><span class="sxs-lookup"><span data-stu-id="7eba8-135">This binding accomplishes two things.</span></span> <span data-ttu-id="7eba8-136">Autentica el servicio de fachada y el servicio back-end para asegurar que la comunicación es segura y viene de una fuente de confianza.</span><span class="sxs-lookup"><span data-stu-id="7eba8-136">It authenticates the façade service and backend service to ensure that the communication is secure and is coming from a trusted source.</span></span> <span data-ttu-id="7eba8-137">Además, también transmite la identidad del llamador inicial dentro del token de seguridad `Username` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-137">Additionally, it also transmits the initial caller's identity inside the `Username` security token.</span></span> <span data-ttu-id="7eba8-138">En este caso, solo se transmite el nombre de usuario del llamador inicial al servicio back-end, la contraseña no está incluida en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7eba8-138">In this case, only the initial caller's username is transmitted to the backend service, the password is not included in the message.</span></span> <span data-ttu-id="7eba8-139">Esto es porque el servicio back-end confia en el servicio de fachada para autenticar el llamador antes de reenviar la solicitud a él.</span><span class="sxs-lookup"><span data-stu-id="7eba8-139">This is because the backend service trusts the façade service to authenticate the caller before forwarding the request to it.</span></span> <span data-ttu-id="7eba8-140">Dado que el servicio de fachada se autentica en el servicio back-end, el servicio back-end puede confiar en la información contenida en la solicitud reenviada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-140">Because the façade service authenticates itself to the backend service, the backend service can trust the information contained in the forwarded request.</span></span>  
  
 <span data-ttu-id="7eba8-141">A continuación, se muestra la configuración de enlace para esta ruta de comunicación.</span><span class="sxs-lookup"><span data-stu-id="7eba8-141">The following is the binding configuration for this communication path.</span></span>  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="7eba8-142">El [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de enlace se encarga de la transmisión y extracción del nombre de usuario del llamador inicial.</span><span class="sxs-lookup"><span data-stu-id="7eba8-142">The [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) binding element takes care of the initial caller's username transmission and extraction.</span></span> <span data-ttu-id="7eba8-143">[\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md)Y se [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) encargan de autenticar los servicios de fachada y back-end y la protección de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7eba8-143">The [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md) and [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) take care of authenticating façade and backend services and message protection.</span></span>  
  
 <span data-ttu-id="7eba8-144">Para reenviar la solicitud, la implementación del servicio de fachada debe proporcionar el nombre de usuario del llamador inicial para que la infraestructura de seguridad de WCF pueda colocarlo en el mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="7eba8-144">To forward the request, the façade service implementation must provide the initial caller's username so that WCF security infrastructure can place this into the forwarded message.</span></span> <span data-ttu-id="7eba8-145">El nombre de usuario del llamador inicial se proporciona en la implementación del servicio de fachada estableciéndolo en la propiedad `ClientCredentials` en la instancia del proxy de cliente que el servicio de fachada utiliza para comunicarse con el servicio back-end.</span><span class="sxs-lookup"><span data-stu-id="7eba8-145">The initial caller's username is provided in the façade service implementation by setting it in the `ClientCredentials` property on the client proxy instance that façade service uses to communicate with the backend service.</span></span>  
  
 <span data-ttu-id="7eba8-146">El código siguiente muestra cómo el método `GetCallerIdentity` se implementa en el servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-146">The following code shows how `GetCallerIdentity` method is implemented on the façade service.</span></span> <span data-ttu-id="7eba8-147">Otros métodos utilizan el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="7eba8-147">Other methods use the same pattern.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 <span data-ttu-id="7eba8-148">Como se muestra en el código anterior, la contraseña no se establece en la propiedad `ClientCredentials` , solo se establece el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="7eba8-148">As shown in the previous code, the password is not set on the `ClientCredentials` property, only the username is set.</span></span> <span data-ttu-id="7eba8-149">La infraestructura de seguridad de WCF crea un token de seguridad de nombre de usuario sin contraseña en este caso, que es exactamente lo que se necesita en este escenario.</span><span class="sxs-lookup"><span data-stu-id="7eba8-149">WCF security infrastructure creates a username security token without a password in this case, which is exactly what is required in this scenario.</span></span>  
  
 <span data-ttu-id="7eba8-150">En el servicio back-end, la información contenida en el token de seguridad del nombre de usuario se debe autenticar.</span><span class="sxs-lookup"><span data-stu-id="7eba8-150">On the backend service, the information contained in the username security token must be authenticated.</span></span> <span data-ttu-id="7eba8-151">De forma predeterminada, la seguridad de WCF intenta asignar el usuario a una cuenta de Windows con la contraseña proporcionada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-151">By default, WCF security attempts to map the user to a Windows account using the provided password.</span></span> <span data-ttu-id="7eba8-152">En este caso, no hay ninguna contraseña proporcionada y no se exige al servicio back-end que autentique el nombre de usuario porque ya la realizó el servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-152">In this case, there is no password provided and the backend service is not required to authenticate the username because the authentication was already performed by the façade service.</span></span> <span data-ttu-id="7eba8-153">Para implementar esta funcionalidad en WCF, `UserNamePasswordValidator` se proporciona un personalizado que solo exige que un nombre de usuario se especifique en el token y no realiza ninguna autenticación adicional.</span><span class="sxs-lookup"><span data-stu-id="7eba8-153">To implement this functionality in WCF, a custom `UserNamePasswordValidator` is provided that only enforces that a username is specified in the token and does not perform any additional authentication.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="7eba8-154">El validador personalizado se configura para ser utilizado dentro del comportamiento `serviceCredentials` en el archivo de configuración de servicio de fachada.</span><span class="sxs-lookup"><span data-stu-id="7eba8-154">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="7eba8-155">Para extraer la información del nombre de usuario e información sobre la cuenta de servicio de fachada confiable, la implementación del servicio back-end utiliza la clase `ServiceSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-155">To extract the username information and information about the trusted façade service account, the backend service implementation uses the `ServiceSecurityContext` class.</span></span> <span data-ttu-id="7eba8-156">El código siguiente muestra cómo se implementa el método `GetCallerIdentity` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-156">The following code shows how the `GetCallerIdentity` method is implemented.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 <span data-ttu-id="7eba8-157">La información de cuenta de servicio de fachada se extrae utilizando la propiedad `ServiceSecurityContext.Current.WindowsIdentity` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-157">The façade service account information is extracted using the `ServiceSecurityContext.Current.WindowsIdentity` property.</span></span> <span data-ttu-id="7eba8-158">Para tener acceso a la información sobre el llamador inicial el servicio back-end utiliza la propiedad `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` .</span><span class="sxs-lookup"><span data-stu-id="7eba8-158">To access the information about the initial caller the backend service uses the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` property.</span></span> <span data-ttu-id="7eba8-159">Busca una notificación `Identity` con un tipo `Name`.</span><span class="sxs-lookup"><span data-stu-id="7eba8-159">It looks for an `Identity` claim with a type `Name`.</span></span> <span data-ttu-id="7eba8-160">Esta demanda se genera automáticamente mediante la infraestructura de seguridad de WCF a partir de la información contenida en el `Username` token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7eba8-160">This claim is automatically generated by WCF security infrastructure from the information contained in the `Username` security token.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="7eba8-161">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eba8-161">Running the sample</span></span>  

 <span data-ttu-id="7eba8-162">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-162">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7eba8-163">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-163">Press ENTER in the client window to shut down the client.</span></span> <span data-ttu-id="7eba8-164">Puede presionar Entrar en las ventanas de la consola de servicio de fachada y back-end para cerrar los servicios.</span><span class="sxs-lookup"><span data-stu-id="7eba8-164">You can press ENTER in the façade and backend service console windows to shut down the services.</span></span>  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="7eba8-165">El archivo por lotes Setup.bat incluido con el ejemplo de escenario de Fachada Confiable le permite configurar el servidor con un certificado pertinente para ejecutar el servicio de fachada que exige que la seguridad basada en certificado se autentique al cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-165">The Setup.bat batch file included with the Trusted Facade scenario sample enables you to configure the server with a relevant certificate to run the façade service that requires certificate-based security to authenticate itself to the client.</span></span> <span data-ttu-id="7eba8-166">Para obtener más detalles, vea el procedimiento de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7eba8-166">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="7eba8-167">A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes.</span><span class="sxs-lookup"><span data-stu-id="7eba8-167">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="7eba8-168">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="7eba8-168">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="7eba8-169">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7eba8-169">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="7eba8-170">La variable `%SERVER_NAME%` especifica el nombre del servidor; el valor predeterminado es el host local.</span><span class="sxs-lookup"><span data-stu-id="7eba8-170">The `%SERVER_NAME%` variable specifies the server name - the default value is localhost.</span></span> <span data-ttu-id="7eba8-171">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="7eba8-171">The certificate is stored in the LocalMachine store.</span></span>  
  
- <span data-ttu-id="7eba8-172">Instalar el certificado del servicio de fachada en el almacén de certificados de confianza de cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-172">Installing the façade service's certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="7eba8-173">La línea siguiente copia el certificado del servicio de fachada en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-173">The following line copies the façade service's certificate into the client trusted people store.</span></span> <span data-ttu-id="7eba8-174">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="7eba8-174">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="7eba8-175">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="7eba8-175">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7eba8-176">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eba8-176">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7eba8-177">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7eba8-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7eba8-178">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7eba8-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="7eba8-179">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="7eba8-179">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="7eba8-180">Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentra Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="7eba8-180">Ensure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="7eba8-181">Ejecute Setup.bat desde la carpeta de instalación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eba8-181">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="7eba8-182">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eba8-182">This installs all the certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="7eba8-183">Inicie BackendService.exe desde el directorio \BackendService\bin en una ventana de la consola independiente</span><span class="sxs-lookup"><span data-stu-id="7eba8-183">Launch the BackendService.exe from \BackendService\bin directory in a separate console window</span></span>  
  
4. <span data-ttu-id="7eba8-184">Inicie FacadeService.exe desde el directorio \FacadeService\bin en una ventana de la consola independiente</span><span class="sxs-lookup"><span data-stu-id="7eba8-184">Launch the FacadeService.exe from \FacadeService\bin directory in a separate console window</span></span>  
  
5. <span data-ttu-id="7eba8-185">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="7eba8-185">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="7eba8-186">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="7eba8-186">Client activity is displayed on the client console application.</span></span>  
  
6. <span data-ttu-id="7eba8-187">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="7eba8-187">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="7eba8-188">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eba8-188">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="7eba8-189">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7eba8-189">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7eba8-190">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7eba8-190">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7eba8-191">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7eba8-191">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7eba8-192">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7eba8-192">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7eba8-193">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7eba8-193">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`
