---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dc2bb949c7db4f70c20c3c0b687cacafed8696df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674810"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="04aaf-102">\<configSections > (elemento) para \<configuración ></span><span class="sxs-lookup"><span data-stu-id="04aaf-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="04aaf-103">Contiene las declaraciones de espacio de nombres y la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="04aaf-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="04aaf-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="04aaf-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="04aaf-105">&nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="04aaf-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="04aaf-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="04aaf-106">Attributes</span></span>

<span data-ttu-id="04aaf-107">Ninguna</span><span class="sxs-lookup"><span data-stu-id="04aaf-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="04aaf-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="04aaf-108">Parent element</span></span>

|     | <span data-ttu-id="04aaf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="04aaf-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="04aaf-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="04aaf-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="04aaf-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04aaf-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="04aaf-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04aaf-112">Child elements</span></span>

|     | <span data-ttu-id="04aaf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04aaf-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="04aaf-114">**\<sección >**</span><span class="sxs-lookup"><span data-stu-id="04aaf-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="04aaf-115">Contiene una declaración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="04aaf-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="04aaf-116">**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="04aaf-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="04aaf-117">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="04aaf-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="04aaf-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="04aaf-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="04aaf-119">Quita una sección predefinida o un grupo de sección.</span><span class="sxs-lookup"><span data-stu-id="04aaf-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="04aaf-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="04aaf-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="04aaf-121">Borra todas las secciones definidas anteriormente y grupos de sección.</span><span class="sxs-lookup"><span data-stu-id="04aaf-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="04aaf-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04aaf-122">Remarks</span></span>

<span data-ttu-id="04aaf-123">Si este elemento está en un archivo de configuración, debe ser el primer elemento secundario de la  **\<configuración >** elemento.</span><span class="sxs-lookup"><span data-stu-id="04aaf-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="04aaf-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04aaf-124">Example</span></span>

<span data-ttu-id="04aaf-125">El ejemplo siguiente muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="04aaf-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="04aaf-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="04aaf-126">Configuration file</span></span>

<span data-ttu-id="04aaf-127">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="04aaf-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="04aaf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="04aaf-128">See also</span></span>

- [<span data-ttu-id="04aaf-129">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="04aaf-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
