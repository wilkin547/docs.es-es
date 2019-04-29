---
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a6d3dd2c24e90bdcdc6520e62dcc1dbe7ce797f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788354"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="e3a90-102">\<transporte > de \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e3a90-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="e3a90-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e3a90-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="e3a90-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3a90-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3a90-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e3a90-105">\<bindings></span></span>  
<span data-ttu-id="e3a90-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="e3a90-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e3a90-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3a90-107">\<binding></span></span>  
<span data-ttu-id="e3a90-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e3a90-108">\<security></span></span>  
<span data-ttu-id="e3a90-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e3a90-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a90-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3a90-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3a90-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3a90-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e3a90-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3a90-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3a90-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3a90-113">Attributes</span></span>  
  
|<span data-ttu-id="e3a90-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e3a90-114">Attribute</span></span>|<span data-ttu-id="e3a90-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3a90-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3a90-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e3a90-116">protectionLevel</span></span>|<span data-ttu-id="e3a90-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e3a90-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e3a90-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="e3a90-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e3a90-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="e3a90-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e3a90-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3a90-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e3a90-121">-None: Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="e3a90-121">-   None: No protection.</span></span><br /><span data-ttu-id="e3a90-122">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3a90-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e3a90-123">-   EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="e3a90-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e3a90-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e3a90-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3a90-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3a90-125">Child Elements</span></span>  
 <span data-ttu-id="e3a90-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e3a90-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3a90-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3a90-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e3a90-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3a90-128">Element</span></span>|<span data-ttu-id="e3a90-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3a90-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3a90-130">\<security></span><span class="sxs-lookup"><span data-stu-id="e3a90-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="e3a90-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e3a90-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3a90-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3a90-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="e3a90-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e3a90-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e3a90-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e3a90-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e3a90-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e3a90-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e3a90-136">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e3a90-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e3a90-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3a90-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
