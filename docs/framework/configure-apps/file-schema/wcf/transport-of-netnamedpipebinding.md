---
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735964"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="e1e0a-102">\<> de transporte de \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="e1e0a-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="e1e0a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1e0a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1e0a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e1e0a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e1e0a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e1e0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding**](netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="e1e0a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e1e0a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="e1e0a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e0a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1e0a-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1e0a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1e0a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e1e0a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1e0a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1e0a-114">Attributes</span></span>  
  
|<span data-ttu-id="e1e0a-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1e0a-115">Attribute</span></span>|<span data-ttu-id="e1e0a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e0a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1e0a-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e1e0a-117">protectionLevel</span></span>|<span data-ttu-id="e1e0a-118">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e1e0a-119">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e1e0a-120">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e1e0a-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1e0a-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e1e0a-122">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-122">-   None: No protection.</span></span><br /><span data-ttu-id="e1e0a-123">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e1e0a-124">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e1e0a-125">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1e0a-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1e0a-126">Child Elements</span></span>  
 <span data-ttu-id="e1e0a-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e1e0a-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1e0a-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1e0a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e1e0a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1e0a-129">Element</span></span>|<span data-ttu-id="e1e0a-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e0a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1e0a-131">\<La ></span><span class="sxs-lookup"><span data-stu-id="e1e0a-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="e1e0a-132">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e1e0a-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1e0a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1e0a-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="e1e0a-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e1e0a-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e1e0a-135">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e1e0a-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e1e0a-136">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e1e0a-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e1e0a-137">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e1e0a-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e1e0a-138">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="e1e0a-138">\<binding></span></span>](bindings.md)
