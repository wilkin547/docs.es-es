---
title: '&lt;Borrar&gt; (elemento) para &lt;configSections&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e48887cf7e227f463b92edd50f69746bbd8abd0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="0d442-102">\<Borrar > (elemento) para \<configSections ></span><span class="sxs-lookup"><span data-stu-id="0d442-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="0d442-103">Borra todas las secciones definidas anteriormente y grupos de sección.</span><span class="sxs-lookup"><span data-stu-id="0d442-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="0d442-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d442-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0d442-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d442-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0d442-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Borrar >**</span><span class="sxs-lookup"><span data-stu-id="0d442-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0d442-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d442-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="0d442-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0d442-108">Attribute</span></span>

|           | <span data-ttu-id="0d442-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d442-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0d442-110">**name**</span><span class="sxs-lookup"><span data-stu-id="0d442-110">**name**</span></span>  | <span data-ttu-id="0d442-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0d442-111">Required attribute.</span></span><br><br><span data-ttu-id="0d442-112">Especifica el nombre de la sección o el grupo de sección para quitar.</span><span class="sxs-lookup"><span data-stu-id="0d442-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0d442-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="0d442-113">Parent element</span></span>

|     | <span data-ttu-id="0d442-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d442-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d442-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="0d442-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="0d442-116">Contiene las declaraciones de espacio de nombres y la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="0d442-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="0d442-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d442-117">Child elements</span></span>

<span data-ttu-id="0d442-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="0d442-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0d442-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d442-119">Remarks</span></span>

<span data-ttu-id="0d442-120">El  **\<borrar >** elemento quita todas las secciones y grupos de secciones de la aplicación que se definieron anteriormente en el archivo de configuración actual o en un nivel superior en la jerarquía de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="0d442-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="0d442-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d442-121">Example</span></span>

<span data-ttu-id="0d442-122">Este ejemplo define un archivo de configuración del equipo y un archivo de configuración de aplicación y muestra cómo utilizar el  **\<borrar >** elemento en un archivo de configuración de aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="0d442-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="0d442-123">El siguiente código de archivo de configuración de máquina declara dos secciones,  **\<sampleSection >** y  **\<anotherSampleSection >**, que se leen antes de que la aplicación archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="0d442-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="0d442-124">El siguiente código de archivo de configuración de la aplicación borra todas las secciones declaradas previamente.</span><span class="sxs-lookup"><span data-stu-id="0d442-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="0d442-125">La aplicación no se puede utilizar ni recuperar la configuración de cualquiera de las secciones que se han declarado en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="0d442-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="0d442-126">Sin embargo, se pueden utilizar los valores de  **\<anotherSection >** dado que viene después de la  **\<borrar >** elemento.</span><span class="sxs-lookup"><span data-stu-id="0d442-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0d442-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0d442-127">Configuration file</span></span>

<span data-ttu-id="0d442-128">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d442-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d442-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d442-129">See also</span></span>

[<span data-ttu-id="0d442-130">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d442-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
