---
title: <add>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215437"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="997f1-102">\<add>elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="997f1-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="997f1-103">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="997f1-103">Adds custom application settings.</span></span> <span data-ttu-id="997f1-104">Cada **\<add>** etiqueta contiene un par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="997f1-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="997f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="997f1-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="997f1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="997f1-106">Attributes</span></span>

| <span data-ttu-id="997f1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="997f1-107">Attribute</span></span> | <span data-ttu-id="997f1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="997f1-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="997f1-109">**key**</span><span class="sxs-lookup"><span data-stu-id="997f1-109">**key**</span></span>   | <span data-ttu-id="997f1-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="997f1-110">Required attribute.</span></span><br><br><span data-ttu-id="997f1-111">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="997f1-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="997f1-112">**value**</span><span class="sxs-lookup"><span data-stu-id="997f1-112">**value**</span></span> | <span data-ttu-id="997f1-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="997f1-113">Required attribute.</span></span><br><br><span data-ttu-id="997f1-114">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="997f1-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="997f1-115">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="997f1-115">Parent element</span></span>

| <span data-ttu-id="997f1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="997f1-116">Element</span></span> | <span data-ttu-id="997f1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="997f1-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="997f1-118">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="997f1-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="997f1-119">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="997f1-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="997f1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="997f1-120">Child elements</span></span>

<span data-ttu-id="997f1-121">None</span><span class="sxs-lookup"><span data-stu-id="997f1-121">None</span></span>

## <a name="example"></a><span data-ttu-id="997f1-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="997f1-122">Example</span></span>

<span data-ttu-id="997f1-123">En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizada y usar el **\<add>** elemento para colocar la configuración en la sección:</span><span class="sxs-lookup"><span data-stu-id="997f1-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="997f1-124">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="997f1-124">Configuration file</span></span>

<span data-ttu-id="997f1-125">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="997f1-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="997f1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="997f1-126">See also</span></span>

- [<span data-ttu-id="997f1-127">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="997f1-127">Configuration file schema for the .NET Framework</span></span>](index.md)
