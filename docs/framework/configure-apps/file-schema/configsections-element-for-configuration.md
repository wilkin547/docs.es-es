---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119015"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="70a0d-102">\<elemento > configSections para la configuración de \<</span><span class="sxs-lookup"><span data-stu-id="70a0d-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="70a0d-103">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="70a0d-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="70a0d-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="70a0d-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="70a0d-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="70a0d-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="70a0d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="70a0d-106">Attributes</span></span>

<span data-ttu-id="70a0d-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="70a0d-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="70a0d-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="70a0d-108">Parent element</span></span>

|     | <span data-ttu-id="70a0d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a0d-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="70a0d-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="70a0d-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="70a0d-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70a0d-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="70a0d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70a0d-112">Child elements</span></span>

|     | <span data-ttu-id="70a0d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a0d-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="70a0d-114"> **\<sección >** </span><span class="sxs-lookup"><span data-stu-id="70a0d-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="70a0d-115">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="70a0d-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="70a0d-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="70a0d-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="70a0d-117">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="70a0d-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="70a0d-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="70a0d-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="70a0d-119">Quita una sección o grupo de sección predefinido.</span><span class="sxs-lookup"><span data-stu-id="70a0d-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="70a0d-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="70a0d-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="70a0d-121">Borra todas las secciones y grupos de sección definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="70a0d-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="70a0d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70a0d-122">Remarks</span></span>

<span data-ttu-id="70a0d-123">Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del elemento **\<configuration >** .</span><span class="sxs-lookup"><span data-stu-id="70a0d-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="70a0d-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a0d-124">Example</span></span>

<span data-ttu-id="70a0d-125">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="70a0d-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="70a0d-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="70a0d-126">Configuration file</span></span>

<span data-ttu-id="70a0d-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="70a0d-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="70a0d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="70a0d-128">See also</span></span>

- [<span data-ttu-id="70a0d-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70a0d-129">Configuration file schema for the .NET Framework</span></span>](index.md)
