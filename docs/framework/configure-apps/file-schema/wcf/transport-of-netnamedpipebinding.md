---
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 1e76d0962ea7b4714ef6ca1f9d4c4c3e23df5b6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934671"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="0b809-102">\<> de transporte \<de > netNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="0b809-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="0b809-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="0b809-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="0b809-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0b809-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b809-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b809-105">\<bindings></span></span>  
<span data-ttu-id="0b809-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="0b809-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="0b809-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b809-107">\<binding></span></span>  
<span data-ttu-id="0b809-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="0b809-108">\<security></span></span>  
<span data-ttu-id="0b809-109">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="0b809-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b809-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b809-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b809-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0b809-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0b809-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0b809-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b809-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b809-113">Attributes</span></span>  
  
|<span data-ttu-id="0b809-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0b809-114">Attribute</span></span>|<span data-ttu-id="0b809-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b809-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b809-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="0b809-116">protectionLevel</span></span>|<span data-ttu-id="0b809-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="0b809-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="0b809-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="0b809-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="0b809-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="0b809-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="0b809-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b809-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0b809-121">Ninguna Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="0b809-121">-   None: No protection.</span></span><br /><span data-ttu-id="0b809-122">Sesión Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0b809-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="0b809-123">-   EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="0b809-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="0b809-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="0b809-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b809-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0b809-125">Child Elements</span></span>  
 <span data-ttu-id="0b809-126">None</span><span class="sxs-lookup"><span data-stu-id="0b809-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b809-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0b809-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0b809-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b809-128">Element</span></span>|<span data-ttu-id="0b809-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b809-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b809-130">\<security></span><span class="sxs-lookup"><span data-stu-id="0b809-130">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="0b809-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="0b809-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b809-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b809-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="0b809-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0b809-133">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0b809-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0b809-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0b809-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="0b809-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0b809-136">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0b809-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0b809-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b809-137">\<binding></span></span>](../../../misc/binding.md)
