---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645354"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="77a10-102">\<generatePublisherEvidence> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="77a10-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="77a10-103">Especifica si el <xref:System.Security.Policy.Publisher> tiempo de ejecución crea pruebas para la seguridad de acceso al código (CAS).</span><span class="sxs-lookup"><span data-stu-id="77a10-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="77a10-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="77a10-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="77a10-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="77a10-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="77a10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="77a10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a10-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77a10-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77a10-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77a10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="77a10-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77a10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77a10-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="77a10-110">Attributes</span></span>  
  
|<span data-ttu-id="77a10-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="77a10-111">Attribute</span></span>|<span data-ttu-id="77a10-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="77a10-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="77a10-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="77a10-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="77a10-114">Especifica si el <xref:System.Security.Policy.Publisher> tiempo de ejecución crea pruebas.</span><span class="sxs-lookup"><span data-stu-id="77a10-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="77a10-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="77a10-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="77a10-116">Valor</span><span class="sxs-lookup"><span data-stu-id="77a10-116">Value</span></span>|<span data-ttu-id="77a10-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="77a10-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="77a10-118">No crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="77a10-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="77a10-119">Crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="77a10-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="77a10-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="77a10-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77a10-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77a10-121">Child Elements</span></span>  
 <span data-ttu-id="77a10-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="77a10-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77a10-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77a10-123">Parent Elements</span></span>  
  
|<span data-ttu-id="77a10-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="77a10-124">Element</span></span>|<span data-ttu-id="77a10-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="77a10-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="77a10-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77a10-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="77a10-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77a10-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77a10-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77a10-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77a10-129">En .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="77a10-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="77a10-130">Para obtener más información, consulte la sección "Simplificación de directivas de seguridad" en [Cambios](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)de seguridad .</span><span class="sxs-lookup"><span data-stu-id="77a10-130">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="77a10-131">Common Language Runtime (CLR) intenta comprobar la firma Authenticode en tiempo de carga para crear <xref:System.Security.Policy.Publisher> evidencia para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="77a10-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="77a10-132">Sin embargo, de forma <xref:System.Security.Policy.Publisher> predeterminada, la mayoría de las aplicaciones no necesitan evidencia.</span><span class="sxs-lookup"><span data-stu-id="77a10-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="77a10-133">La directiva CAS estándar <xref:System.Security.Policy.PublisherMembershipCondition>no confía en el .</span><span class="sxs-lookup"><span data-stu-id="77a10-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="77a10-134">Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador a <xref:System.Security.Permissions.PublisherIdentityPermission> menos que la aplicación se ejecute en un equipo con directiva CAS personalizada o tenga la intención de satisfacer las demandas en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="77a10-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="77a10-135">(Las demandas de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza.)</span><span class="sxs-lookup"><span data-stu-id="77a10-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77a10-136">Se recomienda que `<generatePublisherEvidence>` los servicios usen el elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="77a10-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="77a10-137">El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="77a10-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="77a10-138">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="77a10-138">Configuration File</span></span>  
 <span data-ttu-id="77a10-139">Este elemento solo se puede utilizar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="77a10-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77a10-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77a10-140">Example</span></span>  
 <span data-ttu-id="77a10-141">En el ejemplo siguiente `<generatePublisherEvidence>` se muestra cómo utilizar el elemento para deshabilitar la comprobación de la directiva de publicador CAS para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="77a10-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77a10-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77a10-142">See also</span></span>

- [<span data-ttu-id="77a10-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="77a10-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="77a10-144">Esquema de archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="77a10-144">Configuration File Schema</span></span>](../index.md)
