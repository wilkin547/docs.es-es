---
title: '&lt;quitar&gt; elemento para NameValueSectionHandler y DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742918"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b695f-102">\<Quitar > (elemento) para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="b695f-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b695f-103">Quita un valor definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b695f-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="b695f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b695f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b695f-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="b695f-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="b695f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Quitar >**</span><span class="sxs-lookup"><span data-stu-id="b695f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b695f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b695f-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="b695f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b695f-108">Attribute</span></span>

|           | <span data-ttu-id="b695f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b695f-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b695f-110">**key**</span><span class="sxs-lookup"><span data-stu-id="b695f-110">**key**</span></span>   | <span data-ttu-id="b695f-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b695f-111">Required attribute.</span></span><br><br><span data-ttu-id="b695f-112">Especifica el nombre de la configuración para quitar.</span><span class="sxs-lookup"><span data-stu-id="b695f-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b695f-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="b695f-113">Parent element</span></span>

| <span data-ttu-id="b695f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b695f-114">Element</span></span> | <span data-ttu-id="b695f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b695f-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="b695f-116">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="b695f-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="b695f-117">Define los valores de las secciones de configuración personalizada que utilizan el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="b695f-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b695f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b695f-118">Child elements</span></span>

<span data-ttu-id="b695f-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b695f-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b695f-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b695f-120">Remarks</span></span>

<span data-ttu-id="b695f-121">Puede usar el  **\<quitar >** elemento que se va a quitar la configuración de la aplicación que se han definido en un nivel superior en la jerarquía de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="b695f-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="b695f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b695f-122">Example</span></span>

<span data-ttu-id="b695f-123">En el ejemplo siguiente se muestra cómo utilizar el  **\<quitar >** elemento en un archivo de configuración de aplicación para quitar los valores definidos anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="b695f-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="b695f-124">El siguiente código de archivo de configuración del equipo declara la sección  **\<mySection >** y agrega dos configuraciones, `key1` y `key2`, a él:</span><span class="sxs-lookup"><span data-stu-id="b695f-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="b695f-125">El siguiente código de archivo de configuración de la aplicación quita el `key2` de  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="b695f-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b695f-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b695f-126">Configuration file</span></span>

<span data-ttu-id="b695f-127">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b695f-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b695f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b695f-128">See also</span></span>

[<span data-ttu-id="b695f-129">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b695f-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
