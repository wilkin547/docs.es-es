---
title: '&lt;linkedConfiguration&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: dffff7fefa80f420e61045b21b0e0c1a170e2911
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="06258-102">\<linkedConfiguration > elemento</span><span class="sxs-lookup"><span data-stu-id="06258-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="06258-103">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="06258-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="06258-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="06258-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="06258-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="06258-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="06258-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="06258-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="06258-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06258-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="06258-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="06258-108">Attribute</span></span>

|           | <span data-ttu-id="06258-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="06258-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="06258-110">**href**</span><span class="sxs-lookup"><span data-stu-id="06258-110">**href**</span></span>  | <span data-ttu-id="06258-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="06258-111">Required attribute.</span></span><br><br><span data-ttu-id="06258-112">La dirección URL del archivo de configuración para incluir.</span><span class="sxs-lookup"><span data-stu-id="06258-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="06258-113">El único formato compatible para la **href** atributo es `file://`.</span><span class="sxs-lookup"><span data-stu-id="06258-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="06258-114">Se admiten archivos locales y archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="06258-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="06258-115">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="06258-115">Parent element</span></span>

|     | <span data-ttu-id="06258-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="06258-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="06258-117">**\<assemblyBinding >** elemento</span><span class="sxs-lookup"><span data-stu-id="06258-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="06258-118">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="06258-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="06258-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06258-119">Child elements</span></span>

<span data-ttu-id="06258-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="06258-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="06258-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06258-121">Remarks</span></span>

<span data-ttu-id="06258-122">El  **\<linkedConfiguration >** elemento simplifica el servicio para los ensamblados de componente.</span><span class="sxs-lookup"><span data-stu-id="06258-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="06258-123">Si una o varias aplicaciones utilizan un ensamblado que tiene un archivo de configuración que residen en una ubicación conocida, los archivos de configuración de las aplicaciones que utilizan el ensamblado se pueden usar el  **\<linkedConfiguration >** elemento que se va a incluir el archivo de configuración de ensamblado, en lugar de incluir información de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="06258-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="06258-124">Cuando se repara el ensamblado de componente, actualizar el archivo de configuración comunes proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="06258-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="06258-125">El  **\<linkedConfiguration >** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="06258-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="06258-126">Las reglas siguientes rigen el uso de archivos de configuración vinculados:</span><span class="sxs-lookup"><span data-stu-id="06258-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="06258-127">Los valores de configuración incluyen archivos solo afecta a la directiva de enlace de cargador y solo son utilizados por el cargador.</span><span class="sxs-lookup"><span data-stu-id="06258-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="06258-128">Los archivos de configuración incluidos pueden tener valores distintos de las directivas de enlace, pero dicha configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="06258-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="06258-129">El único formato compatible para la `href` atributo es `file://`.</span><span class="sxs-lookup"><span data-stu-id="06258-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="06258-130">Se admiten archivos locales y archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="06258-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="06258-131">No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="06258-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="06258-132">Todos los archivos de configuración vinculados se combinan para formar un único archivo, de forma similar al comportamiento de la `#include` directiva en C o C++.</span><span class="sxs-lookup"><span data-stu-id="06258-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="06258-133">El  **\<linkedConfiguration >** elemento solo se permite en archivos de configuración de aplicación; se omite en *Machine.config*.</span><span class="sxs-lookup"><span data-stu-id="06258-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="06258-134">Las referencias circulares se detectan y se termina.</span><span class="sxs-lookup"><span data-stu-id="06258-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="06258-135">Es decir, si la  **\<linkedConfiguration >** elementos de una serie de archivos de configuración forman un bucle, se detecta y se detuvo el bucle.</span><span class="sxs-lookup"><span data-stu-id="06258-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="06258-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06258-136">Example</span></span>

<span data-ttu-id="06258-137">En el ejemplo siguiente se muestra cómo puede incluir el archivo de configuración desde el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="06258-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="06258-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="06258-138">See also</span></span>

<span data-ttu-id="06258-139">[**\<assemblyBinding >** elemento](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="06258-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="06258-140">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="06258-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
