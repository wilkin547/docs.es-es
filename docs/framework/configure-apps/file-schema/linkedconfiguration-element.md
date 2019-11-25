---
title: <linkedConfiguration> (elemento)
ms.date: 03/30/2017
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087960"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="b8a62-102">\<elemento > linkedConfiguration</span><span class="sxs-lookup"><span data-stu-id="b8a62-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="b8a62-103">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="b8a62-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="b8a62-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8a62-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="b8a62-105">&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b8a62-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="b8a62-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="b8a62-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b8a62-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8a62-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="b8a62-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8a62-108">Attribute</span></span>

|           | <span data-ttu-id="b8a62-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8a62-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b8a62-110">**href**</span><span class="sxs-lookup"><span data-stu-id="b8a62-110">**href**</span></span>  | <span data-ttu-id="b8a62-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b8a62-111">Required attribute.</span></span><br><br><span data-ttu-id="b8a62-112">Dirección URL del archivo de configuración que se va a incluir.</span><span class="sxs-lookup"><span data-stu-id="b8a62-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="b8a62-113">El único formato admitido para el atributo **href** es `file://`.</span><span class="sxs-lookup"><span data-stu-id="b8a62-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="b8a62-114">Se admiten los archivos locales y los archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="b8a62-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b8a62-115">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="b8a62-115">Parent element</span></span>

|     | <span data-ttu-id="b8a62-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8a62-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b8a62-117"> **\<assemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="b8a62-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="b8a62-118">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8a62-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b8a62-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8a62-119">Child elements</span></span>

<span data-ttu-id="b8a62-120">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b8a62-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b8a62-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8a62-121">Remarks</span></span>

<span data-ttu-id="b8a62-122">El elemento **\<linkedConfiguration >** simplifica el servicio de ensamblados de componentes.</span><span class="sxs-lookup"><span data-stu-id="b8a62-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="b8a62-123">Si una o más aplicaciones usan un ensamblado que tiene un archivo de configuración que reside en una ubicación conocida, los archivos de configuración de las aplicaciones que utilizan el ensamblado pueden utilizar el elemento **\<linkedConfiguration >** para incluir el archivo de configuración del ensamblado, en lugar de incluir la información de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="b8a62-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="b8a62-124">Cuando se da servicio al ensamblado del componente, al actualizar el archivo de configuración común se proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b8a62-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a62-125">El elemento **\<linkedConfiguration >** no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="b8a62-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="b8a62-126">Las siguientes reglas rigen el uso de archivos de configuración vinculados:</span><span class="sxs-lookup"><span data-stu-id="b8a62-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="b8a62-127">Los valores de los archivos de configuración incluidos solo afectan a la Directiva de enlace del cargador y solo los usa el cargador.</span><span class="sxs-lookup"><span data-stu-id="b8a62-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="b8a62-128">Los archivos de configuración incluidos pueden tener valores distintos de las directivas de enlace, pero esa configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="b8a62-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="b8a62-129">El único formato admitido para el atributo `href` es `file://`.</span><span class="sxs-lookup"><span data-stu-id="b8a62-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="b8a62-130">Se admiten los archivos locales y los archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="b8a62-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="b8a62-131">No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8a62-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="b8a62-132">Todos los archivos de configuración vinculados se combinan para formar un archivo, de forma similar al comportamiento de la Directiva `#include`C++en C/.</span><span class="sxs-lookup"><span data-stu-id="b8a62-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="b8a62-133">El elemento **\<linkedConfiguration >** solo se permite en los archivos de configuración de la aplicación; se omite en *Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="b8a62-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="b8a62-134">Las referencias circulares se detectan y finalizan.</span><span class="sxs-lookup"><span data-stu-id="b8a62-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="b8a62-135">Es decir, si el **\<linkedConfiguration >** elementos de una serie de archivos de configuración forman un bucle, el bucle se detecta y se detiene.</span><span class="sxs-lookup"><span data-stu-id="b8a62-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="b8a62-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8a62-136">Example</span></span>

<span data-ttu-id="b8a62-137">En el ejemplo siguiente se muestra cómo incluir el archivo de configuración desde el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="b8a62-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b8a62-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a62-138">See also</span></span>

- [<span data-ttu-id="b8a62-139"> **\<assemblyBinding >** Element</span><span class="sxs-lookup"><span data-stu-id="b8a62-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="b8a62-140">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b8a62-140">Configuration file schema for the .NET Framework</span></span>](index.md)
