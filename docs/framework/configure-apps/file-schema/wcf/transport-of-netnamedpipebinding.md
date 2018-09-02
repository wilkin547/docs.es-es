---
title: Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 0006be71ee67d5f274d8af8087f2d111cddb12b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407260"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="9d3d4-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9d3d4-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="9d3d4-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="9d3d4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9d3d4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d3d4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-105">\<bindings></span></span>  
<span data-ttu-id="9d3d4-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="9d3d4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-107">\<binding></span></span>  
<span data-ttu-id="9d3d4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-108">\<security></span></span>  
<span data-ttu-id="9d3d4-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d3d4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d3d4-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d3d4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9d3d4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d3d4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d3d4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d3d4-113">Attributes</span></span>  
  
|<span data-ttu-id="9d3d4-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="9d3d4-114">Attribute</span></span>|<span data-ttu-id="9d3d4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d3d4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d3d4-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9d3d4-116">protectionLevel</span></span>|<span data-ttu-id="9d3d4-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="9d3d4-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9d3d4-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="9d3d4-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d3d4-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9d3d4-121">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-121">-   None: No protection.</span></span><br /><span data-ttu-id="9d3d4-122">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="9d3d4-123">-EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="9d3d4-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d3d4-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9d3d4-125">Child Elements</span></span>  
 <span data-ttu-id="9d3d4-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9d3d4-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d3d4-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9d3d4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9d3d4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d3d4-128">Element</span></span>|<span data-ttu-id="9d3d4-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d3d4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d3d4-130">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="9d3d4-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d3d4-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3d4-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="9d3d4-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9d3d4-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9d3d4-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9d3d4-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9d3d4-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9d3d4-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9d3d4-136">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9d3d4-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9d3d4-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="9d3d4-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
