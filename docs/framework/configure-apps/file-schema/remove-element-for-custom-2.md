---
title: <remove>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214756"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="2711d-102">\<remove>elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="2711d-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="2711d-103">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="2711d-103">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="2711d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2711d-104">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="2711d-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="2711d-105">Attribute</span></span>

|           | <span data-ttu-id="2711d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2711d-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2711d-107">**key**</span><span class="sxs-lookup"><span data-stu-id="2711d-107">**key**</span></span>   | <span data-ttu-id="2711d-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2711d-108">Required attribute.</span></span><br><br><span data-ttu-id="2711d-109">Especifica el nombre de la configuración que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="2711d-109">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2711d-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="2711d-110">Parent element</span></span>

| <span data-ttu-id="2711d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2711d-111">Element</span></span> | <span data-ttu-id="2711d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2711d-112">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="2711d-113">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="2711d-113">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="2711d-114">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="2711d-114">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2711d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2711d-115">Child elements</span></span>

<span data-ttu-id="2711d-116">None</span><span class="sxs-lookup"><span data-stu-id="2711d-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2711d-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2711d-117">Remarks</span></span>

<span data-ttu-id="2711d-118">Puede usar el **\<remove>** elemento para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2711d-118">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="2711d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2711d-119">Example</span></span>

<span data-ttu-id="2711d-120">En el ejemplo siguiente se muestra cómo utilizar el **\<remove>** elemento en un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="2711d-120">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="2711d-121">El siguiente código de archivo de configuración de máquina declara la sección **\<mySection>** y agrega dos valores de configuración `key1` `key2` :</span><span class="sxs-lookup"><span data-stu-id="2711d-121">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="2711d-122">El siguiente código de archivo de configuración de la aplicación quita la `key2` configuración de **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="2711d-122">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="2711d-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="2711d-123">Configuration file</span></span>

<span data-ttu-id="2711d-124">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2711d-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2711d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2711d-125">See also</span></span>

- [<span data-ttu-id="2711d-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2711d-126">Configuration file schema for the .NET Framework</span></span>](index.md)
