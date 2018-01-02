---
title: '&lt;generatePublisherEvidence&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7f7debed03526dbd7a5b2e24ff8a370921fe020
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="4cfb0-102">&lt;generatePublisherEvidence&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="4cfb0-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="4cfb0-103">Especifica si el runtime crea <xref:System.Security.Policy.Publisher> evidencia de seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="4cfb0-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="4cfb0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4cfb0-104">\<configuration></span></span>  
<span data-ttu-id="4cfb0-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="4cfb0-105">\<runtime></span></span>  
<span data-ttu-id="4cfb0-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="4cfb0-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfb0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cfb0-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cfb0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4cfb0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4cfb0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cfb0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4cfb0-110">Attributes</span></span>  
  
|<span data-ttu-id="4cfb0-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4cfb0-111">Attribute</span></span>|<span data-ttu-id="4cfb0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cfb0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4cfb0-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4cfb0-114">Especifica si el runtime crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4cfb0-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4cfb0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4cfb0-116">Valor</span><span class="sxs-lookup"><span data-stu-id="4cfb0-116">Value</span></span>|<span data-ttu-id="4cfb0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cfb0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4cfb0-118">No crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="4cfb0-119">Crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4cfb0-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cfb0-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4cfb0-121">Child Elements</span></span>  
 <span data-ttu-id="4cfb0-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4cfb0-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4cfb0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4cfb0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4cfb0-124">Element</span></span>|<span data-ttu-id="4cfb0-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cfb0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4cfb0-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4cfb0-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cfb0-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4cfb0-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cfb0-129">En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="4cfb0-130">Para obtener más información, vea la sección "Simplificación de la directiva de seguridad" en [cambios de seguridad](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4cfb0-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="4cfb0-131">Common language runtime (CLR) intenta comprobar la firma Authenticode en tiempo de carga para crear <xref:System.Security.Policy.Publisher> evidencia del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="4cfb0-132">Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no es necesario <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4cfb0-133">La directiva CAS estándar no se basa en el <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="4cfb0-134">Debe evitar el costo de inicio innecesarias asociado a comprobar la firma del editor a menos que la aplicación se ejecuta en un equipo con la directiva CAS personalizada o pretende satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="4cfb0-135">(Las peticiones de permisos de identidad siempre correctamente en un entorno de plena confianza).</span><span class="sxs-lookup"><span data-stu-id="4cfb0-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cfb0-136">Se recomienda que usan los servicios el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="4cfb0-137">Uso de este elemento también puede ayudar a evitar los retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4cfb0-138">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4cfb0-138">Configuration File</span></span>  
 <span data-ttu-id="4cfb0-139">Este elemento se puede usar únicamente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cfb0-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cfb0-140">Example</span></span>  
 <span data-ttu-id="4cfb0-141">En el ejemplo siguiente se muestra cómo utilizar el `<generatePublisherEvidence>` elemento que se va a deshabilitar la comprobación de directiva de edición de entidades emisoras de certificados para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cfb0-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cfb0-142">See Also</span></span>  
 [<span data-ttu-id="4cfb0-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4cfb0-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="4cfb0-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4cfb0-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
