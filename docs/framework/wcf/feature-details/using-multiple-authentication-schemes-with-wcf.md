---
title: "Usar múltiples esquemas de autenticación con WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: db2545470c416fe066226124fb7833ef5d9e5d13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="9e573-102">Usar múltiples esquemas de autenticación con WCF</span><span class="sxs-lookup"><span data-stu-id="9e573-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="9e573-103">WCF permite ahora especificar varios esquemas de autenticación en un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e573-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="9e573-104">Además los servicios hospedados en web pueden heredar sus valores de autenticación directamente de IIS.</span><span class="sxs-lookup"><span data-stu-id="9e573-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="9e573-105">Los servicios autohospedados pueden especificar los esquemas de autenticación que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="9e573-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="9e573-106">Para obtener más información acerca de cómo establecer la configuración de autenticación en IIS, consulte [autenticación de IIS](http://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="9e573-106">For more information about setting authentication settings in IIS, see [IIS Authentication](http://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="9e573-107">Servicios hospedados en IIS</span><span class="sxs-lookup"><span data-stu-id="9e573-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="9e573-108">Para los servicios hospedados en IIS, establezca los esquemas de autenticación que desea usa en IIS.</span><span class="sxs-lookup"><span data-stu-id="9e573-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="9e573-109">A continuación, en el archivo web.config de su servicio, en la configuración de enlace especifique el tipo clientCredential como "InheritedFromHost" como se muestra en el fragmento XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e573-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
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
  
 <span data-ttu-id="9e573-110">Puede especificar que desea que solo un subconjunto de los esquemas de autenticación que se usará con el servicio mediante el ServiceAuthenticationBehavior o el \<serviceAuthenticationManager > elemento.</span><span class="sxs-lookup"><span data-stu-id="9e573-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="9e573-111">Al configurar esto en el código, use ServiceAuthenticationBehavior como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e573-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="9e573-112">Al configurar esto en un archivo de configuración, use la \<serviceAuthenticationManager > elemento tal como se muestra en el siguiente fragmento XML.</span><span class="sxs-lookup"><span data-stu-id="9e573-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="9e573-113">Esto garantizará que solo se considere un subconjunto de los esquemas de autenticación enumerados aquí para aplicar en el punto de conexión de servicio, según cuál se haya seleccionado en IIS.</span><span class="sxs-lookup"><span data-stu-id="9e573-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="9e573-114">Esto significa que un desarrollador puede excluir la autenticación básica de la lista omitiéndola de la lista de serviceAuthenticationManager e incluso si está habilitada en IIS, no se aplicará en el extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9e573-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="9e573-115">Servicios WCF autohospedados</span><span class="sxs-lookup"><span data-stu-id="9e573-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="9e573-116">Los servicios autohospedados se configuran de manera ligeramente diferente puesto que no hay configuración de IIS para heredar.</span><span class="sxs-lookup"><span data-stu-id="9e573-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="9e573-117">Aquí se usa el \<serviceAuthenticationManager > elemento o ServiceAuthenticationBehavior para especificar la configuración de autenticación que se heredarán.</span><span class="sxs-lookup"><span data-stu-id="9e573-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="9e573-118">En el código tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9e573-118">In code it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="9e573-119">En la configuración, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9e573-119">In config, it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="9e573-120">A continuación puede especificar InheritFromHost en la configuración de enlace como se muestra en el fragmento XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e573-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="9e573-121">Opcionalmente, puede especificar los esquemas de autenticación en un enlace personalizado, estableciendo los esquemas de autenticación en el elemento de enlace de transporte HTTP, como se muestra en el siguiente fragmento de código de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e573-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e573-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e573-122">See Also</span></span>  
 [<span data-ttu-id="9e573-123">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="9e573-123">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="9e573-124">Los puntos de conexión: Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="9e573-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="9e573-125">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9e573-125">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9e573-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9e573-126">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9e573-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9e573-127">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="9e573-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9e573-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="9e573-129">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9e573-129">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
