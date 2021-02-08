---
description: 'Más información sobre: <transport> de <netNamedPipeBinding>'
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a54c429bcac192ddc46df7232c33ab98bd1a4c58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773490"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="bd6f0-103">\<transport> de \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="bd6f0-103">\<transport> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="bd6f0-104">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-104">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="bd6f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd6f0-105">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd6f0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd6f0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bd6f0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd6f0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd6f0-108">Attributes</span></span>  
  
|<span data-ttu-id="bd6f0-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd6f0-109">Attribute</span></span>|<span data-ttu-id="bd6f0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd6f0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd6f0-111">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="bd6f0-111">protectionLevel</span></span>|<span data-ttu-id="bd6f0-112">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-112">Defines protection level of the named pipe.</span></span> <span data-ttu-id="bd6f0-113">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-113">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="bd6f0-114">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-114">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="bd6f0-115">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bd6f0-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bd6f0-116">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-116">-   None: No protection.</span></span><br /><span data-ttu-id="bd6f0-117">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-117">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="bd6f0-118">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-118">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="bd6f0-119">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-119">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd6f0-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd6f0-120">Child Elements</span></span>  

 <span data-ttu-id="bd6f0-121">None</span><span class="sxs-lookup"><span data-stu-id="bd6f0-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd6f0-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd6f0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bd6f0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd6f0-123">Element</span></span>|<span data-ttu-id="bd6f0-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd6f0-124">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="bd6f0-125">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="bd6f0-125">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd6f0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd6f0-126">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="bd6f0-127">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bd6f0-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="bd6f0-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bd6f0-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bd6f0-129">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="bd6f0-129">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bd6f0-130">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bd6f0-130">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
