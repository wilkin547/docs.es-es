---
title: Elemento <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697497"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="02b12-102">\<requiredRuntime (elemento >)</span><span class="sxs-lookup"><span data-stu-id="02b12-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="02b12-103">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="02b12-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="02b12-104">Este elemento está en desuso y ya no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="02b12-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="02b12-105">En su lugar, se debe usar el elemento [`supportedRuntime`](supportedruntime-element.md) .</span><span class="sxs-lookup"><span data-stu-id="02b12-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="02b12-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="02b12-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="02b12-107">&nbsp;&nbsp;[ **\<startup >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="02b12-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="02b12-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="02b12-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="02b12-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02b12-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02b12-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02b12-110">Attributes and elements</span></span>

<span data-ttu-id="02b12-111">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02b12-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="02b12-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="02b12-112">Attributes</span></span>

|<span data-ttu-id="02b12-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="02b12-113">Attribute</span></span>|<span data-ttu-id="02b12-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="02b12-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="02b12-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="02b12-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="02b12-116">Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="02b12-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="02b12-117">El valor de cadena debe coincidir con el nombre de directorio que se encuentra en la .NET Framework raíz de instalación.</span><span class="sxs-lookup"><span data-stu-id="02b12-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="02b12-118">No se analiza el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="02b12-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="02b12-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="02b12-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="02b12-120">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="02b12-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="02b12-121">SafeMode (atributo)</span><span class="sxs-lookup"><span data-stu-id="02b12-121">safemode attribute</span></span>

|<span data-ttu-id="02b12-122">Valor</span><span class="sxs-lookup"><span data-stu-id="02b12-122">Value</span></span>|<span data-ttu-id="02b12-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="02b12-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="02b12-124">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="02b12-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="02b12-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="02b12-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="02b12-126">El código de inicio en tiempo de ejecución no busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="02b12-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="02b12-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02b12-127">Child elements</span></span>

<span data-ttu-id="02b12-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02b12-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="02b12-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02b12-129">Parent elements</span></span>

|<span data-ttu-id="02b12-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="02b12-130">Element</span></span>|<span data-ttu-id="02b12-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="02b12-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="02b12-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02b12-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="02b12-133">Contiene el elemento `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="02b12-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="02b12-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02b12-134">Remarks</span></span>
 <span data-ttu-id="02b12-135">Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el elemento `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="02b12-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="02b12-136">Las aplicaciones compiladas con la versión 1,1 o posterior del Runtime deben usar el elemento `<supportedRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="02b12-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="02b12-137">Si usa la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe utilizar el elemento `<requiredRuntime>` para todas las versiones del Runtime.</span><span class="sxs-lookup"><span data-stu-id="02b12-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="02b12-138">El elemento `<supportedRuntime>` se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="02b12-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="02b12-139">El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02b12-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="02b12-140">Esta cadena no se interpreta.</span><span class="sxs-lookup"><span data-stu-id="02b12-140">This string is not interpreted.</span></span> <span data-ttu-id="02b12-141">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no se carga; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="02b12-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="02b12-142">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el elemento `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="02b12-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="02b12-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02b12-143">Example</span></span>

<span data-ttu-id="02b12-144">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="02b12-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="02b12-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="02b12-145">See also</span></span>

- [<span data-ttu-id="02b12-146">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="02b12-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="02b12-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="02b12-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="02b12-148">Cómo: configurar una aplicación para admitir .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="02b12-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
