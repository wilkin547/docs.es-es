---
description: 'Más información sobre: <sectionGroup> elemento para <configSections>'
title: Elemento <sectionGroup> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: 0d822b98acbc041b9d6e146e9cd15848a73d2f88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639892"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="7f093-103">Elemento \<sectionGroup> para \<configSections></span><span class="sxs-lookup"><span data-stu-id="7f093-103">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="7f093-104">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f093-104">Defines a namespace for configuration sections.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**

## <a name="syntax"></a><span data-ttu-id="7f093-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f093-105">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="7f093-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f093-106">Attribute</span></span>

|           | <span data-ttu-id="7f093-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f093-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7f093-108">**name**</span><span class="sxs-lookup"><span data-stu-id="7f093-108">**name**</span></span>  | <span data-ttu-id="7f093-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7f093-109">Required attribute.</span></span><br><br><span data-ttu-id="7f093-110">Especifica el nombre del grupo de sección que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="7f093-110">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7f093-111">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="7f093-111">Parent element</span></span>

|     | <span data-ttu-id="7f093-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f093-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7f093-113">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="7f093-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="7f093-114">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7f093-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7f093-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f093-115">Child elements</span></span>

|     | <span data-ttu-id="7f093-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f093-116">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="7f093-117">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f093-117">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7f093-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f093-118">Remarks</span></span>

<span data-ttu-id="7f093-119">Al declarar un grupo de secciones, se crea una etiqueta de contenedor para las secciones de configuración y se garantiza que no hay conflictos de nomenclatura con las secciones de configuración definidas por otro usuario.</span><span class="sxs-lookup"><span data-stu-id="7f093-119">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="7f093-120">Puede anidar **\<sectionGroup>** elementos entre sí.</span><span class="sxs-lookup"><span data-stu-id="7f093-120">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="7f093-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f093-121">Example</span></span>

<span data-ttu-id="7f093-122">En el ejemplo siguiente se muestra cómo declarar un grupo de secciones y declarar secciones dentro de un grupo de secciones:</span><span class="sxs-lookup"><span data-stu-id="7f093-122">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7f093-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7f093-123">Configuration file</span></span>

<span data-ttu-id="7f093-124">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f093-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f093-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f093-125">See also</span></span>

- [<span data-ttu-id="7f093-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7f093-126">Configuration file schema for the .NET Framework</span></span>](index.md)
