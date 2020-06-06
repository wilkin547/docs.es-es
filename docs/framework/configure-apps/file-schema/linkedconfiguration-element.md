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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087960"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="30299-102">Elemento \<linkedConfiguration></span><span class="sxs-lookup"><span data-stu-id="30299-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="30299-103">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="30299-103">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="30299-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30299-104">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="30299-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="30299-105">Attribute</span></span>

|           | <span data-ttu-id="30299-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="30299-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="30299-107">**href**</span><span class="sxs-lookup"><span data-stu-id="30299-107">**href**</span></span>  | <span data-ttu-id="30299-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="30299-108">Required attribute.</span></span><br><br><span data-ttu-id="30299-109">Dirección URL del archivo de configuración que se va a incluir.</span><span class="sxs-lookup"><span data-stu-id="30299-109">The URL of the configuration file to include.</span></span> <span data-ttu-id="30299-110">El único formato admitido para el atributo **href** es `file://` .</span><span class="sxs-lookup"><span data-stu-id="30299-110">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="30299-111">Se admiten los archivos locales y los archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="30299-111">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="30299-112">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="30299-112">Parent element</span></span>

|     | <span data-ttu-id="30299-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="30299-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="30299-114">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="30299-114">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="30299-115">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="30299-115">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="30299-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30299-116">Child elements</span></span>

<span data-ttu-id="30299-117">None</span><span class="sxs-lookup"><span data-stu-id="30299-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="30299-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30299-118">Remarks</span></span>

<span data-ttu-id="30299-119">El **\<linkedConfiguration>** elemento simplifica el servicio para los ensamblados de componentes.</span><span class="sxs-lookup"><span data-stu-id="30299-119">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="30299-120">Si una o más aplicaciones usan un ensamblado que tiene un archivo de configuración que reside en una ubicación conocida, los archivos de configuración de las aplicaciones que utilizan el ensamblado pueden usar el **\<linkedConfiguration>** elemento para incluir el archivo de configuración del ensamblado, en lugar de incluir la información de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="30299-120">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="30299-121">Cuando se da servicio al ensamblado del componente, al actualizar el archivo de configuración común se proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="30299-121">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="30299-122">El **\<linkedConfiguration>** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="30299-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="30299-123">Las siguientes reglas rigen el uso de archivos de configuración vinculados:</span><span class="sxs-lookup"><span data-stu-id="30299-123">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="30299-124">Los valores de los archivos de configuración incluidos solo afectan a la Directiva de enlace del cargador y solo los usa el cargador.</span><span class="sxs-lookup"><span data-stu-id="30299-124">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="30299-125">Los archivos de configuración incluidos pueden tener valores distintos de las directivas de enlace, pero esa configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="30299-125">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="30299-126">El único formato admitido para el `href` atributo es `file://` .</span><span class="sxs-lookup"><span data-stu-id="30299-126">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="30299-127">Se admiten los archivos locales y los archivos UNC.</span><span class="sxs-lookup"><span data-stu-id="30299-127">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="30299-128">No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="30299-128">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="30299-129">Todos los archivos de configuración vinculados se combinan para formar un archivo, de forma similar al comportamiento de la `#include` Directiva en C/C++.</span><span class="sxs-lookup"><span data-stu-id="30299-129">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="30299-130">El **\<linkedConfiguration>** elemento solo se permite en los archivos de configuración de la aplicación; se omite en *Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="30299-130">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="30299-131">Las referencias circulares se detectan y finalizan.</span><span class="sxs-lookup"><span data-stu-id="30299-131">Circular references are detected and terminated.</span></span> <span data-ttu-id="30299-132">Es decir, si los **\<linkedConfiguration>** elementos de una serie de archivos de configuración forman un bucle, el bucle se detecta y se detiene.</span><span class="sxs-lookup"><span data-stu-id="30299-132">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="30299-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30299-133">Example</span></span>

<span data-ttu-id="30299-134">En el ejemplo siguiente se muestra cómo incluir el archivo de configuración desde el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="30299-134">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="30299-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30299-135">See also</span></span>

- [<span data-ttu-id="30299-136">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="30299-136">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="30299-137">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="30299-137">Configuration file schema for the .NET Framework</span></span>](index.md)
