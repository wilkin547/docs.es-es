---
description: 'Más información sobre: <add> elemento para NameValueSectionHandler y DictionarySectionHandler'
title: <add> elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 5a8cf22b21370e60086408f792f8137386d07aa3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713057"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="a9b54-103">\<add> elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="a9b54-103">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="a9b54-104">Agrega la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9b54-104">Adds custom application settings.</span></span> <span data-ttu-id="a9b54-105">Cada **\<add>** etiqueta contiene un par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="a9b54-105">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="a9b54-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9b54-106">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="a9b54-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9b54-107">Attributes</span></span>

| <span data-ttu-id="a9b54-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="a9b54-108">Attribute</span></span> | <span data-ttu-id="a9b54-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b54-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a9b54-110">**key**</span><span class="sxs-lookup"><span data-stu-id="a9b54-110">**key**</span></span>   | <span data-ttu-id="a9b54-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a9b54-111">Required attribute.</span></span><br><br><span data-ttu-id="a9b54-112">Especifica el nombre de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9b54-112">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="a9b54-113">**value**</span><span class="sxs-lookup"><span data-stu-id="a9b54-113">**value**</span></span> | <span data-ttu-id="a9b54-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a9b54-114">Required attribute.</span></span><br><br><span data-ttu-id="a9b54-115">Especifica el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9b54-115">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a9b54-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a9b54-116">Parent element</span></span>

| <span data-ttu-id="a9b54-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9b54-117">Element</span></span> | <span data-ttu-id="a9b54-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b54-118">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="a9b54-119">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="a9b54-119">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="a9b54-120">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="a9b54-120">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a9b54-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9b54-121">Child elements</span></span>

<span data-ttu-id="a9b54-122">None</span><span class="sxs-lookup"><span data-stu-id="a9b54-122">None</span></span>

## <a name="example"></a><span data-ttu-id="a9b54-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9b54-123">Example</span></span>

<span data-ttu-id="a9b54-124">En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizada y usar el **\<add>** elemento para colocar la configuración en la sección:</span><span class="sxs-lookup"><span data-stu-id="a9b54-124">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="a9b54-125">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a9b54-125">Configuration file</span></span>

<span data-ttu-id="a9b54-126">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9b54-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9b54-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9b54-127">See also</span></span>

- [<span data-ttu-id="a9b54-128">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9b54-128">Configuration file schema for the .NET Framework</span></span>](index.md)
