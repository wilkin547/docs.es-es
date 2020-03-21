---
title: Elemento <clear> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155432"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="041c5-102">\<claro> \<elemento para configSections></span><span class="sxs-lookup"><span data-stu-id="041c5-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="041c5-103">Borra todas las secciones y grupos de secciones definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="041c5-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="041c5-104">&nbsp; &nbsp; &nbsp; [\*\* \<configuración>\*\*](configuration-element.md) &nbsp; &nbsp; &nbsp;>**>>>>de>\<** [\*\* \<\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="041c5-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="041c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="041c5-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="041c5-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="041c5-106">Attribute</span></span>

|           | <span data-ttu-id="041c5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="041c5-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="041c5-108">**nombre**</span><span class="sxs-lookup"><span data-stu-id="041c5-108">**name**</span></span>  | <span data-ttu-id="041c5-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="041c5-109">Required attribute.</span></span><br><br><span data-ttu-id="041c5-110">Especifica el nombre de la sección o grupo de secciones que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="041c5-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="041c5-111">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="041c5-111">Parent element</span></span>

|     | <span data-ttu-id="041c5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="041c5-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="041c5-113">\*\* \<configSections>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="041c5-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="041c5-114">Contiene declaraciones de sección de configuración y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="041c5-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="041c5-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="041c5-115">Child elements</span></span>

<span data-ttu-id="041c5-116">None</span><span class="sxs-lookup"><span data-stu-id="041c5-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="041c5-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="041c5-117">Remarks</span></span>

<span data-ttu-id="041c5-118">El elemento \*\* \<>claro\*\* quita todas las secciones y grupos de secciones de la aplicación que se definieron anteriormente en el archivo de configuración actual o en un nivel superior de la jerarquía de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="041c5-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="041c5-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="041c5-119">Example</span></span>

<span data-ttu-id="041c5-120">En este ejemplo se define un archivo de configuración \*\* \<\*\* de máquina y un archivo de configuración de la aplicación y se muestra cómo utilizar el elemento>claro en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="041c5-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="041c5-121">El siguiente código de archivo de configuración del equipo declara dos secciones, \*\* \<sampleSection>\*\* y \*\* \<anotherSampleSection>\*\*, que se leen antes del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="041c5-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="041c5-122">El siguiente código de archivo de configuración de la aplicación borra todas las secciones declaradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="041c5-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="041c5-123">La aplicación no puede usar ni recuperar la configuración en ninguna de las secciones que se declararon en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="041c5-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="041c5-124">Sin embargo, puede usar la configuración de \*\* \<otroSection>\*\* porque viene después del \*\* \<elemento de>claro.\*\*</span><span class="sxs-lookup"><span data-stu-id="041c5-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="041c5-125">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="041c5-125">Configuration file</span></span>

<span data-ttu-id="041c5-126">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="041c5-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="041c5-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="041c5-127">See also</span></span>

- [<span data-ttu-id="041c5-128">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="041c5-128">Configuration file schema for the .NET Framework</span></span>](index.md)
