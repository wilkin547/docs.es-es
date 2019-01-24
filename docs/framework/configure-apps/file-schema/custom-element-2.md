---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 74496726aa2fe5c88a273a22f096c585aa54de0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693803"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="8480c-102">Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="8480c-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="8480c-103">Define los valores de las secciones de configuración personalizada que utilicen el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="8480c-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="8480c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8480c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8480c-105">&nbsp;&nbsp;**\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="8480c-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="8480c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8480c-106">Attributes</span></span>

<span data-ttu-id="8480c-107">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8480c-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="8480c-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="8480c-108">Parent element</span></span>

|     | <span data-ttu-id="8480c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8480c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8480c-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="8480c-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="8480c-111">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8480c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8480c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8480c-112">Child elements</span></span>

|     | <span data-ttu-id="8480c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8480c-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="8480c-114">[**\<Agregar >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8480c-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="8480c-115">Agrega la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="8480c-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="8480c-116">[**\<Quitar >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8480c-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="8480c-117">Quita un valor definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8480c-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="8480c-118">[**\<Borrar >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="8480c-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="8480c-119">Borra todos los valores definidos anteriormente en una sección.</span><span class="sxs-lookup"><span data-stu-id="8480c-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8480c-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8480c-120">Remarks</span></span>

<span data-ttu-id="8480c-121">El  **\<sectionName >** trata de un elemento personalizado definido por una  **\<sección >** etiquetar en el  **\<configSections >** elemento.</span><span class="sxs-lookup"><span data-stu-id="8480c-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="8480c-122">En la tabla siguiente se muestra que el tipo de objeto al método ConfigurationSettings.GetConfig devuelve para cada controlador de la sección de configuración:</span><span class="sxs-lookup"><span data-stu-id="8480c-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="8480c-123">Controlador de la sección de configuración</span><span class="sxs-lookup"><span data-stu-id="8480c-123">Configuration section handler</span></span>                        | <span data-ttu-id="8480c-124">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="8480c-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="8480c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8480c-125">Example</span></span>

<span data-ttu-id="8480c-126">El ejemplo siguiente muestra cómo declarar las secciones que utilizan el <xref:System.Configuration.DictionarySectionHandler> y <xref:System.Configuration.NameValueSectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="8480c-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="8480c-127">El primer elemento personalizado es  **\<dictionarySample >**, que contiene los valores leídos por la <xref:System.Configuration.DictionarySectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8480c-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="8480c-128">El segundo elemento personalizado es  **\<mySection >**, que contiene los valores leídos por la <xref:System.Configuration.NameValueSectionHandler> clase en el `System.dll` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8480c-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="8480c-129">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8480c-129">Configuration file</span></span>

<span data-ttu-id="8480c-130">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8480c-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8480c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8480c-131">See also</span></span>

- [<span data-ttu-id="8480c-132">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8480c-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
