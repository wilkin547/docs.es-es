---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 1d0431085a04d3fb817dfe0883779acc4d693084
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214789"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="aa73b-102">Elemento personalizado para SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="aa73b-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="aa73b-103">Define la configuración de una sección de configuración personalizada que se define mediante una \<sección > elemento y utiliza la clase <xref:System.Configuration.SingleTagSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="aa73b-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="aa73b-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="aa73b-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="aa73b-105">&nbsp;&nbsp; *\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="aa73b-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="aa73b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa73b-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="aa73b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa73b-107">Attributes</span></span>

<span data-ttu-id="aa73b-108">Los atributos y los valores de atributo son definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aa73b-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="aa73b-109">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="aa73b-109">Parent element</span></span>

|     | <span data-ttu-id="aa73b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa73b-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="aa73b-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="aa73b-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="aa73b-112">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa73b-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="aa73b-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa73b-113">Child elements</span></span>

<span data-ttu-id="aa73b-114">None</span><span class="sxs-lookup"><span data-stu-id="aa73b-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="aa73b-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aa73b-115">Remarks</span></span>

<span data-ttu-id="aa73b-116">El elemento **\<sectionName >** es un elemento personalizado definido por una [**sección de\<>** ](section-element.md) etiqueta del elemento\<[**configSections >** ](configsections-element-for-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="aa73b-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="aa73b-117">El sistema de configuración devuelve un objeto <xref:System.Collections.IDictionary> cuando se llama a <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa73b-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="aa73b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa73b-118">Example</span></span>

<span data-ttu-id="aa73b-119">En el ejemplo siguiente se declara un elemento personalizado denominado **\<> sampleSection** que contiene la configuración leída por la clase <xref:System.Configuration.SingleTagSectionHandler>:</span><span class="sxs-lookup"><span data-stu-id="aa73b-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="aa73b-120">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="aa73b-120">Configuration file</span></span>

<span data-ttu-id="aa73b-121">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa73b-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa73b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa73b-122">See also</span></span>

- [<span data-ttu-id="aa73b-123">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa73b-123">Configuration file schema for the .NET Framework</span></span>](index.md)
