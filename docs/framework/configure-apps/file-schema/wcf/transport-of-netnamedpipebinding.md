---
title: Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 9116532c8b4aae2f7539706b97d564444195c79d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="e5f36-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e5f36-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="e5f36-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e5f36-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="e5f36-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5f36-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5f36-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e5f36-105">\<bindings></span></span>  
<span data-ttu-id="e5f36-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e5f36-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e5f36-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e5f36-107">\<binding></span></span>  
<span data-ttu-id="e5f36-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e5f36-108">\<security></span></span>  
<span data-ttu-id="e5f36-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="e5f36-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f36-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5f36-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5f36-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5f36-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5f36-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5f36-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5f36-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5f36-113">Attributes</span></span>  
  
|<span data-ttu-id="e5f36-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5f36-114">Attribute</span></span>|<span data-ttu-id="e5f36-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5f36-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5f36-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e5f36-116">protectionLevel</span></span>|<span data-ttu-id="e5f36-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e5f36-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e5f36-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="e5f36-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e5f36-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="e5f36-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e5f36-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5f36-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5f36-121">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="e5f36-121">-   None: No protection.</span></span><br /><span data-ttu-id="e5f36-122">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e5f36-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e5f36-123">-EncryptAndSign: Los mensajes se cifrarán y firmarán.</span><span class="sxs-lookup"><span data-stu-id="e5f36-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e5f36-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e5f36-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5f36-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5f36-125">Child Elements</span></span>  
 <span data-ttu-id="e5f36-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e5f36-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5f36-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5f36-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e5f36-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5f36-128">Element</span></span>|<span data-ttu-id="e5f36-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5f36-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5f36-130">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e5f36-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="e5f36-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e5f36-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5f36-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5f36-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="e5f36-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e5f36-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e5f36-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e5f36-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e5f36-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e5f36-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e5f36-136">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e5f36-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e5f36-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e5f36-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
