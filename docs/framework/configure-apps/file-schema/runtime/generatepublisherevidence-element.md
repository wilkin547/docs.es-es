---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caec297f8d0f6febad5cf46adb0a2658960c6bb1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663671"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="edddb-102">\<generatePublisherEvidence >, elemento</span><span class="sxs-lookup"><span data-stu-id="edddb-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="edddb-103">Especifica si el tiempo de <xref:System.Security.Policy.Publisher> ejecución crea evidencia para la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="edddb-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="edddb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="edddb-104">\<configuration></span></span>  
<span data-ttu-id="edddb-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="edddb-105">\<runtime></span></span>  
<span data-ttu-id="edddb-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="edddb-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edddb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edddb-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edddb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="edddb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="edddb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="edddb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edddb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="edddb-110">Attributes</span></span>  
  
|<span data-ttu-id="edddb-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="edddb-111">Attribute</span></span>|<span data-ttu-id="edddb-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="edddb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="edddb-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="edddb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="edddb-114">Especifica si el tiempo de <xref:System.Security.Policy.Publisher> ejecución crea evidencia.</span><span class="sxs-lookup"><span data-stu-id="edddb-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="edddb-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="edddb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="edddb-116">Valor</span><span class="sxs-lookup"><span data-stu-id="edddb-116">Value</span></span>|<span data-ttu-id="edddb-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="edddb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="edddb-118">No crea <xref:System.Security.Policy.Publisher> ninguna evidencia.</span><span class="sxs-lookup"><span data-stu-id="edddb-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="edddb-119">Crea <xref:System.Security.Policy.Publisher> una evidencia.</span><span class="sxs-lookup"><span data-stu-id="edddb-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="edddb-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="edddb-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edddb-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="edddb-121">Child Elements</span></span>  
 <span data-ttu-id="edddb-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="edddb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edddb-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="edddb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="edddb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="edddb-124">Element</span></span>|<span data-ttu-id="edddb-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="edddb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="edddb-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="edddb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="edddb-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="edddb-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edddb-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="edddb-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edddb-129">En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="edddb-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="edddb-130">Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="edddb-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="edddb-131">El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga <xref:System.Security.Policy.Publisher> para crear una evidencia para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="edddb-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="edddb-132">Sin embargo, de forma predeterminada, la mayoría de <xref:System.Security.Policy.Publisher> las aplicaciones no necesitan evidencia.</span><span class="sxs-lookup"><span data-stu-id="edddb-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="edddb-133">La <xref:System.Security.Policy.PublisherMembershipCondition>Directiva CAS estándar no se basa en.</span><span class="sxs-lookup"><span data-stu-id="edddb-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="edddb-134">Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o <xref:System.Security.Permissions.PublisherIdentityPermission> que pretenda satisfacer las demandas de en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="edddb-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="edddb-135">(Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).</span><span class="sxs-lookup"><span data-stu-id="edddb-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edddb-136">Se recomienda que los servicios utilicen `<generatePublisherEvidence>` el elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="edddb-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="edddb-137">El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="edddb-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="edddb-138">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="edddb-138">Configuration File</span></span>  
 <span data-ttu-id="edddb-139">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edddb-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edddb-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edddb-140">Example</span></span>  
 <span data-ttu-id="edddb-141">En el ejemplo siguiente se muestra cómo usar `<generatePublisherEvidence>` el elemento para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="edddb-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edddb-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="edddb-142">See also</span></span>

- [<span data-ttu-id="edddb-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="edddb-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="edddb-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="edddb-144">Configuration File Schema</span></span>](../index.md)
