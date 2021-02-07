---
description: 'Más información sobre: elemento personalizado para SingleTagSectionHandler'
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 83022a1ebf295b89d5f868589e3d9a77c78e3fab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729984"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="e5ebe-103">Elemento personalizado para SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="e5ebe-103">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="e5ebe-104">Define la configuración en una sección de configuración personalizada que está definida por un \<section> elemento y utiliza la <xref:System.Configuration.SingleTagSectionHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="e5ebe-104">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="e5ebe-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="e5ebe-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="e5ebe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5ebe-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="e5ebe-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5ebe-107">Attributes</span></span>

<span data-ttu-id="e5ebe-108">Los atributos y los valores de atributo son definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e5ebe-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="e5ebe-109">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="e5ebe-109">Parent element</span></span>

|     | <span data-ttu-id="e5ebe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5ebe-110">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="e5ebe-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5ebe-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e5ebe-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5ebe-112">Child elements</span></span>

<span data-ttu-id="e5ebe-113">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e5ebe-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e5ebe-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5ebe-114">Remarks</span></span>

<span data-ttu-id="e5ebe-115">El **\<sectionName>** elemento es un elemento personalizado definido por una [**\<section>**](section-element.md) etiqueta en el [**\<configSections>**](configsections-element-for-configuration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e5ebe-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="e5ebe-116">El sistema de configuración devuelve un <xref:System.Collections.IDictionary> objeto cuando se llama a <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e5ebe-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="e5ebe-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5ebe-117">Example</span></span>

<span data-ttu-id="e5ebe-118">En el ejemplo siguiente se declara un elemento personalizado denominado **\<sampleSection>** que contiene los valores leídos por la <xref:System.Configuration.SingleTagSectionHandler> clase:</span><span class="sxs-lookup"><span data-stu-id="e5ebe-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="e5ebe-119">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e5ebe-119">Configuration file</span></span>

<span data-ttu-id="e5ebe-120">Este elemento se puede usar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5ebe-120">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ebe-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ebe-121">See also</span></span>

- [<span data-ttu-id="e5ebe-122">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e5ebe-122">Configuration file schema for the .NET Framework</span></span>](index.md)
