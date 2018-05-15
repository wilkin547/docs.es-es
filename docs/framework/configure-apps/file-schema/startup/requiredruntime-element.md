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
ms.openlocfilehash: 184547dd47e728f17f28105e74b2ca67c1436efc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="60d3c-102">&lt;requiredRuntime&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="60d3c-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="60d3c-103">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="60d3c-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="60d3c-104">Este elemento está en desuso y ya no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="60d3c-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="60d3c-105">El [ `supportedRuntime` ](supportedruntime-element.md) deberían usar el elemento en su lugar.</span><span class="sxs-lookup"><span data-stu-id="60d3c-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="60d3c-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="60d3c-106">\<configuration></span></span>  
<span data-ttu-id="60d3c-107">\<Inicio ></span><span class="sxs-lookup"><span data-stu-id="60d3c-107">\<startup></span></span>  
<span data-ttu-id="60d3c-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="60d3c-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d3c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60d3c-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60d3c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60d3c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="60d3c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="60d3c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60d3c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="60d3c-112">Attributes</span></span>  
  
|<span data-ttu-id="60d3c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="60d3c-113">Attribute</span></span>|<span data-ttu-id="60d3c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="60d3c-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="60d3c-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="60d3c-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="60d3c-116">Un valor de cadena que especifica la versión de .NET Framework que es compatible con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="60d3c-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="60d3c-117">El valor de cadena debe coincidir con el nombre de directorio se encuentra en la raíz de la instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60d3c-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="60d3c-118">No se analiza el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="60d3c-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="60d3c-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="60d3c-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="60d3c-120">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60d3c-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="60d3c-121">Atributo safemode</span><span class="sxs-lookup"><span data-stu-id="60d3c-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="60d3c-122">Valor</span><span class="sxs-lookup"><span data-stu-id="60d3c-122">Value</span></span>|<span data-ttu-id="60d3c-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="60d3c-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="60d3c-124">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="60d3c-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="60d3c-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="60d3c-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="60d3c-126">El código de inicio en tiempo de ejecución no busque en el registro.</span><span class="sxs-lookup"><span data-stu-id="60d3c-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60d3c-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60d3c-127">Child Elements</span></span>  
 <span data-ttu-id="60d3c-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60d3c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60d3c-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60d3c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="60d3c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="60d3c-130">Element</span></span>|<span data-ttu-id="60d3c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="60d3c-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="60d3c-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60d3c-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="60d3c-133">Contiene el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="60d3c-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60d3c-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60d3c-134">Remarks</span></span>  
 <span data-ttu-id="60d3c-135">Las aplicaciones compiladas para admitir solo la versión 1.0 del tiempo de ejecución deben usar la `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="60d3c-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="60d3c-136">Las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución deben usar el `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="60d3c-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60d3c-137">Si usas el [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe utilizar el `<requiredRuntime>` (elemento) para todas las versiones del runtime.</span><span class="sxs-lookup"><span data-stu-id="60d3c-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="60d3c-138">El `<supportedRuntime>` elemento se omite cuando usa [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="60d3c-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="60d3c-139">El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación para la versión especificada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60d3c-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="60d3c-140">Esta cadena no se interpreta.</span><span class="sxs-lookup"><span data-stu-id="60d3c-140">This string is not interpreted.</span></span> <span data-ttu-id="60d3c-141">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no está cargado; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="60d3c-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60d3c-142">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="60d3c-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60d3c-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60d3c-143">Example</span></span>  
 <span data-ttu-id="60d3c-144">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="60d3c-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60d3c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="60d3c-145">See Also</span></span>  
 [<span data-ttu-id="60d3c-146">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="60d3c-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="60d3c-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="60d3c-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="60d3c-148">\<PaveOver> Especificar la versión en tiempo de ejecución que se va a usar</span><span class="sxs-lookup"><span data-stu-id="60d3c-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
