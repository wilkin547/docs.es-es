---
title: '&lt;sectionGroup&gt; (elemento) para &lt;configSections&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c5c040a322c38da319f2e964519f94d761327e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="2179f-102">\<sectionGroup > (elemento) para \<configSections ></span><span class="sxs-lookup"><span data-stu-id="2179f-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="2179f-103">Define un espacio de nombres de secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="2179f-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="2179f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2179f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2179f-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2179f-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="2179f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="2179f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2179f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2179f-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="2179f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2179f-108">Attribute</span></span>

|           | <span data-ttu-id="2179f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2179f-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2179f-110">**name**</span><span class="sxs-lookup"><span data-stu-id="2179f-110">**name**</span></span>  | <span data-ttu-id="2179f-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2179f-111">Required attribute.</span></span><br><br><span data-ttu-id="2179f-112">Especifica el nombre del grupo de sección que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="2179f-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2179f-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="2179f-113">Parent element</span></span>

|     | <span data-ttu-id="2179f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2179f-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2179f-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="2179f-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="2179f-116">Contiene las declaraciones de espacio de nombres y la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="2179f-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2179f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2179f-117">Child elements</span></span>

|     | <span data-ttu-id="2179f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2179f-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2179f-119">**\<sección >**</span><span class="sxs-lookup"><span data-stu-id="2179f-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="2179f-120">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="2179f-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2179f-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2179f-121">Remarks</span></span>

<span data-ttu-id="2179f-122">Declarar un grupo de secciones crea una etiqueta de contenedor para las secciones de configuración y no garantiza que no habrá ningún conflicto de nomenclatura con secciones de configuración definidas por otra persona.</span><span class="sxs-lookup"><span data-stu-id="2179f-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="2179f-123">Puede anidar  **\<sectionGroup >** elementos dentro de otros.</span><span class="sxs-lookup"><span data-stu-id="2179f-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="2179f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2179f-124">Example</span></span>

<span data-ttu-id="2179f-125">En el ejemplo siguiente se muestra cómo declarar un grupo de secciones y declarar secciones dentro de un grupo de sección:</span><span class="sxs-lookup"><span data-stu-id="2179f-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2179f-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="2179f-126">Configuration file</span></span>

<span data-ttu-id="2179f-127">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2179f-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2179f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2179f-128">See also</span></span>

[<span data-ttu-id="2179f-129">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2179f-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
