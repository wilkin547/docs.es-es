---
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
ms.openlocfilehash: 19fa1561ca3acd845918d952379c5227121465b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174074"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="147fe-102">Elemento \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="147fe-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="147fe-103">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="147fe-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="147fe-104">Este elemento está en desuso y ya no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="147fe-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="147fe-105">[`supportedRuntime`](supportedruntime-element.md)En su lugar, se debe usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="147fe-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="147fe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="147fe-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="147fe-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="147fe-107">Attributes and elements</span></span>

<span data-ttu-id="147fe-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="147fe-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="147fe-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="147fe-109">Attributes</span></span>

|<span data-ttu-id="147fe-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="147fe-110">Attribute</span></span>|<span data-ttu-id="147fe-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="147fe-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="147fe-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="147fe-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="147fe-113">Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="147fe-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="147fe-114">El valor de cadena debe coincidir con el nombre de directorio que se encuentra en la .NET Framework raíz de instalación.</span><span class="sxs-lookup"><span data-stu-id="147fe-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="147fe-115">No se analiza el contenido del valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="147fe-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="147fe-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="147fe-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="147fe-117">Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="147fe-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="147fe-118">SafeMode (atributo)</span><span class="sxs-lookup"><span data-stu-id="147fe-118">safemode attribute</span></span>

|<span data-ttu-id="147fe-119">Value</span><span class="sxs-lookup"><span data-stu-id="147fe-119">Value</span></span>|<span data-ttu-id="147fe-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="147fe-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="147fe-121">El código de inicio en tiempo de ejecución busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="147fe-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="147fe-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="147fe-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="147fe-123">El código de inicio en tiempo de ejecución no busca en el registro.</span><span class="sxs-lookup"><span data-stu-id="147fe-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="147fe-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="147fe-124">Child elements</span></span>

<span data-ttu-id="147fe-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="147fe-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="147fe-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="147fe-126">Parent elements</span></span>

|<span data-ttu-id="147fe-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="147fe-127">Element</span></span>|<span data-ttu-id="147fe-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="147fe-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="147fe-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="147fe-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="147fe-130">Contiene el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="147fe-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="147fe-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="147fe-131">Remarks</span></span>

 <span data-ttu-id="147fe-132">Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="147fe-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="147fe-133">Las aplicaciones compiladas con la versión 1,1 o posterior del Runtime deben usar el `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="147fe-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="147fe-134">Si usa la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe usar el `<requiredRuntime>` elemento para todas las versiones del Runtime.</span><span class="sxs-lookup"><span data-stu-id="147fe-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="147fe-135">El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="147fe-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="147fe-136">La `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="147fe-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="147fe-137">Esta cadena no se interpreta.</span><span class="sxs-lookup"><span data-stu-id="147fe-137">This string is not interpreted.</span></span> <span data-ttu-id="147fe-138">Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no se carga; el código de inicio muestra un mensaje de error y se cierra.</span><span class="sxs-lookup"><span data-stu-id="147fe-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="147fe-139">El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="147fe-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="147fe-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="147fe-140">Example</span></span>

<span data-ttu-id="147fe-141">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="147fe-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="147fe-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="147fe-142">See also</span></span>

- [<span data-ttu-id="147fe-143">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="147fe-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="147fe-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="147fe-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="147fe-145">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="147fe-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
