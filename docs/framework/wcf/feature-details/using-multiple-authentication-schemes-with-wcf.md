---
title: Usar múltiples esquemas de autenticación con WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 3aae9bff4300af97f7b179d9d8115340a26e715a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289430"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="012bc-102">Usar múltiples esquemas de autenticación con WCF</span><span class="sxs-lookup"><span data-stu-id="012bc-102">Using Multiple Authentication Schemes with WCF</span></span>

<span data-ttu-id="012bc-103">WCF permite ahora especificar varios esquemas de autenticación en un único extremo.</span><span class="sxs-lookup"><span data-stu-id="012bc-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="012bc-104">Además los servicios hospedados en web pueden heredar sus valores de autenticación directamente de IIS.</span><span class="sxs-lookup"><span data-stu-id="012bc-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="012bc-105">Los servicios autohospedados pueden especificar los esquemas de autenticación que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="012bc-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="012bc-106">Para obtener más información sobre cómo establecer la configuración de autenticación en IIS, vea [autenticación de IIS](https://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="012bc-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="012bc-107">Servicios hospedados en IIS</span><span class="sxs-lookup"><span data-stu-id="012bc-107">IIS-Hosted Services</span></span>  

 <span data-ttu-id="012bc-108">Para los servicios hospedados en IIS, establezca los esquemas de autenticación que desea usa en IIS.</span><span class="sxs-lookup"><span data-stu-id="012bc-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="012bc-109">Después, en el archivo de web.config del servicio, en la configuración de enlace especifique el tipo de clientCredential como "InheritedFromHost" como se muestra en el siguiente fragmento de código XML:</span><span class="sxs-lookup"><span data-stu-id="012bc-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="012bc-110">Puede especificar que solo quiere usar un subconjunto de esquemas de autenticación con el servicio mediante el ServiceAuthenticationBehavior o el \<serviceAuthenticationManager> elemento.</span><span class="sxs-lookup"><span data-stu-id="012bc-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="012bc-111">Al configurar esto en el código, use ServiceAuthenticationBehavior como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="012bc-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="012bc-112">Al configurar esto en un archivo de configuración, use el \<serviceAuthenticationManager> elemento como se muestra en el siguiente fragmento de código XML.</span><span class="sxs-lookup"><span data-stu-id="012bc-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="012bc-113">Esto garantizará que solo se considere un subconjunto de los esquemas de autenticación enumerados aquí para aplicar en el punto de conexión de servicio, según cuál se haya seleccionado en IIS.</span><span class="sxs-lookup"><span data-stu-id="012bc-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="012bc-114">Esto significa que un desarrollador puede excluir la autenticación básica de la lista omitiéndola de la lista de serviceAuthenticationManager e incluso si está habilitada en IIS, no se aplicará en el punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="012bc-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="012bc-115">Servicios WCF autohospedados</span><span class="sxs-lookup"><span data-stu-id="012bc-115">Self-Hosted Services</span></span>  

 <span data-ttu-id="012bc-116">Los servicios autohospedados se configuran de manera ligeramente diferente puesto que no hay configuración de IIS para heredar.</span><span class="sxs-lookup"><span data-stu-id="012bc-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="012bc-117">Aquí se usa el \<serviceAuthenticationManager> elemento o ServiceAuthenticationBehavior para especificar la configuración de autenticación que se va a heredar.</span><span class="sxs-lookup"><span data-stu-id="012bc-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="012bc-118">En el código tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="012bc-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="012bc-119">En la configuración, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="012bc-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="012bc-120">A continuación puede especificar InheritFromHost en la configuración de enlace como se muestra en el fragmento XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="012bc-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="012bc-121">Opcionalmente, puede especificar los esquemas de autenticación en un enlace personalizado, estableciendo los esquemas de autenticación en el elemento de enlace de transporte HTTP, como se muestra en el siguiente fragmento de código de configuración.</span><span class="sxs-lookup"><span data-stu-id="012bc-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="012bc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="012bc-122">See also</span></span>

- [<span data-ttu-id="012bc-123">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="012bc-123">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="012bc-124">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="012bc-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="012bc-125">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="012bc-125">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="012bc-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="012bc-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="012bc-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="012bc-127">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="012bc-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="012bc-128">Custom Bindings</span></span>](../extending/custom-bindings.md)
