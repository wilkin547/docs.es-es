---
title: Elemento <clear> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c06fca8b83638fb47bedb21863cb9b200cd211f3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927732"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="5a114-102">\<borrar > elemento para \<configSections ></span><span class="sxs-lookup"><span data-stu-id="5a114-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="5a114-103">Borra todas las secciones y grupos de sección definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="5a114-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="5a114-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5a114-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="5a114-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5a114-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="5a114-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="5a114-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5a114-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a114-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="5a114-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="5a114-108">Attribute</span></span>

|           | <span data-ttu-id="5a114-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5a114-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5a114-110">**name**</span><span class="sxs-lookup"><span data-stu-id="5a114-110">**name**</span></span>  | <span data-ttu-id="5a114-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5a114-111">Required attribute.</span></span><br><br><span data-ttu-id="5a114-112">Especifica el nombre de la sección o grupo de secciones que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="5a114-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5a114-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="5a114-113">Parent element</span></span>

|     | <span data-ttu-id="5a114-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5a114-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5a114-115">configSections (elemento >)  **\<** </span><span class="sxs-lookup"><span data-stu-id="5a114-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="5a114-116">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5a114-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5a114-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a114-117">Child elements</span></span>

<span data-ttu-id="5a114-118">None</span><span class="sxs-lookup"><span data-stu-id="5a114-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5a114-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a114-119">Remarks</span></span>

<span data-ttu-id="5a114-120">El elemento Clear > quita todas las secciones y grupos de secciones de la aplicación que se definieron anteriormente en el archivo de configuración actual o en un nivel superior en la jerarquía del archivo de configuración.  **\<**</span><span class="sxs-lookup"><span data-stu-id="5a114-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5a114-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a114-121">Example</span></span>

<span data-ttu-id="5a114-122">En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el  **\<elemento Clear >** en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en la configuración del equipo. filesystem.</span><span class="sxs-lookup"><span data-stu-id="5a114-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5a114-123">El siguiente código de archivo de configuración de máquina declara dos secciones,  **\<sampleSection >** y  **\<anotherSampleSection >** , que se leen antes del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="5a114-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="5a114-124">El siguiente código de archivo de configuración de la aplicación borra todas las secciones declaradas previamente.</span><span class="sxs-lookup"><span data-stu-id="5a114-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="5a114-125">La aplicación no puede usar ni recuperar la configuración de ninguna de las secciones que se han declarado en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="5a114-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="5a114-126">Sin embargo, puede usar la configuración de  **\<anotherSection >** porque va después del elemento de  **\<>** de borrado.</span><span class="sxs-lookup"><span data-stu-id="5a114-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="5a114-127">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5a114-127">Configuration file</span></span>

<span data-ttu-id="5a114-128">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a114-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a114-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a114-129">See also</span></span>

- [<span data-ttu-id="5a114-130">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a114-130">Configuration file schema for the .NET Framework</span></span>](index.md)
