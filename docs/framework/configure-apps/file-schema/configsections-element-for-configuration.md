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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155354"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="ec0db-102">\<configSections> \<elemento para la configuración></span><span class="sxs-lookup"><span data-stu-id="ec0db-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="ec0db-103">Contiene declaraciones de sección de configuración y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ec0db-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="ec0db-104">configuración &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="ec0db-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="ec0db-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec0db-105">Attributes</span></span>

<span data-ttu-id="ec0db-106">None</span><span class="sxs-lookup"><span data-stu-id="ec0db-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ec0db-107">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="ec0db-107">Parent element</span></span>

|     | <span data-ttu-id="ec0db-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0db-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ec0db-109">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="ec0db-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="ec0db-110">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec0db-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ec0db-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec0db-111">Child elements</span></span>

|     | <span data-ttu-id="ec0db-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0db-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ec0db-113">**\<sección>**</span><span class="sxs-lookup"><span data-stu-id="ec0db-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="ec0db-114">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="ec0db-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="ec0db-115">**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="ec0db-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="ec0db-116">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="ec0db-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="ec0db-117">**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="ec0db-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="ec0db-118">Quita una sección o un grupo de secciones predefinidos.</span><span class="sxs-lookup"><span data-stu-id="ec0db-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="ec0db-119">**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="ec0db-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="ec0db-120">Borra todas las secciones y grupos de secciones definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ec0db-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ec0db-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec0db-121">Remarks</span></span>

<span data-ttu-id="ec0db-122">Si este elemento está en un archivo de configuración, debe ser el primer elemento secundario del elemento \*\* \<de configuración>.\*\*</span><span class="sxs-lookup"><span data-stu-id="ec0db-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="ec0db-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec0db-123">Example</span></span>

<span data-ttu-id="ec0db-124">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="ec0db-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ec0db-125">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ec0db-125">Configuration file</span></span>

<span data-ttu-id="ec0db-126">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec0db-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec0db-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec0db-127">See also</span></span>

- [<span data-ttu-id="ec0db-128">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ec0db-128">Configuration file schema for the .NET Framework</span></span>](index.md)
