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
ms.openlocfilehash: 5e528a8b81fa3d9abc4f345d18f01e33f483a4a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673847"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="a5cab-102">\<requiredRuntime > elemento</span><span class="sxs-lookup"><span data-stu-id="a5cab-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="a5cab-103">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a5cab-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="a5cab-104">Este elemento está en desuso y ya no se debe usar.</span><span class="sxs-lookup"><span data-stu-id="a5cab-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="a5cab-105">El [ `supportedRuntime` ](supportedruntime-element.md) elemento debe usarse en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a5cab-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="a5cab-106">\<Configuración > \<Inicio > \<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="a5cab-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="a5cab-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5cab-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a5cab-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5cab-108">Attributes and elements</span></span>

<span data-ttu-id="a5cab-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5cab-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a5cab-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5cab-110">Attributes</span></span>

|<span data-ttu-id="a5cab-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a5cab-111">Attribute</span></span>|<span data-ttu-id="a5cab-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5cab-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="a5cab-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="a5cab-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a5cab-114">Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5cab-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="a5cab-115">El valor de cadena debe coincidir con el nombre del directorio se encuentra en la raíz de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5cab-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="a5cab-116">No se puede analizar el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="a5cab-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="a5cab-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="a5cab-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a5cab-118">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5cab-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="a5cab-119">atributo safemode</span><span class="sxs-lookup"><span data-stu-id="a5cab-119">safemode attribute</span></span>

|<span data-ttu-id="a5cab-120">Valor</span><span class="sxs-lookup"><span data-stu-id="a5cab-120">Value</span></span>|<span data-ttu-id="a5cab-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5cab-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a5cab-122">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="a5cab-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="a5cab-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5cab-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="a5cab-124">El código de inicio en tiempo de ejecución no busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="a5cab-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a5cab-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a5cab-125">Child elements</span></span>

<span data-ttu-id="a5cab-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a5cab-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a5cab-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5cab-127">Parent elements</span></span>

|<span data-ttu-id="a5cab-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5cab-128">Element</span></span>|<span data-ttu-id="a5cab-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5cab-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a5cab-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5cab-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="a5cab-131">Contiene el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5cab-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5cab-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5cab-132">Remarks</span></span>
 <span data-ttu-id="a5cab-133">Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5cab-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="a5cab-134">Las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución deben usar la `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5cab-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="a5cab-135">Si usas el [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe usar el `<requiredRuntime>` (elemento) para todas las versiones del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5cab-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="a5cab-136">El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="a5cab-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="a5cab-137">El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5cab-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="a5cab-138">No se interpreta esta cadena.</span><span class="sxs-lookup"><span data-stu-id="a5cab-138">This string is not interpreted.</span></span> <span data-ttu-id="a5cab-139">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no está cargado; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="a5cab-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="a5cab-140">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5cab-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="a5cab-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5cab-141">Example</span></span>

<span data-ttu-id="a5cab-142">El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5cab-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a5cab-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5cab-143">See also</span></span>

- [<span data-ttu-id="a5cab-144">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="a5cab-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a5cab-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5cab-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a5cab-146">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a5cab-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)