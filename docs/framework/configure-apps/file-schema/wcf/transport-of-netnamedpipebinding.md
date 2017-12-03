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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15489d2f5447fc2d3d4fb5173bcc94b5fb68e1c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="4b6e1-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="4b6e1-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="4b6e1-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="4b6e1-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b6e1-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-105">\<bindings></span></span>  
<span data-ttu-id="4b6e1-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="4b6e1-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-107">\<binding></span></span>  
<span data-ttu-id="4b6e1-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-108">\<security></span></span>  
<span data-ttu-id="4b6e1-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6e1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b6e1-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b6e1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4b6e1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b6e1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b6e1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="4b6e1-113">Attributes</span></span>  
  
|<span data-ttu-id="4b6e1-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="4b6e1-114">Attribute</span></span>|<span data-ttu-id="4b6e1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b6e1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b6e1-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="4b6e1-116">protectionLevel</span></span>|<span data-ttu-id="4b6e1-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="4b6e1-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="4b6e1-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="4b6e1-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b6e1-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4b6e1-121">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-121">-   None: No protection.</span></span><br /><span data-ttu-id="4b6e1-122">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="4b6e1-123">-EncryptAndSign: Los mensajes se cifrarán y firmarán.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="4b6e1-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b6e1-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b6e1-125">Child Elements</span></span>  
 <span data-ttu-id="4b6e1-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4b6e1-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b6e1-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4b6e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4b6e1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b6e1-128">Element</span></span>|<span data-ttu-id="4b6e1-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b6e1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b6e1-130">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="4b6e1-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b6e1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b6e1-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="4b6e1-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4b6e1-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4b6e1-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4b6e1-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4b6e1-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="4b6e1-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4b6e1-136">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4b6e1-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4b6e1-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="4b6e1-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
