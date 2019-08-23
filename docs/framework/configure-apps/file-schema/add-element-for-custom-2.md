---
title: <add>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ec6d5045580e887de5f05a05c8f39fa62c6e3f2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921329"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="dc715-102">\<Agregar > elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="dc715-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="dc715-103">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="dc715-103">Adds custom application settings.</span></span> <span data-ttu-id="dc715-104">Cada etiqueta Add > contiene un par clave-valor.  **\<**</span><span class="sxs-lookup"><span data-stu-id="dc715-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="dc715-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="dc715-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="dc715-106">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="dc715-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="dc715-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="dc715-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dc715-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc715-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="dc715-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc715-109">Attributes</span></span>

| <span data-ttu-id="dc715-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc715-110">Attribute</span></span> | <span data-ttu-id="dc715-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc715-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="dc715-112">**key**</span><span class="sxs-lookup"><span data-stu-id="dc715-112">**key**</span></span>   | <span data-ttu-id="dc715-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dc715-113">Required attribute.</span></span><br><br><span data-ttu-id="dc715-114">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="dc715-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="dc715-115">**value**</span><span class="sxs-lookup"><span data-stu-id="dc715-115">**value**</span></span> | <span data-ttu-id="dc715-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dc715-116">Required attribute.</span></span><br><br><span data-ttu-id="dc715-117">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="dc715-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="dc715-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="dc715-118">Parent element</span></span>

| <span data-ttu-id="dc715-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc715-119">Element</span></span> | <span data-ttu-id="dc715-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc715-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="dc715-121"> **sectionName>\<** elemento</span><span class="sxs-lookup"><span data-stu-id="dc715-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="dc715-122">Define la configuración de las secciones de configuración personalizadas <xref:System.Configuration.NameValueSectionHandler> que <xref:System.Configuration.DictionarySectionHandler> utilizan las clases y.</span><span class="sxs-lookup"><span data-stu-id="dc715-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="dc715-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc715-123">Child elements</span></span>

<span data-ttu-id="dc715-124">None</span><span class="sxs-lookup"><span data-stu-id="dc715-124">None</span></span>

## <a name="example"></a><span data-ttu-id="dc715-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc715-125">Example</span></span>

<span data-ttu-id="dc715-126">En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizada y usar el  **\<elemento Add >** para colocar la configuración en la sección:</span><span class="sxs-lookup"><span data-stu-id="dc715-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="dc715-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="dc715-127">Configuration file</span></span>

<span data-ttu-id="dc715-128">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc715-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc715-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc715-129">See also</span></span>

- [<span data-ttu-id="dc715-130">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc715-130">Configuration file schema for the .NET Framework</span></span>](index.md)
