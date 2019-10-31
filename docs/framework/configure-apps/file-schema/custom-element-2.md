---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73c07d58bb226346cb99a1fe50b12bb0e7e746e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118541"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ed01e-102">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="ed01e-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ed01e-103">Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="ed01e-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="ed01e-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed01e-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="ed01e-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="ed01e-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="ed01e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed01e-106">Attributes</span></span>

<span data-ttu-id="ed01e-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ed01e-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ed01e-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="ed01e-108">Parent element</span></span>

|     | <span data-ttu-id="ed01e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed01e-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ed01e-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ed01e-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="ed01e-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ed01e-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ed01e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed01e-112">Child elements</span></span>

|     | <span data-ttu-id="ed01e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed01e-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="ed01e-114">[ **\<agregar >** ](add-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ed01e-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="ed01e-115">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed01e-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="ed01e-116">[ **\<quitar >** ](remove-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ed01e-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ed01e-117">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="ed01e-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="ed01e-118">[ **\<borrar >** ](clear-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ed01e-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ed01e-119">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="ed01e-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ed01e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed01e-120">Remarks</span></span>

<span data-ttu-id="ed01e-121">El elemento **\<sectionName >** es un elemento personalizado definido por una **sección de\<** etiqueta del elemento\<**configSections >** .</span><span class="sxs-lookup"><span data-stu-id="ed01e-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="ed01e-122">En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="ed01e-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="ed01e-123">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="ed01e-123">Configuration section handler</span></span>                        | <span data-ttu-id="ed01e-124">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="ed01e-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="ed01e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed01e-125">Example</span></span>

<span data-ttu-id="ed01e-126">En el ejemplo siguiente se muestra cómo declarar secciones que usan las clases <xref:System.Configuration.DictionarySectionHandler> y <xref:System.Configuration.NameValueSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="ed01e-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="ed01e-127">El primer elemento personalizado es **\<dictionarySample >** , que contiene los valores leídos por la clase <xref:System.Configuration.DictionarySectionHandler> en el ensamblado de `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="ed01e-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="ed01e-128">El segundo elemento personalizado es **\<mi sección >** , que contiene los valores leídos por la clase <xref:System.Configuration.NameValueSectionHandler> en el ensamblado de `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="ed01e-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ed01e-129">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ed01e-129">Configuration file</span></span>

<span data-ttu-id="ed01e-130">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed01e-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed01e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed01e-131">See also</span></span>

- [<span data-ttu-id="ed01e-132">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed01e-132">Configuration file schema for the .NET Framework</span></span>](index.md)
