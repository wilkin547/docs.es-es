---
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 6ea0b1e374659bbbbb2f47630c009f823ccd4de9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399327"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="417d5-102">\<> de transporte \<de > netNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="417d5-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="417d5-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="417d5-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="417d5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="417d5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="417d5-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="417d5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="417d5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="417d5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="417d5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netNamedPipeBinding**](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="417d5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="417d5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="417d5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="417d5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="417d5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="417d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de transporte**</span><span class="sxs-lookup"><span data-stu-id="417d5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417d5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="417d5-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="417d5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="417d5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="417d5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="417d5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="417d5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="417d5-114">Attributes</span></span>  
  
|<span data-ttu-id="417d5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="417d5-115">Attribute</span></span>|<span data-ttu-id="417d5-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="417d5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="417d5-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="417d5-117">protectionLevel</span></span>|<span data-ttu-id="417d5-118">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="417d5-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="417d5-119">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="417d5-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="417d5-120">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="417d5-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="417d5-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="417d5-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="417d5-122">Ninguna Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="417d5-122">-   None: No protection.</span></span><br /><span data-ttu-id="417d5-123">Sesión Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="417d5-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="417d5-124">-   EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="417d5-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="417d5-125">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="417d5-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="417d5-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="417d5-126">Child Elements</span></span>  
 <span data-ttu-id="417d5-127">None</span><span class="sxs-lookup"><span data-stu-id="417d5-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="417d5-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="417d5-128">Parent Elements</span></span>  
  
|<span data-ttu-id="417d5-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="417d5-129">Element</span></span>|<span data-ttu-id="417d5-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="417d5-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="417d5-131">\<security></span><span class="sxs-lookup"><span data-stu-id="417d5-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="417d5-132">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="417d5-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="417d5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="417d5-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="417d5-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="417d5-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="417d5-135">Enlaces</span><span class="sxs-lookup"><span data-stu-id="417d5-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="417d5-136">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="417d5-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="417d5-137">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="417d5-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="417d5-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="417d5-138">\<binding></span></span>](../../../misc/binding.md)
