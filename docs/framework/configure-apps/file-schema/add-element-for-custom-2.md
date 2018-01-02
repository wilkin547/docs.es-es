---
title: '&lt;agregar&gt; elemento para NameValueSectionHandler y DictionarySectionHandler'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e29d0007820bb0218338394fe199e7acfd66344e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="0eb42-102">\<Agregar > (elemento) para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="0eb42-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="0eb42-103">Agrega la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="0eb42-103">Adds custom application settings.</span></span> <span data-ttu-id="0eb42-104">Cada  **\<Agregar >** etiqueta contiene un par de clave/valor.</span><span class="sxs-lookup"><span data-stu-id="0eb42-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="0eb42-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0eb42-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0eb42-106">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="0eb42-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="0eb42-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="0eb42-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0eb42-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eb42-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="0eb42-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0eb42-109">Attributes</span></span>

| <span data-ttu-id="0eb42-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="0eb42-110">Attribute</span></span> | <span data-ttu-id="0eb42-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eb42-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0eb42-112">**key**</span><span class="sxs-lookup"><span data-stu-id="0eb42-112">**key**</span></span>   | <span data-ttu-id="0eb42-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0eb42-113">Required attribute.</span></span><br><br><span data-ttu-id="0eb42-114">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0eb42-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="0eb42-115">**value**</span><span class="sxs-lookup"><span data-stu-id="0eb42-115">**value**</span></span> | <span data-ttu-id="0eb42-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0eb42-116">Required attribute.</span></span><br><br><span data-ttu-id="0eb42-117">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0eb42-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0eb42-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="0eb42-118">Parent element</span></span>

| <span data-ttu-id="0eb42-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0eb42-119">Element</span></span> | <span data-ttu-id="0eb42-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eb42-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="0eb42-121">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="0eb42-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="0eb42-122">Define los valores de las secciones de configuración personalizada que utilizan el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="0eb42-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0eb42-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0eb42-123">Child elements</span></span>

<span data-ttu-id="0eb42-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="0eb42-124">None</span></span>

## <a name="example"></a><span data-ttu-id="0eb42-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eb42-125">Example</span></span>

<span data-ttu-id="0eb42-126">En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizado y utilice la  **\<Agregar >** elemento que se va a colocar los valores en la sección:</span><span class="sxs-lookup"><span data-stu-id="0eb42-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0eb42-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0eb42-127">Configuration file</span></span>

<span data-ttu-id="0eb42-128">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0eb42-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb42-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eb42-129">See also</span></span>

[<span data-ttu-id="0eb42-130">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0eb42-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
