---
title: '&lt;Borrar&gt; elemento para NameValueSectionHandler y DictionarySectionHandler'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57ee634c987d344d81f1ca099fe55e633bfbf659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="1d6fc-102">\<Borrar > (elemento) para NameValueSectionHandler y DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="1d6fc-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="1d6fc-103">Borra todos los valores definidos anteriormente en una sección.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="1d6fc-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1d6fc-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="1d6fc-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="1d6fc-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="1d6fc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Borrar >**</span><span class="sxs-lookup"><span data-stu-id="1d6fc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1d6fc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d6fc-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="1d6fc-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1d6fc-108">Attributes</span></span>

<span data-ttu-id="1d6fc-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1d6fc-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1d6fc-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="1d6fc-110">Parent element</span></span>

|     | <span data-ttu-id="1d6fc-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d6fc-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="1d6fc-112">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="1d6fc-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="1d6fc-113">Define los valores de las secciones de configuración personalizada que utilizan el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1d6fc-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1d6fc-114">Child elements</span></span>

<span data-ttu-id="1d6fc-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1d6fc-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="1d6fc-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d6fc-116">Remarks</span></span>

<span data-ttu-id="1d6fc-117">Puede usar el  **\<borrar >** elemento para quitar toda la configuración de la aplicación que se han definido en un nivel superior en la jerarquía de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="1d6fc-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d6fc-118">Example</span></span>

<span data-ttu-id="1d6fc-119">Este ejemplo define un archivo de configuración del equipo y un archivo de configuración de aplicación y muestra cómo utilizar el  **\<borrar >** elemento en un archivo de configuración de aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="1d6fc-120">El siguiente código de archivo de configuración del equipo declara la sección  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="1d6fc-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="1d6fc-121">El siguiente código de archivo de configuración de la aplicación quita todos los valores de  **\<mySection >**.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="1d6fc-122">La aplicación no puede recuperar la configuración que se declaran en el en el  **\<mySection >** sección del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="1d6fc-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1d6fc-123">Configuration file</span></span>

<span data-ttu-id="1d6fc-124">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d6fc-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d6fc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d6fc-125">See also</span></span>

[<span data-ttu-id="1d6fc-126">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1d6fc-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
