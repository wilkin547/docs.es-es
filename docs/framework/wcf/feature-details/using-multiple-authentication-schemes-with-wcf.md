---
description: Más información acerca de cómo usar varios esquemas de autenticación con WCF
title: Usar múltiples esquemas de autenticación con WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: fd03a13c5d38bbf26e2b6079d1320bc389c9f20b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779717"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="c939b-103">Usar múltiples esquemas de autenticación con WCF</span><span class="sxs-lookup"><span data-stu-id="c939b-103">Using Multiple Authentication Schemes with WCF</span></span>

<span data-ttu-id="c939b-104">WCF permite ahora especificar varios esquemas de autenticación en un único extremo.</span><span class="sxs-lookup"><span data-stu-id="c939b-104">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="c939b-105">Además los servicios hospedados en web pueden heredar sus valores de autenticación directamente de IIS.</span><span class="sxs-lookup"><span data-stu-id="c939b-105">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="c939b-106">Los servicios autohospedados pueden especificar los esquemas de autenticación que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="c939b-106">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="c939b-107">Para obtener más información sobre cómo establecer la configuración de autenticación en IIS, vea [autenticación de IIS](https://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="c939b-107">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="c939b-108">Servicios hospedados en IIS</span><span class="sxs-lookup"><span data-stu-id="c939b-108">IIS-Hosted Services</span></span>  

 <span data-ttu-id="c939b-109">Para los servicios hospedados en IIS, establezca los esquemas de autenticación que desea usa en IIS.</span><span class="sxs-lookup"><span data-stu-id="c939b-109">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="c939b-110">Después, en el archivo de web.config del servicio, en la configuración de enlace especifique el tipo de clientCredential como "InheritedFromHost" como se muestra en el siguiente fragmento de código XML:</span><span class="sxs-lookup"><span data-stu-id="c939b-110">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
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
  
 <span data-ttu-id="c939b-111">Puede especificar que solo quiere usar un subconjunto de esquemas de autenticación con el servicio mediante el ServiceAuthenticationBehavior o el \<serviceAuthenticationManager> elemento.</span><span class="sxs-lookup"><span data-stu-id="c939b-111">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="c939b-112">Al configurar esto en el código, use ServiceAuthenticationBehavior como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c939b-112">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="c939b-113">Al configurar esto en un archivo de configuración, use el \<serviceAuthenticationManager> elemento como se muestra en el siguiente fragmento de código XML.</span><span class="sxs-lookup"><span data-stu-id="c939b-113">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="c939b-114">Esto garantizará que solo se considere un subconjunto de los esquemas de autenticación enumerados aquí para aplicar en el punto de conexión de servicio, según cuál se haya seleccionado en IIS.</span><span class="sxs-lookup"><span data-stu-id="c939b-114">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="c939b-115">Esto significa que un desarrollador puede excluir la autenticación básica de la lista omitiéndola de la lista de serviceAuthenticationManager e incluso si está habilitada en IIS, no se aplicará en el punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="c939b-115">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="c939b-116">Servicios WCF autohospedados</span><span class="sxs-lookup"><span data-stu-id="c939b-116">Self-Hosted Services</span></span>  

 <span data-ttu-id="c939b-117">Los servicios autohospedados se configuran de manera ligeramente diferente puesto que no hay configuración de IIS para heredar.</span><span class="sxs-lookup"><span data-stu-id="c939b-117">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="c939b-118">Aquí se usa el \<serviceAuthenticationManager> elemento o ServiceAuthenticationBehavior para especificar la configuración de autenticación que se va a heredar.</span><span class="sxs-lookup"><span data-stu-id="c939b-118">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="c939b-119">En el código tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c939b-119">In code it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="c939b-120">En la configuración, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c939b-120">In config, it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="c939b-121">A continuación puede especificar InheritFromHost en la configuración de enlace como se muestra en el fragmento XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="c939b-121">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="c939b-122">Opcionalmente, puede especificar los esquemas de autenticación en un enlace personalizado, estableciendo los esquemas de autenticación en el elemento de enlace de transporte HTTP, como se muestra en el siguiente fragmento de código de configuración.</span><span class="sxs-lookup"><span data-stu-id="c939b-122">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c939b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c939b-123">See also</span></span>

- [<span data-ttu-id="c939b-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="c939b-124">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="c939b-125">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="c939b-125">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="c939b-126">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c939b-126">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="c939b-127">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c939b-127">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c939b-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c939b-128">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="c939b-129">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c939b-129">Custom Bindings</span></span>](../extending/custom-bindings.md)
