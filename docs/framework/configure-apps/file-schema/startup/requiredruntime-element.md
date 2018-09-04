---
title: '&lt;requiredRuntime&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ac1e1f7bc36d8d2b12b99de2794bb0ba31ddbd7a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518652"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="3888b-102">&lt;requiredRuntime&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="3888b-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="3888b-103">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3888b-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="3888b-104">Este elemento está en desuso y ya no se debe usar.</span><span class="sxs-lookup"><span data-stu-id="3888b-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="3888b-105">El [ `supportedRuntime` ](supportedruntime-element.md) elemento debe usarse en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3888b-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="3888b-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3888b-106">\<configuration></span></span>  
<span data-ttu-id="3888b-107">\<Inicio ></span><span class="sxs-lookup"><span data-stu-id="3888b-107">\<startup></span></span>  
<span data-ttu-id="3888b-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="3888b-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3888b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3888b-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3888b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3888b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3888b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3888b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3888b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3888b-112">Attributes</span></span>  
  
|<span data-ttu-id="3888b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3888b-113">Attribute</span></span>|<span data-ttu-id="3888b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3888b-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="3888b-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="3888b-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3888b-116">Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="3888b-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="3888b-117">El valor de cadena debe coincidir con el nombre del directorio se encuentra en la raíz de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3888b-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="3888b-118">No se puede analizar el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="3888b-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="3888b-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="3888b-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3888b-120">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3888b-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="3888b-121">Atributo safemode</span><span class="sxs-lookup"><span data-stu-id="3888b-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="3888b-122">Valor</span><span class="sxs-lookup"><span data-stu-id="3888b-122">Value</span></span>|<span data-ttu-id="3888b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="3888b-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3888b-124">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="3888b-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="3888b-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3888b-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="3888b-126">El código de inicio en tiempo de ejecución no busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="3888b-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3888b-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3888b-127">Child Elements</span></span>  
 <span data-ttu-id="3888b-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3888b-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3888b-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3888b-129">Parent Elements</span></span>  
  
|<span data-ttu-id="3888b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="3888b-130">Element</span></span>|<span data-ttu-id="3888b-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="3888b-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3888b-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3888b-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="3888b-133">Contiene el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3888b-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3888b-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3888b-134">Remarks</span></span>  
 <span data-ttu-id="3888b-135">Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3888b-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="3888b-136">Las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución deben usar la `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3888b-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3888b-137">Si usas el [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe usar el `<requiredRuntime>` (elemento) para todas las versiones del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3888b-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="3888b-138">El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="3888b-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="3888b-139">El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3888b-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="3888b-140">No se interpreta esta cadena.</span><span class="sxs-lookup"><span data-stu-id="3888b-140">This string is not interpreted.</span></span> <span data-ttu-id="3888b-141">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no está cargado; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="3888b-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3888b-142">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3888b-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3888b-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3888b-143">Example</span></span>  
 <span data-ttu-id="3888b-144">El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3888b-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3888b-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="3888b-145">See Also</span></span>  
 [<span data-ttu-id="3888b-146">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="3888b-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="3888b-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3888b-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3888b-148">\<PaveOver> Especificar la versión en tiempo de ejecución que se va a usar</span><span class="sxs-lookup"><span data-stu-id="3888b-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
