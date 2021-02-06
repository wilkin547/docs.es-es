---
description: 'Más información acerca de: <requiredRuntime> elemento'
title: <requiredRuntime> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: e9d0a88a65f72ec03f3b2b124920d8265b8bf0c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639853"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="7d978-103">Elemento \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="7d978-103">\<requiredRuntime> element</span></span>

<span data-ttu-id="7d978-104">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="7d978-104">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="7d978-105">Este elemento está en desuso y ya no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="7d978-105">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="7d978-106">[`supportedRuntime`](supportedruntime-element.md)En su lugar, se debe usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="7d978-106">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="7d978-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d978-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d978-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7d978-108">Attributes and elements</span></span>

<span data-ttu-id="7d978-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7d978-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d978-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7d978-110">Attributes</span></span>

|<span data-ttu-id="7d978-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="7d978-111">Attribute</span></span>|<span data-ttu-id="7d978-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d978-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="7d978-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="7d978-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7d978-114">Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d978-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="7d978-115">El valor de cadena debe coincidir con el nombre de directorio que se encuentra en la .NET Framework raíz de instalación.</span><span class="sxs-lookup"><span data-stu-id="7d978-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="7d978-116">No se analiza el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="7d978-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="7d978-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="7d978-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7d978-118">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d978-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="7d978-119">SafeMode (atributo)</span><span class="sxs-lookup"><span data-stu-id="7d978-119">safemode attribute</span></span>

|<span data-ttu-id="7d978-120">Value</span><span class="sxs-lookup"><span data-stu-id="7d978-120">Value</span></span>|<span data-ttu-id="7d978-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d978-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7d978-122">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="7d978-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="7d978-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d978-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="7d978-124">El código de inicio en tiempo de ejecución no busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="7d978-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7d978-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7d978-125">Child elements</span></span>

<span data-ttu-id="7d978-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7d978-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d978-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7d978-127">Parent elements</span></span>

|<span data-ttu-id="7d978-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d978-128">Element</span></span>|<span data-ttu-id="7d978-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d978-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7d978-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d978-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="7d978-131">Contiene el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="7d978-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7d978-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7d978-132">Remarks</span></span>

 <span data-ttu-id="7d978-133">Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="7d978-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="7d978-134">Las aplicaciones compiladas con la versión 1,1 o posterior del Runtime deben usar el `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="7d978-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="7d978-135">Si usa la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe usar el `<requiredRuntime>` elemento para todas las versiones del Runtime.</span><span class="sxs-lookup"><span data-stu-id="7d978-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="7d978-136">El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="7d978-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="7d978-137">La `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d978-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="7d978-138">Esta cadena no se interpreta.</span><span class="sxs-lookup"><span data-stu-id="7d978-138">This string is not interpreted.</span></span> <span data-ttu-id="7d978-139">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no se carga; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="7d978-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="7d978-140">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="7d978-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="7d978-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d978-141">Example</span></span>

<span data-ttu-id="7d978-142">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7d978-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7d978-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d978-143">See also</span></span>

- [<span data-ttu-id="7d978-144">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="7d978-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7d978-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7d978-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7d978-146">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7d978-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
