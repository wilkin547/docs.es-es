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
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153740"
---
# <a name="section-element"></a><span data-ttu-id="76d37-102">\<sección> elemento</span><span class="sxs-lookup"><span data-stu-id="76d37-102">\<section> element</span></span>

<span data-ttu-id="76d37-103">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="76d37-104">[**\<configuración>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76d37-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="76d37-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="76d37-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="76d37-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sección>**</span><span class="sxs-lookup"><span data-stu-id="76d37-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="76d37-107">[**\<configuración>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76d37-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="76d37-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="76d37-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="76d37-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="76d37-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="76d37-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sección>**</span><span class="sxs-lookup"><span data-stu-id="76d37-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="76d37-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76d37-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="76d37-112">Atributos necesarios</span><span class="sxs-lookup"><span data-stu-id="76d37-112">Required attributes</span></span>

|           | <span data-ttu-id="76d37-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="76d37-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="76d37-114">**nombre**</span><span class="sxs-lookup"><span data-stu-id="76d37-114">**name**</span></span>  | <span data-ttu-id="76d37-115">Especifica el nombre de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="76d37-116">**tipo**</span><span class="sxs-lookup"><span data-stu-id="76d37-116">**type**</span></span>  | <span data-ttu-id="76d37-117">Especifica el nombre de la clase de controlador de sección de configuración que lee la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="76d37-118">El valor de tipo tiene la sintaxis "fully-qualified-section-handler-class-name, simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="76d37-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="76d37-119">El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *.dll.*</span><span class="sxs-lookup"><span data-stu-id="76d37-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="76d37-120">Atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="76d37-120">Optional attributes</span></span>

<span data-ttu-id="76d37-121">Los siguientes atributos solo se aplican a las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="76d37-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="76d37-122">El sistema de configuración omite estos atributos para otros tipos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="76d37-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="76d37-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="76d37-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="76d37-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="76d37-124">**allowDefinition**</span></span> | <span data-ttu-id="76d37-125">Especifica en qué archivo de configuración se puede utilizar la sección.</span><span class="sxs-lookup"><span data-stu-id="76d37-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="76d37-126">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="76d37-126">Use one of the following values:</span></span><br><br><span data-ttu-id="76d37-127">**En todas partes**</span><span class="sxs-lookup"><span data-stu-id="76d37-127">**Everywhere**</span></span><br><span data-ttu-id="76d37-128">Permite que la sección se utilice en cualquier archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="76d37-129">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="76d37-129">This is the default.</span></span><br><span data-ttu-id="76d37-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="76d37-130">**MachineOnly**</span></span><br><span data-ttu-id="76d37-131">Permite que la sección se utilice solo en el archivo de configuración de la máquina (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="76d37-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="76d37-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="76d37-132">**MachineToApplication**</span></span><br><span data-ttu-id="76d37-133">Permite utilizar la sección en el archivo de configuración de la máquina o en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76d37-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="76d37-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="76d37-134">**allowLocation**</span></span>   | <span data-ttu-id="76d37-135">Determina si la sección se \*\* \<\*\* puede utilizar dentro de la ubicación>elemento.</span><span class="sxs-lookup"><span data-stu-id="76d37-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="76d37-136">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="76d37-136">Use one of the following values:</span></span><br><br><span data-ttu-id="76d37-137">**true**</span><span class="sxs-lookup"><span data-stu-id="76d37-137">**true**</span></span><br><span data-ttu-id="76d37-138">Permite que la sección \*\* \<\*\* se utilice dentro de la ubicación>elemento.</span><span class="sxs-lookup"><span data-stu-id="76d37-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="76d37-139">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="76d37-139">This is the default.</span></span><br><span data-ttu-id="76d37-140">**false**</span><span class="sxs-lookup"><span data-stu-id="76d37-140">**false**</span></span><br><span data-ttu-id="76d37-141">No permite que la sección \*\* \<\*\* se utilice dentro de la ubicación>elemento.</span><span class="sxs-lookup"><span data-stu-id="76d37-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="76d37-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76d37-142">Parent elements</span></span>

|     | <span data-ttu-id="76d37-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="76d37-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="76d37-144">\*\* \<configSections>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="76d37-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="76d37-145">Contiene declaraciones de sección de configuración y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="76d37-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="76d37-146">\*\* \<sectionGroup>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="76d37-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="76d37-147">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="76d37-148">Un \*\* \<elemento de>\*\* de sección es un elemento secundario de \*\* \<configSections>\*\* o \*\* \<sectionGroup>\*\* pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="76d37-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="76d37-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76d37-149">Child elements</span></span>

<span data-ttu-id="76d37-150">None</span><span class="sxs-lookup"><span data-stu-id="76d37-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="76d37-151">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76d37-151">Remarks</span></span>

<span data-ttu-id="76d37-152">Al declarar una sección de configuración, se define esencialmente un nuevo elemento para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="76d37-153">El nuevo elemento contiene la configuración que lee un controlador <xref:System.Configuration.IConfigurationSectionHandler> de sección de configuración (es decir, una clase que implementa la interfaz).</span><span class="sxs-lookup"><span data-stu-id="76d37-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="76d37-154">Los atributos y elementos secundarios de una sección que defina dependen del controlador de sección que utilice para leer la configuración.</span><span class="sxs-lookup"><span data-stu-id="76d37-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="76d37-155">Declarar un controlador de sección de configuración en el archivo *Machine.config* le permite usar la sección de configuración en cualquier archivo de configuración de la aplicación en ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="76d37-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="76d37-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76d37-156">Example</span></span>

<span data-ttu-id="76d37-157">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="76d37-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="76d37-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="76d37-158">Configuration file</span></span>

<span data-ttu-id="76d37-159">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76d37-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="76d37-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76d37-160">See also</span></span>

- [<span data-ttu-id="76d37-161">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="76d37-161">Configuration file schema for the .NET Framework</span></span>](index.md)
