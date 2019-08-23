---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921041"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="8f5ff-102">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="8f5ff-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="8f5ff-103">Define la configuración de las secciones de configuración personalizadas <xref:System.Configuration.NameValueSectionHandler> que <xref:System.Configuration.DictionarySectionHandler> utilizan las clases y.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="8f5ff-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f5ff-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8f5ff-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="8f5ff-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="8f5ff-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8f5ff-106">Attributes</span></span>

<span data-ttu-id="8f5ff-107">None</span><span class="sxs-lookup"><span data-stu-id="8f5ff-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="8f5ff-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="8f5ff-108">Parent element</span></span>

|     | <span data-ttu-id="8f5ff-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8f5ff-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f5ff-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="8f5ff-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="8f5ff-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8f5ff-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8f5ff-112">Child elements</span></span>

|     | <span data-ttu-id="8f5ff-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8f5ff-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="8f5ff-114">Agregue > para y [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8f5ff-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="8f5ff-115">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="8f5ff-116">quitar > para y [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8f5ff-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="8f5ff-117">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="8f5ff-118">borrar > para y [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8f5ff-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="8f5ff-119">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8f5ff-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f5ff-120">Remarks</span></span>

<span data-ttu-id="8f5ff-121">**El\<elemento sectionName >** es un elemento personalizado definido por una  **\<sección >** etiqueta en el  **\<elemento > configSections** .</span><span class="sxs-lookup"><span data-stu-id="8f5ff-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="8f5ff-122">En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="8f5ff-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="8f5ff-123">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="8f5ff-123">Configuration section handler</span></span>                        | <span data-ttu-id="8f5ff-124">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="8f5ff-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="8f5ff-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f5ff-125">Example</span></span>

<span data-ttu-id="8f5ff-126">En el ejemplo siguiente se muestra cómo declarar secciones que utilizan <xref:System.Configuration.DictionarySectionHandler> las <xref:System.Configuration.NameValueSectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="8f5ff-127">El primer elemento personalizado es  **\<dictionarySample >** , que contiene la configuración leída por <xref:System.Configuration.DictionarySectionHandler> la clase en `System.dll` el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="8f5ff-128">El segundo elemento personalizado es  **\<la sección >** , que contiene la configuración leída por <xref:System.Configuration.NameValueSectionHandler> la clase en `System.dll` el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="8f5ff-129">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8f5ff-129">Configuration file</span></span>

<span data-ttu-id="8f5ff-130">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f5ff-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f5ff-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f5ff-131">See also</span></span>

- [<span data-ttu-id="8f5ff-132">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f5ff-132">Configuration file schema for the .NET Framework</span></span>](index.md)
