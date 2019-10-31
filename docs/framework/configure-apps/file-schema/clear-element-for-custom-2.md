---
title: elemento <clear> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e27bb7e21baf2eb4990d0107db4aae1b5f9a7d1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119072"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="daf70-102">\<borrar > elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="daf70-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="daf70-103">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="daf70-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="daf70-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="daf70-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="daf70-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="daf70-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="daf70-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="daf70-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="daf70-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="daf70-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="daf70-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="daf70-108">Attributes</span></span>

<span data-ttu-id="daf70-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="daf70-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="daf70-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="daf70-110">Parent element</span></span>

|     | <span data-ttu-id="daf70-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="daf70-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="daf70-112"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="daf70-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="daf70-113">Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="daf70-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="daf70-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="daf70-114">Child elements</span></span>

<span data-ttu-id="daf70-115">Ninguno</span><span class="sxs-lookup"><span data-stu-id="daf70-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="daf70-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daf70-116">Remarks</span></span>

<span data-ttu-id="daf70-117">Puede usar el elemento **\<clear >** para quitar toda la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="daf70-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="daf70-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="daf70-118">Example</span></span>

<span data-ttu-id="daf70-119">En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el elemento **\<clear >** en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="daf70-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="daf70-120">El siguiente código de archivo de configuración de máquina declara la sección **\<mi sección >** :</span><span class="sxs-lookup"><span data-stu-id="daf70-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="daf70-121">El siguiente código de archivo de configuración de la aplicación quita todos los valores de\<de la **sección >** .</span><span class="sxs-lookup"><span data-stu-id="daf70-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="daf70-122">La aplicación no puede recuperar ninguno de los valores de configuración que se declararon en la sección **\<** sección del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="daf70-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="daf70-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="daf70-123">Configuration file</span></span>

<span data-ttu-id="daf70-124">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="daf70-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="daf70-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="daf70-125">See also</span></span>

- [<span data-ttu-id="daf70-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="daf70-126">Configuration file schema for the .NET Framework</span></span>](index.md)
