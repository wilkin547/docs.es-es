---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09a12f062b2fe3ad6e5ac90f0d268bbbeab44876
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674147"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="1e0d3-102">\<generatePublisherEvidence > elemento</span><span class="sxs-lookup"><span data-stu-id="1e0d3-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="1e0d3-103">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia para la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="1e0d3-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="1e0d3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1e0d3-104">\<configuration></span></span>  
<span data-ttu-id="1e0d3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1e0d3-105">\<runtime></span></span>  
<span data-ttu-id="1e0d3-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="1e0d3-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0d3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e0d3-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0d3-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1e0d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1e0d3-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e0d3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e0d3-110">Attributes</span></span>  
  
|<span data-ttu-id="1e0d3-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1e0d3-111">Attribute</span></span>|<span data-ttu-id="1e0d3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e0d3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1e0d3-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1e0d3-114">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1e0d3-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="1e0d3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1e0d3-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1e0d3-116">Value</span></span>|<span data-ttu-id="1e0d3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e0d3-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1e0d3-118">No crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="1e0d3-119">Crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="1e0d3-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e0d3-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1e0d3-121">Child Elements</span></span>  
 <span data-ttu-id="1e0d3-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e0d3-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1e0d3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1e0d3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e0d3-124">Element</span></span>|<span data-ttu-id="1e0d3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e0d3-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1e0d3-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1e0d3-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e0d3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e0d3-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e0d3-129">En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="1e0d3-130">Para obtener más información, vea la sección "Simplificación de la directiva de seguridad" en [cambios de seguridad](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="1e0d3-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="1e0d3-131">Common language runtime (CLR) intenta comprobar la firma Authenticode en tiempo de carga para crear <xref:System.Security.Policy.Publisher> evidencia del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="1e0d3-132">Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no es necesario <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="1e0d3-133">La directiva CAS estándar no se basa en el <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="1e0d3-134">Debe evitar el costo innecesario asociado con la comprobación de la firma de publicador a menos que la aplicación se ejecuta en un equipo con la directiva CAS personalizada o va a satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="1e0d3-135">(Las peticiones de permisos de identidad siempre tuvo éxito en un entorno de plena confianza).</span><span class="sxs-lookup"><span data-stu-id="1e0d3-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e0d3-136">Se recomienda que los servicios usan el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="1e0d3-137">Uso de este elemento también puede ayudar a evitar retrasos que pueden causar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1e0d3-138">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1e0d3-138">Configuration File</span></span>  
 <span data-ttu-id="1e0d3-139">Este elemento se puede usar solo en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e0d3-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e0d3-140">Example</span></span>  
 <span data-ttu-id="1e0d3-141">El ejemplo siguiente muestra cómo usar el `<generatePublisherEvidence>` elemento que se va a deshabilitar la comprobación de directiva de edición de entidades emisoras de certificados para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e0d3-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e0d3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e0d3-142">See also</span></span>

- [<span data-ttu-id="1e0d3-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1e0d3-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1e0d3-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1e0d3-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
