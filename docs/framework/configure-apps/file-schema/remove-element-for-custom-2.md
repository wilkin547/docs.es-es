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
ms.openlocfilehash: ece76f06f5ecbf47302b62a5e546cc13298106bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535585"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ff045-102">\<Quitar > elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="ff045-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ff045-103">Quita un valor definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ff045-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="ff045-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ff045-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ff045-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="ff045-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="ff045-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="ff045-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ff045-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff045-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="ff045-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff045-108">Attribute</span></span>

|           | <span data-ttu-id="ff045-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff045-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ff045-110">**key**</span><span class="sxs-lookup"><span data-stu-id="ff045-110">**key**</span></span>   | <span data-ttu-id="ff045-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ff045-111">Required attribute.</span></span><br><br><span data-ttu-id="ff045-112">Especifica el nombre de la configuración para quitar.</span><span class="sxs-lookup"><span data-stu-id="ff045-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ff045-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="ff045-113">Parent element</span></span>

| <span data-ttu-id="ff045-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff045-114">Element</span></span> | <span data-ttu-id="ff045-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff045-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="ff045-116">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="ff045-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="ff045-117">Define los valores de las secciones de configuración personalizada que utilicen el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="ff045-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ff045-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff045-118">Child elements</span></span>

<span data-ttu-id="ff045-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ff045-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ff045-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff045-120">Remarks</span></span>

<span data-ttu-id="ff045-121">Puede usar el  **\<quitar >** elemento para quitar la configuración de la aplicación que se han definido en un nivel superior de la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff045-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ff045-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff045-122">Example</span></span>

<span data-ttu-id="ff045-123">El ejemplo siguiente muestra cómo usar el  **\<quitar >** elemento en un archivo de configuración de aplicación para quitar los valores definidos anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="ff045-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ff045-124">El siguiente código de archivo de configuración del equipo declara la sección  **\<mySection >** y agrega dos configuraciones, `key1` y `key2`, a él:</span><span class="sxs-lookup"><span data-stu-id="ff045-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="ff045-125">El siguiente código de archivo de configuración de la aplicación se quita la `key2` de  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="ff045-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ff045-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ff045-126">Configuration file</span></span>

<span data-ttu-id="ff045-127">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff045-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff045-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff045-128">See also</span></span>

- [<span data-ttu-id="ff045-129">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ff045-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
