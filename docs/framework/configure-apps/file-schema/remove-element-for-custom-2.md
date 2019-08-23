---
title: <remove>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920948"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ef3ad-102">\<quitar > elemento de NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="ef3ad-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ef3ad-103">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="ef3ad-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ef3ad-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="ef3ad-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="ef3ad-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="ef3ad-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="ef3ad-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ef3ad-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef3ad-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="ef3ad-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef3ad-108">Attribute</span></span>

|           | <span data-ttu-id="ef3ad-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef3ad-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ef3ad-110">**key**</span><span class="sxs-lookup"><span data-stu-id="ef3ad-110">**key**</span></span>   | <span data-ttu-id="ef3ad-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-111">Required attribute.</span></span><br><br><span data-ttu-id="ef3ad-112">Especifica el nombre de la configuración que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ef3ad-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="ef3ad-113">Parent element</span></span>

| <span data-ttu-id="ef3ad-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef3ad-114">Element</span></span> | <span data-ttu-id="ef3ad-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef3ad-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="ef3ad-116"> **sectionName>\<** elemento</span><span class="sxs-lookup"><span data-stu-id="ef3ad-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="ef3ad-117">Define la configuración de las secciones de configuración personalizadas <xref:System.Configuration.NameValueSectionHandler> que <xref:System.Configuration.DictionarySectionHandler> utilizan las clases y.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ef3ad-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef3ad-118">Child elements</span></span>

<span data-ttu-id="ef3ad-119">None</span><span class="sxs-lookup"><span data-stu-id="ef3ad-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ef3ad-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef3ad-120">Remarks</span></span>

<span data-ttu-id="ef3ad-121">Puede usar el  **\<elemento Remove >** para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ef3ad-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef3ad-122">Example</span></span>

<span data-ttu-id="ef3ad-123">En el ejemplo siguiente se muestra cómo usar el elemento  **\<Remove >** en un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ef3ad-124">El siguiente código de archivo de configuración de máquina declara  **\<** la sección de la sección > y le `key1` agrega `key2`dos valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="ef3ad-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="ef3ad-125">El siguiente código de archivo de configuración de `key2` la aplicación quita la configuración de  **\<la sección >** :</span><span class="sxs-lookup"><span data-stu-id="ef3ad-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ef3ad-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ef3ad-126">Configuration file</span></span>

<span data-ttu-id="ef3ad-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef3ad-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef3ad-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef3ad-128">See also</span></span>

- [<span data-ttu-id="ef3ad-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ef3ad-129">Configuration file schema for the .NET Framework</span></span>](index.md)
