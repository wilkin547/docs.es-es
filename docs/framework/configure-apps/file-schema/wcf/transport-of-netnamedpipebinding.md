---
title: <transport> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 81c52405478d4c1ab5c65aab73f7feff61b879d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178026"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="c8096-102">\<transport> de \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c8096-102">\<transport> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="c8096-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="c8096-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="c8096-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8096-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8096-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c8096-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c8096-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c8096-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8096-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8096-107">Attributes</span></span>  
  
|<span data-ttu-id="c8096-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8096-108">Attribute</span></span>|<span data-ttu-id="c8096-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8096-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8096-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c8096-110">protectionLevel</span></span>|<span data-ttu-id="c8096-111">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="c8096-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="c8096-112">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="c8096-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c8096-113">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="c8096-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c8096-114">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8096-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8096-115">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="c8096-115">-   None: No protection.</span></span><br /><span data-ttu-id="c8096-116">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="c8096-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c8096-117">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="c8096-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c8096-118">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="c8096-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8096-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c8096-119">Child Elements</span></span>  

 <span data-ttu-id="c8096-120">None</span><span class="sxs-lookup"><span data-stu-id="c8096-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8096-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c8096-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c8096-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8096-122">Element</span></span>|<span data-ttu-id="c8096-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8096-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="c8096-124">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="c8096-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8096-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8096-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="c8096-126">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c8096-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c8096-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c8096-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c8096-128">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c8096-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c8096-129">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c8096-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
