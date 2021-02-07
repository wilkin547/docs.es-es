---
description: 'Más información sobre: <configSections> elemento para <configuration>'
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 543ceed8d53fd299e8a0b65594592b64d6b833a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698994"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="19368-103">Elemento \<configSections> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="19368-103">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="19368-104">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="19368-104">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="19368-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="19368-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="19368-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="19368-106">Attributes</span></span>

<span data-ttu-id="19368-107">None</span><span class="sxs-lookup"><span data-stu-id="19368-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="19368-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="19368-108">Parent element</span></span>

|     | <span data-ttu-id="19368-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="19368-109">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="19368-110">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19368-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="19368-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="19368-111">Child elements</span></span>

|     | <span data-ttu-id="19368-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="19368-112">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="19368-113">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="19368-113">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="19368-114">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="19368-114">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="19368-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19368-115">Remarks</span></span>

<span data-ttu-id="19368-116">Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="19368-116">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="19368-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19368-117">Example</span></span>

<span data-ttu-id="19368-118">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="19368-118">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="19368-119">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="19368-119">Configuration file</span></span>

<span data-ttu-id="19368-120">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19368-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="19368-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="19368-121">See also</span></span>

- [<span data-ttu-id="19368-122">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19368-122">Configuration file schema for the .NET Framework</span></span>](index.md)
