---
title: <clear>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927704"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="56639-102">\<borrar > elemento de NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="56639-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="56639-103">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="56639-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="56639-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="56639-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="56639-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="56639-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="56639-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="56639-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="56639-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56639-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="56639-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="56639-108">Attributes</span></span>

<span data-ttu-id="56639-109">None</span><span class="sxs-lookup"><span data-stu-id="56639-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="56639-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="56639-110">Parent element</span></span>

|     | <span data-ttu-id="56639-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="56639-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="56639-112"> **sectionName>\<** elemento</span><span class="sxs-lookup"><span data-stu-id="56639-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="56639-113">Define la configuración de las secciones de configuración personalizadas <xref:System.Configuration.NameValueSectionHandler> que <xref:System.Configuration.DictionarySectionHandler> utilizan las clases y.</span><span class="sxs-lookup"><span data-stu-id="56639-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="56639-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56639-114">Child elements</span></span>

<span data-ttu-id="56639-115">None</span><span class="sxs-lookup"><span data-stu-id="56639-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="56639-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56639-116">Remarks</span></span>

<span data-ttu-id="56639-117">Puede usar el  **\<elemento Clear >** para quitar toda la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="56639-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="56639-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56639-118">Example</span></span>

<span data-ttu-id="56639-119">En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el  **\<elemento Clear >** en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en la configuración del equipo. filesystem.</span><span class="sxs-lookup"><span data-stu-id="56639-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="56639-120">El siguiente código de archivo de configuración de máquina declara la sección  **\<>** :</span><span class="sxs-lookup"><span data-stu-id="56639-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="56639-121">El siguiente código de archivo de configuración de la aplicación quita todos los valores de  **\<la sección >** .</span><span class="sxs-lookup"><span data-stu-id="56639-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="56639-122">La aplicación no puede recuperar ninguno de los valores de configuración que se declararon en la sección de la  **\<sección >** del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="56639-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="56639-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="56639-123">Configuration file</span></span>

<span data-ttu-id="56639-124">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="56639-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="56639-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="56639-125">See also</span></span>

- [<span data-ttu-id="56639-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="56639-126">Configuration file schema for the .NET Framework</span></span>](index.md)
