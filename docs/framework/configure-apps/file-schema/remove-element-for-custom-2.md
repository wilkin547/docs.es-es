---
description: 'Más información sobre: <remove> elemento para NameValueSectionHandler y DictionarySectionHandler'
title: <remove> elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: bf1434b257aa014c8f46e34f2d57d109bd510452
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740085"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="83a1b-103">\<remove> elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="83a1b-103">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="83a1b-104">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="83a1b-104">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="83a1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83a1b-105">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="83a1b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="83a1b-106">Attribute</span></span>

|           | <span data-ttu-id="83a1b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="83a1b-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="83a1b-108">**key**</span><span class="sxs-lookup"><span data-stu-id="83a1b-108">**key**</span></span>   | <span data-ttu-id="83a1b-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="83a1b-109">Required attribute.</span></span><br><br><span data-ttu-id="83a1b-110">Especifica el nombre de la configuración que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="83a1b-110">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="83a1b-111">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="83a1b-111">Parent element</span></span>

| <span data-ttu-id="83a1b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="83a1b-112">Element</span></span> | <span data-ttu-id="83a1b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="83a1b-113">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="83a1b-114">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="83a1b-114">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="83a1b-115">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="83a1b-115">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="83a1b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83a1b-116">Child elements</span></span>

<span data-ttu-id="83a1b-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="83a1b-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="83a1b-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83a1b-118">Remarks</span></span>

<span data-ttu-id="83a1b-119">Puede usar el **\<remove>** elemento para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="83a1b-119">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="83a1b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83a1b-120">Example</span></span>

<span data-ttu-id="83a1b-121">En el ejemplo siguiente se muestra cómo utilizar el **\<remove>** elemento en un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="83a1b-121">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="83a1b-122">El siguiente código de archivo de configuración de máquina declara la sección **\<mySection>** y agrega dos valores de configuración `key1` `key2` :</span><span class="sxs-lookup"><span data-stu-id="83a1b-122">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="83a1b-123">El siguiente código de archivo de configuración de la aplicación quita la `key2` configuración de **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="83a1b-123">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="83a1b-124">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="83a1b-124">Configuration file</span></span>

<span data-ttu-id="83a1b-125">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83a1b-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="83a1b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="83a1b-126">See also</span></span>

- [<span data-ttu-id="83a1b-127">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83a1b-127">Configuration file schema for the .NET Framework</span></span>](index.md)
