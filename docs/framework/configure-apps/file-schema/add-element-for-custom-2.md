---
title: <add> elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9b421b4bab32c1aae7a6ba7d69b9f4aea2ab99a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705498"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b89f6-102">\<Agregar > elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="b89f6-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b89f6-103">Agrega la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="b89f6-103">Adds custom application settings.</span></span> <span data-ttu-id="b89f6-104">Cada  **\<Agregar >** etiqueta contiene un par clave/valor.</span><span class="sxs-lookup"><span data-stu-id="b89f6-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="b89f6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b89f6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b89f6-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="b89f6-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="b89f6-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span><span class="sxs-lookup"><span data-stu-id="b89f6-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b89f6-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b89f6-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="b89f6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b89f6-109">Attributes</span></span>

| <span data-ttu-id="b89f6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="b89f6-110">Attribute</span></span> | <span data-ttu-id="b89f6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b89f6-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b89f6-112">**key**</span><span class="sxs-lookup"><span data-stu-id="b89f6-112">**key**</span></span>   | <span data-ttu-id="b89f6-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b89f6-113">Required attribute.</span></span><br><br><span data-ttu-id="b89f6-114">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b89f6-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="b89f6-115">**value**</span><span class="sxs-lookup"><span data-stu-id="b89f6-115">**value**</span></span> | <span data-ttu-id="b89f6-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b89f6-116">Required attribute.</span></span><br><br><span data-ttu-id="b89f6-117">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b89f6-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b89f6-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="b89f6-118">Parent element</span></span>

| <span data-ttu-id="b89f6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b89f6-119">Element</span></span> | <span data-ttu-id="b89f6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b89f6-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="b89f6-121">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="b89f6-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="b89f6-122">Define los valores de las secciones de configuración personalizada que utilicen el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="b89f6-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b89f6-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b89f6-123">Child elements</span></span>

<span data-ttu-id="b89f6-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b89f6-124">None</span></span>

## <a name="example"></a><span data-ttu-id="b89f6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b89f6-125">Example</span></span>

<span data-ttu-id="b89f6-126">El ejemplo siguiente muestra cómo definir una sección de configuración personalizado y usar el  **\<Agregar >** elemento para que la configuración en la sección:</span><span class="sxs-lookup"><span data-stu-id="b89f6-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="b89f6-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b89f6-127">Configuration file</span></span>

<span data-ttu-id="b89f6-128">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b89f6-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b89f6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b89f6-129">See also</span></span>

- [<span data-ttu-id="b89f6-130">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b89f6-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
