---
title: Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 7177dda08e1ce5b4f8adb072dce6155df714979d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556095"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="089e3-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="089e3-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="089e3-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="089e3-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="089e3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="089e3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="089e3-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="089e3-105">\<bindings></span></span>  
<span data-ttu-id="089e3-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="089e3-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="089e3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="089e3-107">\<binding></span></span>  
<span data-ttu-id="089e3-108">\<security></span><span class="sxs-lookup"><span data-stu-id="089e3-108">\<security></span></span>  
<span data-ttu-id="089e3-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="089e3-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="089e3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="089e3-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="089e3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="089e3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="089e3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="089e3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="089e3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="089e3-113">Attributes</span></span>  
  
|<span data-ttu-id="089e3-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="089e3-114">Attribute</span></span>|<span data-ttu-id="089e3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="089e3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="089e3-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="089e3-116">protectionLevel</span></span>|<span data-ttu-id="089e3-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="089e3-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="089e3-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="089e3-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="089e3-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="089e3-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="089e3-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="089e3-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="089e3-121">-None: Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="089e3-121">-   None: No protection.</span></span><br /><span data-ttu-id="089e3-122">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="089e3-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="089e3-123">-   EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="089e3-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="089e3-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="089e3-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="089e3-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="089e3-125">Child Elements</span></span>  
 <span data-ttu-id="089e3-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="089e3-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="089e3-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="089e3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="089e3-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="089e3-128">Element</span></span>|<span data-ttu-id="089e3-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="089e3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="089e3-130">\<security></span><span class="sxs-lookup"><span data-stu-id="089e3-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="089e3-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="089e3-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="089e3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="089e3-132">See also</span></span>
- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="089e3-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="089e3-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="089e3-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="089e3-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="089e3-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="089e3-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="089e3-136">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="089e3-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="089e3-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="089e3-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
