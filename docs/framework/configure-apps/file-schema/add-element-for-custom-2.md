---
title: elemento <add> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e7d68530ae1f0666fc4940ffe7605c3bf8dfe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119609"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="642b1-102">\<agregar > elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="642b1-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="642b1-103">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="642b1-103">Adds custom application settings.</span></span> <span data-ttu-id="642b1-104">Cada **\<agregar >** etiqueta contiene un par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="642b1-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="642b1-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="642b1-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="642b1-106">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="642b1-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="642b1-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<agregar >**</span><span class="sxs-lookup"><span data-stu-id="642b1-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="642b1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="642b1-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="642b1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="642b1-109">Attributes</span></span>

| <span data-ttu-id="642b1-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="642b1-110">Attribute</span></span> | <span data-ttu-id="642b1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="642b1-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="642b1-112">**key**</span><span class="sxs-lookup"><span data-stu-id="642b1-112">**key**</span></span>   | <span data-ttu-id="642b1-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="642b1-113">Required attribute.</span></span><br><br><span data-ttu-id="642b1-114">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="642b1-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="642b1-115">**valor**</span><span class="sxs-lookup"><span data-stu-id="642b1-115">**value**</span></span> | <span data-ttu-id="642b1-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="642b1-116">Required attribute.</span></span><br><br><span data-ttu-id="642b1-117">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="642b1-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="642b1-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="642b1-118">Parent element</span></span>

| <span data-ttu-id="642b1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="642b1-119">Element</span></span> | <span data-ttu-id="642b1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="642b1-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="642b1-121"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="642b1-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="642b1-122">Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="642b1-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="642b1-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="642b1-123">Child elements</span></span>

<span data-ttu-id="642b1-124">Ninguno</span><span class="sxs-lookup"><span data-stu-id="642b1-124">None</span></span>

## <a name="example"></a><span data-ttu-id="642b1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="642b1-125">Example</span></span>

<span data-ttu-id="642b1-126">En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizada y usar el elemento **\<agregar >** para colocar la configuración en la sección:</span><span class="sxs-lookup"><span data-stu-id="642b1-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="642b1-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="642b1-127">Configuration file</span></span>

<span data-ttu-id="642b1-128">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="642b1-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="642b1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="642b1-129">See also</span></span>

- [<span data-ttu-id="642b1-130">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="642b1-130">Configuration file schema for the .NET Framework</span></span>](index.md)
