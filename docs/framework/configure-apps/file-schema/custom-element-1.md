---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 0d765a9789ad566428b1fbda6c0863b10b98c363
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345075"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="c36b6-102">Elemento personalizado para SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="c36b6-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="c36b6-103">Define la configuración en una sección \<de configuración personalizada <xref:System.Configuration.SingleTagSectionHandler> definida por una sección> elemento y utiliza la clase.</span><span class="sxs-lookup"><span data-stu-id="c36b6-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="c36b6-104">sección &nbsp; &nbsp;de configuración [\*\* \<>Nombre\*\*](configuration-element.md) \* \<>\*</span><span class="sxs-lookup"><span data-stu-id="c36b6-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="c36b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c36b6-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="c36b6-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c36b6-106">Attributes</span></span>

<span data-ttu-id="c36b6-107">Los atributos y los valores de atributo están definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c36b6-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="c36b6-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="c36b6-108">Parent element</span></span>

|     | <span data-ttu-id="c36b6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c36b6-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c36b6-110">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="c36b6-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="c36b6-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c36b6-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c36b6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c36b6-112">Child elements</span></span>

<span data-ttu-id="c36b6-113">None</span><span class="sxs-lookup"><span data-stu-id="c36b6-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c36b6-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c36b6-114">Remarks</span></span>

<span data-ttu-id="c36b6-115">El \*\* \<\*\* elemento de>sectionName es [\*\* \<\*\*](section-element.md) un elemento personalizado definido por una etiqueta de>de sección en el [\*\* \<elemento>configSections.\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c36b6-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="c36b6-116">El sistema de <xref:System.Collections.IDictionary> configuración devuelve <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>un objeto cuando se llama a .</span><span class="sxs-lookup"><span data-stu-id="c36b6-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="c36b6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c36b6-117">Example</span></span>

<span data-ttu-id="c36b6-118">En el ejemplo siguiente se declara un elemento personalizado <xref:System.Configuration.SingleTagSectionHandler> denominado \*\* \<sampleSection>\*\* que contiene la configuración leída por la clase:</span><span class="sxs-lookup"><span data-stu-id="c36b6-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="c36b6-119">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c36b6-119">Configuration file</span></span>

<span data-ttu-id="c36b6-120">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c36b6-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c36b6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c36b6-121">See also</span></span>

- [<span data-ttu-id="c36b6-122">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c36b6-122">Configuration file schema for the .NET Framework</span></span>](index.md)
