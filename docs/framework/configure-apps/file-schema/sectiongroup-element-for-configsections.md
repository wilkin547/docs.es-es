---
title: Elemento <sectionGroup> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215259"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="686c8-102">Elemento \<sectionGroup> para \<configSections></span><span class="sxs-lookup"><span data-stu-id="686c8-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="686c8-103">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="686c8-103">Defines a namespace for configuration sections.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**

## <a name="syntax"></a><span data-ttu-id="686c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="686c8-104">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="686c8-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="686c8-105">Attribute</span></span>

|           | <span data-ttu-id="686c8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="686c8-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="686c8-107">**name**</span><span class="sxs-lookup"><span data-stu-id="686c8-107">**name**</span></span>  | <span data-ttu-id="686c8-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="686c8-108">Required attribute.</span></span><br><br><span data-ttu-id="686c8-109">Especifica el nombre del grupo de sección que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="686c8-109">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="686c8-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="686c8-110">Parent element</span></span>

|     | <span data-ttu-id="686c8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="686c8-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="686c8-112">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="686c8-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="686c8-113">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="686c8-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="686c8-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="686c8-114">Child elements</span></span>

|     | <span data-ttu-id="686c8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="686c8-115">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="686c8-116">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="686c8-116">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="686c8-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="686c8-117">Remarks</span></span>

<span data-ttu-id="686c8-118">Al declarar un grupo de secciones, se crea una etiqueta de contenedor para las secciones de configuración y se garantiza que no hay conflictos de nomenclatura con las secciones de configuración definidas por otro usuario.</span><span class="sxs-lookup"><span data-stu-id="686c8-118">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="686c8-119">Puede anidar **\<sectionGroup>** elementos entre sí.</span><span class="sxs-lookup"><span data-stu-id="686c8-119">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="686c8-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="686c8-120">Example</span></span>

<span data-ttu-id="686c8-121">En el ejemplo siguiente se muestra cómo declarar un grupo de secciones y declarar secciones dentro de un grupo de secciones:</span><span class="sxs-lookup"><span data-stu-id="686c8-121">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="686c8-122">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="686c8-122">Configuration file</span></span>

<span data-ttu-id="686c8-123">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="686c8-123">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="686c8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="686c8-124">See also</span></span>

- [<span data-ttu-id="686c8-125">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="686c8-125">Configuration file schema for the .NET Framework</span></span>](index.md)
