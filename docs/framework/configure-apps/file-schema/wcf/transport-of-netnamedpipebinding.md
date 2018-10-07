---
title: Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: c42132f774257589b9020248188ee8d972eb92ba
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837055"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="77fa7-102">Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="77fa7-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="77fa7-103">Define los valores de seguridad de transporte para una canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="77fa7-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="77fa7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="77fa7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77fa7-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="77fa7-105">\<bindings></span></span>  
<span data-ttu-id="77fa7-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="77fa7-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="77fa7-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="77fa7-107">\<binding></span></span>  
<span data-ttu-id="77fa7-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="77fa7-108">\<security></span></span>  
<span data-ttu-id="77fa7-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="77fa7-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77fa7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77fa7-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77fa7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77fa7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="77fa7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77fa7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77fa7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="77fa7-113">Attributes</span></span>  
  
|<span data-ttu-id="77fa7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="77fa7-114">Attribute</span></span>|<span data-ttu-id="77fa7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="77fa7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77fa7-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="77fa7-116">protectionLevel</span></span>|<span data-ttu-id="77fa7-117">Define el nivel de protección de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="77fa7-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="77fa7-118">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="77fa7-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="77fa7-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="77fa7-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="77fa7-120">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="77fa7-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="77fa7-121">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="77fa7-121">-   None: No protection.</span></span><br /><span data-ttu-id="77fa7-122">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="77fa7-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="77fa7-123">-EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="77fa7-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="77fa7-124">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="77fa7-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77fa7-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77fa7-125">Child Elements</span></span>  
 <span data-ttu-id="77fa7-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="77fa7-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77fa7-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77fa7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="77fa7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="77fa7-128">Element</span></span>|<span data-ttu-id="77fa7-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="77fa7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77fa7-130">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="77fa7-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="77fa7-131">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="77fa7-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77fa7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="77fa7-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="77fa7-133">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="77fa7-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="77fa7-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="77fa7-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="77fa7-135">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="77fa7-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="77fa7-136">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="77fa7-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="77fa7-137">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="77fa7-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
