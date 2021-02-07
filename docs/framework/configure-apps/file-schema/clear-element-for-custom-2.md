---
description: 'Más información sobre: <clear> elemento para NameValueSectionHandler y DictionarySectionHandler'
title: <clear> elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: 896aa7e8f0e3b41574538fcd9e4be9d6155da889
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699238"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="a22ca-103">\<clear> elemento para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="a22ca-103">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="a22ca-104">Borra todos los valores de configuración definidos previamente en una sección.</span><span class="sxs-lookup"><span data-stu-id="a22ca-104">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="a22ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a22ca-105">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="a22ca-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a22ca-106">Attributes</span></span>

<span data-ttu-id="a22ca-107">None</span><span class="sxs-lookup"><span data-stu-id="a22ca-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="a22ca-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a22ca-108">Parent element</span></span>

|     | <span data-ttu-id="a22ca-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a22ca-109">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="a22ca-110">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="a22ca-110">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="a22ca-111">Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.</span><span class="sxs-lookup"><span data-stu-id="a22ca-111">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a22ca-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a22ca-112">Child elements</span></span>

<span data-ttu-id="a22ca-113">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a22ca-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a22ca-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a22ca-114">Remarks</span></span>

<span data-ttu-id="a22ca-115">Puede usar el **\<clear>** elemento para quitar toda la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a22ca-115">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="a22ca-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a22ca-116">Example</span></span>

<span data-ttu-id="a22ca-117">En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el **\<clear>** elemento en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="a22ca-117">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="a22ca-118">El siguiente código de archivo de configuración de máquina declara la sección **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="a22ca-118">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="a22ca-119">El siguiente código de archivo de configuración de la aplicación quita todos los valores de **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="a22ca-119">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="a22ca-120">La aplicación no puede recuperar ninguno de los valores de configuración que se declararon en la **\<mySection>** sección del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="a22ca-120">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a22ca-121">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a22ca-121">Configuration file</span></span>

<span data-ttu-id="a22ca-122">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a22ca-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a22ca-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a22ca-123">See also</span></span>

- [<span data-ttu-id="a22ca-124">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a22ca-124">Configuration file schema for the .NET Framework</span></span>](index.md)
