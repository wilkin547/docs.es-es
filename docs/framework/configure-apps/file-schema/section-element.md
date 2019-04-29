---
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 58f823ce0c128f30e361b4a631d41286533b5f0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701507"
---
# <a name="section-element"></a><span data-ttu-id="339c6-102">\<sección > elemento</span><span class="sxs-lookup"><span data-stu-id="339c6-102">\<section> element</span></span>

<span data-ttu-id="339c6-103">Contiene una declaración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="339c6-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="339c6-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="339c6-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="339c6-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="339c6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sección >**</span><span class="sxs-lookup"><span data-stu-id="339c6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="339c6-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="339c6-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="339c6-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="339c6-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="339c6-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="339c6-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="339c6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sección >**</span><span class="sxs-lookup"><span data-stu-id="339c6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="339c6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="339c6-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="339c6-112">Atributos requeridos</span><span class="sxs-lookup"><span data-stu-id="339c6-112">Required attributes</span></span>

|           | <span data-ttu-id="339c6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="339c6-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="339c6-114">**name**</span><span class="sxs-lookup"><span data-stu-id="339c6-114">**name**</span></span>  | <span data-ttu-id="339c6-115">Especifica el nombre de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="339c6-116">**type**</span><span class="sxs-lookup"><span data-stu-id="339c6-116">**type**</span></span>  | <span data-ttu-id="339c6-117">Especifica el nombre de la clase de controlador de sección de configuración que lee la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="339c6-118">El valor de tipo tiene la sintaxis "fully-qualified-section-handler-class-name, nombre de ensamblado simple".</span><span class="sxs-lookup"><span data-stu-id="339c6-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="339c6-119">El nombre de ensamblado simple es el nombre de archivo raíz sin el *.dll* la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="339c6-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="339c6-120">Atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="339c6-120">Optional attributes</span></span>

<span data-ttu-id="339c6-121">Los atributos siguientes son aplicables solo para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="339c6-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="339c6-122">El sistema de configuración omite estos atributos para otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="339c6-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="339c6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="339c6-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="339c6-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="339c6-124">**allowDefinition**</span></span> | <span data-ttu-id="339c6-125">Especifica qué archivo de configuración se puede utilizar la sección.</span><span class="sxs-lookup"><span data-stu-id="339c6-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="339c6-126">Utilice uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="339c6-126">Use one of the following values:</span></span><br><br><span data-ttu-id="339c6-127">**Everywhere**</span><span class="sxs-lookup"><span data-stu-id="339c6-127">**Everywhere**</span></span><br><span data-ttu-id="339c6-128">Permite la sección para usarse en cualquier archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="339c6-129">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="339c6-129">This is the default.</span></span><br><span data-ttu-id="339c6-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="339c6-130">**MachineOnly**</span></span><br><span data-ttu-id="339c6-131">Permite la sección que se usará solo en el archivo de configuración de máquina (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="339c6-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="339c6-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="339c6-132">**MachineToApplication**</span></span><br><span data-ttu-id="339c6-133">Permite la sección que se usará en el archivo de configuración del equipo o el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="339c6-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="339c6-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="339c6-134">**allowLocation**</span></span>   | <span data-ttu-id="339c6-135">Determina si se puede usar la sección dentro de la  **\<ubicación >** elemento.</span><span class="sxs-lookup"><span data-stu-id="339c6-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="339c6-136">Utilice uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="339c6-136">Use one of the following values:</span></span><br><br><span data-ttu-id="339c6-137">**true**</span><span class="sxs-lookup"><span data-stu-id="339c6-137">**true**</span></span><br><span data-ttu-id="339c6-138">Permite la sección para su uso en el  **\<ubicación >** elemento.</span><span class="sxs-lookup"><span data-stu-id="339c6-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="339c6-139">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="339c6-139">This is the default.</span></span><br><span data-ttu-id="339c6-140">**false**</span><span class="sxs-lookup"><span data-stu-id="339c6-140">**false**</span></span><br><span data-ttu-id="339c6-141">No se permite la sección para su uso en el  **\<ubicación >** elemento.</span><span class="sxs-lookup"><span data-stu-id="339c6-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="339c6-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="339c6-142">Parent elements</span></span>

|     | <span data-ttu-id="339c6-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="339c6-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="339c6-144">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="339c6-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="339c6-145">Contiene las declaraciones de espacio de nombres y la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="339c6-146">**\<sectionGroup >** elemento</span><span class="sxs-lookup"><span data-stu-id="339c6-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="339c6-147">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="339c6-148">Un  **\<sección >** elemento es un elemento secundario de uno de ellos  **\<configSections >** o  **\<sectionGroup >** pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="339c6-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="339c6-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="339c6-149">Child elements</span></span>

<span data-ttu-id="339c6-150">Ninguna</span><span class="sxs-lookup"><span data-stu-id="339c6-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="339c6-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="339c6-151">Remarks</span></span>

<span data-ttu-id="339c6-152">Declarar esencialmente una sección de configuración define un nuevo elemento para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="339c6-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="339c6-153">El nuevo elemento contiene la configuración que una sección de configuración controlador (es decir, una clase que implementa el <xref:System.Configuration.IConfigurationSectionHandler> interfaz) lee.</span><span class="sxs-lookup"><span data-stu-id="339c6-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="339c6-154">El controlador de sección que se utiliza para leer la configuración de dependen de los atributos y elementos secundarios de una sección que defina.</span><span class="sxs-lookup"><span data-stu-id="339c6-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="339c6-155">Declarar un controlador de la sección de configuración en el *Machine.config* archivo le permite usar la sección de configuración en cualquier archivo de configuración en ese equipo, a menos que el **allowDefinition**atributo especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="339c6-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="339c6-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="339c6-156">Example</span></span>

<span data-ttu-id="339c6-157">El ejemplo siguiente muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="339c6-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="339c6-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="339c6-158">Configuration file</span></span>

<span data-ttu-id="339c6-159">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="339c6-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="339c6-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="339c6-160">See also</span></span>

- [<span data-ttu-id="339c6-161">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="339c6-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
