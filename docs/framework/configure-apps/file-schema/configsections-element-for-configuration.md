---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214822"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="0d594-102">\<elemento > configSections para la configuración de \<></span><span class="sxs-lookup"><span data-stu-id="0d594-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="0d594-103">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d594-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="0d594-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d594-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="0d594-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="0d594-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="0d594-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0d594-106">Attributes</span></span>

<span data-ttu-id="0d594-107">None</span><span class="sxs-lookup"><span data-stu-id="0d594-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0d594-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="0d594-108">Parent element</span></span>

|     | <span data-ttu-id="0d594-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d594-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d594-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0d594-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="0d594-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d594-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0d594-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d594-112">Child elements</span></span>

|     | <span data-ttu-id="0d594-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d594-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d594-114"> **\<sección >** </span><span class="sxs-lookup"><span data-stu-id="0d594-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="0d594-115">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="0d594-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="0d594-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="0d594-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="0d594-117">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="0d594-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="0d594-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="0d594-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="0d594-119">Quita una sección o grupo de sección predefinido.</span><span class="sxs-lookup"><span data-stu-id="0d594-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="0d594-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="0d594-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="0d594-121">Borra todas las secciones y grupos de sección definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="0d594-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0d594-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d594-122">Remarks</span></span>

<span data-ttu-id="0d594-123">Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del elemento **\<configuration >** .</span><span class="sxs-lookup"><span data-stu-id="0d594-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="0d594-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d594-124">Example</span></span>

<span data-ttu-id="0d594-125">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="0d594-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0d594-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0d594-126">Configuration file</span></span>

<span data-ttu-id="0d594-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d594-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d594-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d594-128">See also</span></span>

- [<span data-ttu-id="0d594-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d594-129">Configuration file schema for the .NET Framework</span></span>](index.md)
