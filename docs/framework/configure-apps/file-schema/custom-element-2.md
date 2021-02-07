---
description: 'Más información sobre: elemento personalizado para NameValueSectionHandler y DictionarySectionHandler'
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: c1bb5b2fb321e2cc9235e02be2158c0875d42032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698731"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="7a1d3-103">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="7a1d3-103">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="7a1d3-104">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-104">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="7a1d3-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a1d3-105">Attributes</span></span>

<span data-ttu-id="7a1d3-106">None</span><span class="sxs-lookup"><span data-stu-id="7a1d3-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7a1d3-107">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="7a1d3-107">Parent element</span></span>

|     | <span data-ttu-id="7a1d3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a1d3-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="7a1d3-109">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7a1d3-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a1d3-110">Child elements</span></span>

|     | <span data-ttu-id="7a1d3-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a1d3-111">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="7a1d3-112">[**\<add>**](add-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="7a1d3-112">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="7a1d3-113">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-113">Adds custom application settings.</span></span> |
| <span data-ttu-id="7a1d3-114">[**\<remove>**](remove-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="7a1d3-114">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="7a1d3-115">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-115">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="7a1d3-116">[**\<clear>**](clear-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="7a1d3-116">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="7a1d3-117">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-117">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7a1d3-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a1d3-118">Remarks</span></span>

<span data-ttu-id="7a1d3-119">El **\<sectionName>** elemento es un elemento personalizado definido por una **\<section>** etiqueta en el **\<configSections>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-119">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="7a1d3-120">En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="7a1d3-120">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="7a1d3-121">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="7a1d3-121">Configuration section handler</span></span>                        | <span data-ttu-id="7a1d3-122">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7a1d3-122">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="7a1d3-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a1d3-123">Example</span></span>

<span data-ttu-id="7a1d3-124">En el ejemplo siguiente se muestra cómo declarar secciones que utilizan <xref:System.Configuration.DictionarySectionHandler> las <xref:System.Configuration.NameValueSectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-124">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="7a1d3-125">El primer elemento personalizado es **\<dictionarySample>** , que contiene la configuración leída por la <xref:System.Configuration.DictionarySectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-125">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="7a1d3-126">El segundo elemento personalizado es **\<mySection>** , que contiene la configuración leída por la <xref:System.Configuration.NameValueSectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-126">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7a1d3-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7a1d3-127">Configuration file</span></span>

<span data-ttu-id="7a1d3-128">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a1d3-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a1d3-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a1d3-129">See also</span></span>

- [<span data-ttu-id="7a1d3-130">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a1d3-130">Configuration file schema for the .NET Framework</span></span>](index.md)
