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
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215259"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="74786-102">\<elemento sectionGroup > para \<configSections ></span><span class="sxs-lookup"><span data-stu-id="74786-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="74786-103">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="74786-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="74786-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="74786-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="74786-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="74786-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="74786-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="74786-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="74786-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74786-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="74786-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="74786-108">Attribute</span></span>

|           | <span data-ttu-id="74786-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="74786-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="74786-110">**name**</span><span class="sxs-lookup"><span data-stu-id="74786-110">**name**</span></span>  | <span data-ttu-id="74786-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="74786-111">Required attribute.</span></span><br><br><span data-ttu-id="74786-112">Especifica el nombre del grupo de sección que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="74786-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="74786-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="74786-113">Parent element</span></span>

|     | <span data-ttu-id="74786-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="74786-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="74786-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="74786-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="74786-116">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="74786-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="74786-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74786-117">Child elements</span></span>

|     | <span data-ttu-id="74786-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="74786-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="74786-119"> **\<sección >** </span><span class="sxs-lookup"><span data-stu-id="74786-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="74786-120">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="74786-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="74786-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74786-121">Remarks</span></span>

<span data-ttu-id="74786-122">Al declarar un grupo de secciones, se crea una etiqueta de contenedor para las secciones de configuración y se garantiza que no hay conflictos de nomenclatura con las secciones de configuración definidas por otro usuario.</span><span class="sxs-lookup"><span data-stu-id="74786-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="74786-123">Puede anidar **\<elementos > sectionGroup** entre sí.</span><span class="sxs-lookup"><span data-stu-id="74786-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="74786-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74786-124">Example</span></span>

<span data-ttu-id="74786-125">En el ejemplo siguiente se muestra cómo declarar un grupo de secciones y declarar secciones dentro de un grupo de secciones:</span><span class="sxs-lookup"><span data-stu-id="74786-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="74786-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="74786-126">Configuration file</span></span>

<span data-ttu-id="74786-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="74786-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="74786-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74786-128">See also</span></span>

- [<span data-ttu-id="74786-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74786-129">Configuration file schema for the .NET Framework</span></span>](index.md)
