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
ms.openlocfilehash: 8785523d664294e3ca3792fb0f84d739d1f1a376
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215727"
---
# <a name="section-element"></a><span data-ttu-id="5f5be-102">\<sección > elemento</span><span class="sxs-lookup"><span data-stu-id="5f5be-102">\<section> element</span></span>

<span data-ttu-id="5f5be-103">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="5f5be-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5f5be-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="5f5be-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="5f5be-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="5f5be-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sección** ></span><span class="sxs-lookup"><span data-stu-id="5f5be-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="5f5be-107">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5f5be-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="5f5be-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="5f5be-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="5f5be-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup**](sectiongroup-element-for-configsections.md) ></span><span class="sxs-lookup"><span data-stu-id="5f5be-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="5f5be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sección** ></span><span class="sxs-lookup"><span data-stu-id="5f5be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5f5be-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f5be-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="5f5be-112">Atributos necesarios</span><span class="sxs-lookup"><span data-stu-id="5f5be-112">Required attributes</span></span>

|           | <span data-ttu-id="5f5be-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f5be-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5f5be-114">**name**</span><span class="sxs-lookup"><span data-stu-id="5f5be-114">**name**</span></span>  | <span data-ttu-id="5f5be-115">Especifica el nombre de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="5f5be-116">**type**</span><span class="sxs-lookup"><span data-stu-id="5f5be-116">**type**</span></span>  | <span data-ttu-id="5f5be-117">Especifica el nombre de la clase de controlador de la sección de configuración que lee la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="5f5be-118">El valor de tipo tiene la sintaxis "Full-Qualified-Section-Handler-Class-Name, simple-Assembly-name".</span><span class="sxs-lookup"><span data-stu-id="5f5be-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="5f5be-119">El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *. dll* .</span><span class="sxs-lookup"><span data-stu-id="5f5be-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="5f5be-120">Atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="5f5be-120">Optional attributes</span></span>

<span data-ttu-id="5f5be-121">Los atributos siguientes solo son aplicables a las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5f5be-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="5f5be-122">El sistema de configuración omite estos atributos para otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5f5be-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="5f5be-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f5be-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="5f5be-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="5f5be-124">**allowDefinition**</span></span> | <span data-ttu-id="5f5be-125">Especifica el archivo de configuración en el que se puede usar la sección.</span><span class="sxs-lookup"><span data-stu-id="5f5be-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="5f5be-126">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f5be-126">Use one of the following values:</span></span><br><br><span data-ttu-id="5f5be-127">**Todas**</span><span class="sxs-lookup"><span data-stu-id="5f5be-127">**Everywhere**</span></span><br><span data-ttu-id="5f5be-128">Permite que la sección se use en cualquier archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="5f5be-129">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f5be-129">This is the default.</span></span><br><span data-ttu-id="5f5be-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="5f5be-130">**MachineOnly**</span></span><br><span data-ttu-id="5f5be-131">Permite que la sección se use solo en el archivo de configuración del equipo (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="5f5be-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="5f5be-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="5f5be-132">**MachineToApplication**</span></span><br><span data-ttu-id="5f5be-133">Permite usar la sección en el archivo de configuración del equipo o en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f5be-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="5f5be-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="5f5be-134">**allowLocation**</span></span>   | <span data-ttu-id="5f5be-135">Determina si la sección se puede usar dentro del elemento de **> de ubicación\<** .</span><span class="sxs-lookup"><span data-stu-id="5f5be-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="5f5be-136">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f5be-136">Use one of the following values:</span></span><br><br><span data-ttu-id="5f5be-137">**true**</span><span class="sxs-lookup"><span data-stu-id="5f5be-137">**true**</span></span><br><span data-ttu-id="5f5be-138">Permite que la sección se use dentro del elemento **\<location >** .</span><span class="sxs-lookup"><span data-stu-id="5f5be-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="5f5be-139">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f5be-139">This is the default.</span></span><br><span data-ttu-id="5f5be-140">**false**</span><span class="sxs-lookup"><span data-stu-id="5f5be-140">**false**</span></span><br><span data-ttu-id="5f5be-141">No permite el uso de la sección dentro del elemento **\<location >** .</span><span class="sxs-lookup"><span data-stu-id="5f5be-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="5f5be-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f5be-142">Parent elements</span></span>

|     | <span data-ttu-id="5f5be-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f5be-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5f5be-144"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="5f5be-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="5f5be-145">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5f5be-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="5f5be-146"> **\<sectionGroup >** Element</span><span class="sxs-lookup"><span data-stu-id="5f5be-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="5f5be-147">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="5f5be-148">Una **\<sección >** elemento es un elemento secundario de **\<configSections >** o **\<sectionGroup** >, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="5f5be-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="5f5be-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f5be-149">Child elements</span></span>

<span data-ttu-id="5f5be-150">None</span><span class="sxs-lookup"><span data-stu-id="5f5be-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5f5be-151">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f5be-151">Remarks</span></span>

<span data-ttu-id="5f5be-152">Al declarar una sección de configuración, básicamente se define un nuevo elemento para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="5f5be-153">El nuevo elemento contiene valores que lee un controlador de sección de configuración (es decir, una clase que implementa la interfaz <xref:System.Configuration.IConfigurationSectionHandler>).</span><span class="sxs-lookup"><span data-stu-id="5f5be-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="5f5be-154">Los atributos y elementos secundarios de una sección que se define dependen del controlador de la sección que se usa para leer la configuración.</span><span class="sxs-lookup"><span data-stu-id="5f5be-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="5f5be-155">Declarar un controlador de sección de configuración en el archivo *Machine. config* permite usar la sección de configuración en cualquier archivo de configuración de la aplicación de ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="5f5be-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="5f5be-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f5be-156">Example</span></span>

<span data-ttu-id="5f5be-157">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="5f5be-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="5f5be-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5f5be-158">Configuration file</span></span>

<span data-ttu-id="5f5be-159">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f5be-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f5be-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f5be-160">See also</span></span>

- [<span data-ttu-id="5f5be-161">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5f5be-161">Configuration file schema for the .NET Framework</span></span>](index.md)
