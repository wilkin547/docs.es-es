---
title: Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00f4ddfd218e8797aa2089a21081ee711be316d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="e763a-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e763a-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="e763a-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e763a-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="e763a-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e763a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e763a-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e763a-105">\<bindings></span></span>  
<span data-ttu-id="e763a-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e763a-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e763a-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e763a-107">\<binding></span></span>  
<span data-ttu-id="e763a-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e763a-108">\<security></span></span>  
<span data-ttu-id="e763a-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="e763a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e763a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e763a-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e763a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e763a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e763a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e763a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e763a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e763a-113">Attributes</span></span>  
  
|<span data-ttu-id="e763a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e763a-114">Attribute</span></span>|<span data-ttu-id="e763a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e763a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e763a-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e763a-116">protectionLevel</span></span>|<span data-ttu-id="e763a-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e763a-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e763a-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="e763a-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e763a-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="e763a-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e763a-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e763a-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e763a-121">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="e763a-121">-   None: No protection.</span></span><br /><span data-ttu-id="e763a-122">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e763a-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e763a-123">-EncryptAndSign: Los mensajes se cifrarán y firmarán.</span><span class="sxs-lookup"><span data-stu-id="e763a-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e763a-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e763a-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e763a-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e763a-125">Child Elements</span></span>  
 <span data-ttu-id="e763a-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e763a-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e763a-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e763a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e763a-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e763a-128">Element</span></span>|<span data-ttu-id="e763a-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e763a-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e763a-130">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e763a-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="e763a-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e763a-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e763a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e763a-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="e763a-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e763a-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e763a-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e763a-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e763a-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e763a-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e763a-136">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e763a-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e763a-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e763a-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
