---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "81645354"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="85959-102">\<generatePublisherEvidence> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="85959-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="85959-103">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia para la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="85959-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="85959-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85959-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85959-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85959-105">Attributes and Elements</span></span>  
 <span data-ttu-id="85959-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85959-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85959-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="85959-107">Attributes</span></span>  
  
|<span data-ttu-id="85959-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="85959-108">Attribute</span></span>|<span data-ttu-id="85959-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="85959-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="85959-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="85959-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="85959-111">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="85959-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="85959-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="85959-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="85959-113">Value</span><span class="sxs-lookup"><span data-stu-id="85959-113">Value</span></span>|<span data-ttu-id="85959-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="85959-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="85959-115">No crea ninguna <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="85959-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="85959-116">Crea una <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="85959-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="85959-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="85959-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85959-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85959-118">Child Elements</span></span>  
 <span data-ttu-id="85959-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85959-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85959-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85959-120">Parent Elements</span></span>  
  
|<span data-ttu-id="85959-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="85959-121">Element</span></span>|<span data-ttu-id="85959-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="85959-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85959-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85959-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="85959-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="85959-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85959-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85959-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85959-126">En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="85959-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="85959-127">Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="85959-127">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="85959-128">El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga para crear una <xref:System.Security.Policy.Publisher> evidencia para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="85959-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="85959-129">Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no necesitan <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="85959-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="85959-130">La Directiva CAS estándar no se basa en <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="85959-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="85959-131">Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o que pretenda satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="85959-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="85959-132">(Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).</span><span class="sxs-lookup"><span data-stu-id="85959-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85959-133">Se recomienda que los servicios utilicen el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="85959-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="85959-134">El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="85959-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="85959-135">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="85959-135">Configuration File</span></span>  
 <span data-ttu-id="85959-136">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="85959-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85959-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85959-137">Example</span></span>  
 <span data-ttu-id="85959-138">En el ejemplo siguiente se muestra cómo usar el `<generatePublisherEvidence>` elemento para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="85959-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="85959-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85959-139">See also</span></span>

- [<span data-ttu-id="85959-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="85959-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="85959-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="85959-141">Configuration File Schema</span></span>](../index.md)
