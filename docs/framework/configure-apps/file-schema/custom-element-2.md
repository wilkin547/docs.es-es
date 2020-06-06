---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215475"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="93eb9-102">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="93eb9-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="93eb9-103">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="93eb9-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="93eb9-104">Atributos</span><span class="sxs-lookup"><span data-stu-id="93eb9-104">Attributes</span></span>

<span data-ttu-id="93eb9-105">None</span><span class="sxs-lookup"><span data-stu-id="93eb9-105">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="93eb9-106">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="93eb9-106">Parent element</span></span>

|     | <span data-ttu-id="93eb9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="93eb9-107">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="93eb9-108">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93eb9-108">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="93eb9-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93eb9-109">Child elements</span></span>

|     | <span data-ttu-id="93eb9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="93eb9-110">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="93eb9-111">[**\<add>**](add-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="93eb9-111">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="93eb9-112">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="93eb9-112">Adds custom application settings.</span></span> |
| <span data-ttu-id="93eb9-113">[**\<remove>**](remove-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="93eb9-113">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="93eb9-114">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="93eb9-114">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="93eb9-115">[**\<clear>**](clear-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="93eb9-115">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="93eb9-116">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="93eb9-116">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="93eb9-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93eb9-117">Remarks</span></span>

<span data-ttu-id="93eb9-118">El **\<sectionName>** elemento es un elemento personalizado definido por una **\<section>** etiqueta en el **\<configSections>** elemento.</span><span class="sxs-lookup"><span data-stu-id="93eb9-118">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="93eb9-119">En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="93eb9-119">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="93eb9-120">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="93eb9-120">Configuration section handler</span></span>                        | <span data-ttu-id="93eb9-121">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93eb9-121">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="93eb9-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93eb9-122">Example</span></span>

<span data-ttu-id="93eb9-123">En el ejemplo siguiente se muestra cómo declarar secciones que utilizan <xref:System.Configuration.DictionarySectionHandler> las <xref:System.Configuration.NameValueSectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="93eb9-123">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="93eb9-124">El primer elemento personalizado es **\<dictionarySample>** , que contiene la configuración leída por la <xref:System.Configuration.DictionarySectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93eb9-124">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="93eb9-125">El segundo elemento personalizado es **\<mySection>** , que contiene la configuración leída por la <xref:System.Configuration.NameValueSectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="93eb9-125">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="93eb9-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="93eb9-126">Configuration file</span></span>

<span data-ttu-id="93eb9-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93eb9-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="93eb9-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93eb9-128">See also</span></span>

- [<span data-ttu-id="93eb9-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93eb9-129">Configuration file schema for the .NET Framework</span></span>](index.md)
