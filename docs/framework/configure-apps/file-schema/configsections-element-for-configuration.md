---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155354"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="68056-102">Elemento \<configSections> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="68056-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="68056-103">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="68056-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="68056-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="68056-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="68056-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="68056-105">Attributes</span></span>

<span data-ttu-id="68056-106">None</span><span class="sxs-lookup"><span data-stu-id="68056-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="68056-107">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="68056-107">Parent element</span></span>

|     | <span data-ttu-id="68056-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="68056-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="68056-109">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68056-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="68056-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68056-110">Child elements</span></span>

|     | <span data-ttu-id="68056-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="68056-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="68056-112">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="68056-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="68056-113">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="68056-113">Defines a namespace for configuration sections.</span></span> |
| [**\<remove>**](remove-element-for-configsections.md) | <span data-ttu-id="68056-114">Quita una sección o grupo de sección predefinido.</span><span class="sxs-lookup"><span data-stu-id="68056-114">Removes a predefined section or section group.</span></span> |
| [**\<clear>**](clear-element-for-configsections.md) | <span data-ttu-id="68056-115">Borra todas las secciones y grupos de sección definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="68056-115">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="68056-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68056-116">Remarks</span></span>

<span data-ttu-id="68056-117">Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="68056-117">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="68056-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68056-118">Example</span></span>

<span data-ttu-id="68056-119">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="68056-119">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="68056-120">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="68056-120">Configuration file</span></span>

<span data-ttu-id="68056-121">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68056-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="68056-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68056-122">See also</span></span>

- [<span data-ttu-id="68056-123">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="68056-123">Configuration file schema for the .NET Framework</span></span>](index.md)
