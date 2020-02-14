---
title: elemento <remove> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214756"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="f2cb0-102">\<quitar > elemento de NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="f2cb0-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="f2cb0-103">Quita un valor definido previamente.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="f2cb0-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2cb0-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="f2cb0-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="f2cb0-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="f2cb0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**</span><span class="sxs-lookup"><span data-stu-id="f2cb0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f2cb0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2cb0-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="f2cb0-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f2cb0-108">Attribute</span></span>

|           | <span data-ttu-id="f2cb0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2cb0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f2cb0-110">**key**</span><span class="sxs-lookup"><span data-stu-id="f2cb0-110">**key**</span></span>   | <span data-ttu-id="f2cb0-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-111">Required attribute.</span></span><br><br><span data-ttu-id="f2cb0-112">Especifica el nombre de la configuración que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f2cb0-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="f2cb0-113">Parent element</span></span>

| <span data-ttu-id="f2cb0-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2cb0-114">Element</span></span> | <span data-ttu-id="f2cb0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2cb0-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="f2cb0-116"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="f2cb0-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="f2cb0-117">Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f2cb0-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f2cb0-118">Child elements</span></span>

<span data-ttu-id="f2cb0-119">None</span><span class="sxs-lookup"><span data-stu-id="f2cb0-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f2cb0-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2cb0-120">Remarks</span></span>

<span data-ttu-id="f2cb0-121">Puede usar el elemento **\<remove >** para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="f2cb0-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2cb0-122">Example</span></span>

<span data-ttu-id="f2cb0-123">En el ejemplo siguiente se muestra cómo usar el elemento **\<quitar >** de un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="f2cb0-124">El siguiente código de archivo de configuración de máquina declara la sección **\<mi sección >** y le agrega dos valores, `key1` y `key2`:</span><span class="sxs-lookup"><span data-stu-id="f2cb0-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="f2cb0-125">El siguiente código de archivo de configuración de la aplicación quita el valor `key2` de **\<sección >** :</span><span class="sxs-lookup"><span data-stu-id="f2cb0-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f2cb0-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f2cb0-126">Configuration file</span></span>

<span data-ttu-id="f2cb0-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2cb0-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2cb0-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2cb0-128">See also</span></span>

- [<span data-ttu-id="f2cb0-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2cb0-129">Configuration file schema for the .NET Framework</span></span>](index.md)
