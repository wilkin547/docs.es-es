---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 07bc0d9560546f4946d34413697fb0adcf84c58d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743282"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="d3d86-102">Elemento personalizado para SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="d3d86-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="d3d86-103">Define la configuración en una sección de configuración personalizada que se define mediante una</span><span class="sxs-lookup"><span data-stu-id="d3d86-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="d3d86-104">elemento y se utiliza la <xref:System.Configuration.SingleTagSectionHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="d3d86-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="d3d86-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d3d86-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d3d86-106">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="d3d86-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="d3d86-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3d86-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="d3d86-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3d86-108">Attributes</span></span>

<span data-ttu-id="d3d86-109">Atributos y valores de atributo son definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d3d86-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="d3d86-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="d3d86-110">Parent element</span></span>

|     | <span data-ttu-id="d3d86-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3d86-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d3d86-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="d3d86-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="d3d86-113">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3d86-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d3d86-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3d86-114">Child elements</span></span>

<span data-ttu-id="d3d86-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d3d86-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d3d86-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3d86-116">Remarks</span></span>

<span data-ttu-id="d3d86-117">El  **\<sectionName >** trata de un elemento personalizado definido por una [  **\<sección >** ](~/docs/framework/configure-apps/file-schema/section-element.md) etiqueta en el [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d3d86-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="d3d86-118">El sistema de configuración devuelve un <xref:System.Collections.IDictionary> objeto cuando se llama a <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3d86-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="d3d86-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3d86-119">Example</span></span>

<span data-ttu-id="d3d86-120">En el ejemplo siguiente se declara un elemento personalizado denominado  **\<sampleSection >** que contiene los valores leídos por el <xref:System.Configuration.SingleTagSectionHandler> clase:</span><span class="sxs-lookup"><span data-stu-id="d3d86-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d3d86-121">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d3d86-121">Configuration file</span></span>

<span data-ttu-id="d3d86-122">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3d86-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3d86-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3d86-123">See also</span></span>

[<span data-ttu-id="d3d86-124">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d3d86-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
