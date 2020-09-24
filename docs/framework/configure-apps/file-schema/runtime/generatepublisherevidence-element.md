---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 506e7873fab8e41fce121587c22d85600a8b1760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158778"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="4ade4-102">\<generatePublisherEvidence> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="4ade4-102">\<generatePublisherEvidence> Element</span></span>

<span data-ttu-id="4ade4-103">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia para la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="4ade4-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="4ade4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ade4-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ade4-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ade4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4ade4-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ade4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ade4-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ade4-107">Attributes</span></span>  
  
|<span data-ttu-id="4ade4-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ade4-108">Attribute</span></span>|<span data-ttu-id="4ade4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ade4-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4ade4-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4ade4-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ade4-111">Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4ade4-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4ade4-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4ade4-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="4ade4-113">Value</span><span class="sxs-lookup"><span data-stu-id="4ade4-113">Value</span></span>|<span data-ttu-id="4ade4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ade4-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4ade4-115">No crea ninguna <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4ade4-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="4ade4-116">Crea una <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4ade4-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4ade4-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ade4-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ade4-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ade4-118">Child Elements</span></span>  

 <span data-ttu-id="4ade4-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ade4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ade4-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ade4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ade4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ade4-121">Element</span></span>|<span data-ttu-id="4ade4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ade4-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ade4-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ade4-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4ade4-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ade4-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ade4-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ade4-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ade4-126">En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4ade4-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="4ade4-127">Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="4ade4-127">For more information, see the "Security Policy Simplification" section in [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="4ade4-128">El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga para crear una <xref:System.Security.Policy.Publisher> evidencia para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ade4-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="4ade4-129">Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no necesitan <xref:System.Security.Policy.Publisher> evidencia.</span><span class="sxs-lookup"><span data-stu-id="4ade4-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4ade4-130">La Directiva CAS estándar no se basa en <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="4ade4-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="4ade4-131">Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o que pretenda satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4ade4-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="4ade4-132">(Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).</span><span class="sxs-lookup"><span data-stu-id="4ade4-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ade4-133">Se recomienda que los servicios utilicen el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="4ade4-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="4ade4-134">El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="4ade4-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4ade4-135">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4ade4-135">Configuration File</span></span>  

 <span data-ttu-id="4ade4-136">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ade4-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ade4-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ade4-137">Example</span></span>  

 <span data-ttu-id="4ade4-138">En el ejemplo siguiente se muestra cómo usar el `<generatePublisherEvidence>` elemento para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ade4-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ade4-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ade4-139">See also</span></span>

- [<span data-ttu-id="4ade4-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4ade4-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4ade4-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4ade4-141">Configuration File Schema</span></span>](../index.md)
