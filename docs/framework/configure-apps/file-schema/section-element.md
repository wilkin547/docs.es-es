---
description: 'Más información acerca de: <section> elemento'
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 7756f7ee3be2391a0d068708f3719083640b5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639944"
---
# <a name="section-element"></a><span data-ttu-id="a2a39-104">Elemento \<section></span><span class="sxs-lookup"><span data-stu-id="a2a39-104">\<section> element</span></span>

<span data-ttu-id="a2a39-105">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-105">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="a2a39-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2a39-106">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="a2a39-107">Atributos necesarios</span><span class="sxs-lookup"><span data-stu-id="a2a39-107">Required attributes</span></span>

|           | <span data-ttu-id="a2a39-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2a39-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a2a39-109">**name**</span><span class="sxs-lookup"><span data-stu-id="a2a39-109">**name**</span></span>  | <span data-ttu-id="a2a39-110">Especifica el nombre de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-110">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="a2a39-111">**type**</span><span class="sxs-lookup"><span data-stu-id="a2a39-111">**type**</span></span>  | <span data-ttu-id="a2a39-112">Especifica el nombre de la clase de controlador de la sección de configuración que lee la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-112">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="a2a39-113">El valor de tipo tiene la sintaxis "Full-Qualified-Section-Handler-Class-Name, simple-Assembly-name".</span><span class="sxs-lookup"><span data-stu-id="a2a39-113">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="a2a39-114">El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *. dll* .</span><span class="sxs-lookup"><span data-stu-id="a2a39-114">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="a2a39-115">Atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="a2a39-115">Optional attributes</span></span>

<span data-ttu-id="a2a39-116">Los atributos siguientes solo son aplicables a las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a2a39-116">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="a2a39-117">El sistema de configuración omite estos atributos para otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a2a39-117">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="a2a39-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2a39-118">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="a2a39-119">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="a2a39-119">**allowDefinition**</span></span> | <span data-ttu-id="a2a39-120">Especifica el archivo de configuración en el que se puede usar la sección.</span><span class="sxs-lookup"><span data-stu-id="a2a39-120">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="a2a39-121">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2a39-121">Use one of the following values:</span></span><br><br><span data-ttu-id="a2a39-122">**En todas partes**</span><span class="sxs-lookup"><span data-stu-id="a2a39-122">**Everywhere**</span></span><br><span data-ttu-id="a2a39-123">Permite que la sección se use en cualquier archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-123">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="a2a39-124">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a2a39-124">This is the default.</span></span><br><span data-ttu-id="a2a39-125">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="a2a39-125">**MachineOnly**</span></span><br><span data-ttu-id="a2a39-126">Permite que la sección se use solo en el archivo de configuración del equipo (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="a2a39-126">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="a2a39-127">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="a2a39-127">**MachineToApplication**</span></span><br><span data-ttu-id="a2a39-128">Permite usar la sección en el archivo de configuración del equipo o en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2a39-128">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="a2a39-129">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="a2a39-129">**allowLocation**</span></span>   | <span data-ttu-id="a2a39-130">Determina si la sección se puede usar dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a2a39-130">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="a2a39-131">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2a39-131">Use one of the following values:</span></span><br><br><span data-ttu-id="a2a39-132">**true**</span><span class="sxs-lookup"><span data-stu-id="a2a39-132">**true**</span></span><br><span data-ttu-id="a2a39-133">Permite que la sección se use dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a2a39-133">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="a2a39-134">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a2a39-134">This is the default.</span></span><br><span data-ttu-id="a2a39-135">**false**</span><span class="sxs-lookup"><span data-stu-id="a2a39-135">**false**</span></span><br><span data-ttu-id="a2a39-136">No permite el uso de la sección dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a2a39-136">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="a2a39-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a2a39-137">Parent elements</span></span>

|     | <span data-ttu-id="a2a39-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2a39-138">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a2a39-139">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="a2a39-139">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="a2a39-140">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a2a39-140">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="a2a39-141">**\<sectionGroup>** Element</span><span class="sxs-lookup"><span data-stu-id="a2a39-141">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="a2a39-142">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-142">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="a2a39-143">Un **\<section>** elemento es un elemento secundario de **\<configSections>** o, **\<sectionGroup>** pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="a2a39-143">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="a2a39-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2a39-144">Child elements</span></span>

<span data-ttu-id="a2a39-145">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a2a39-145">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a2a39-146">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a2a39-146">Remarks</span></span>

<span data-ttu-id="a2a39-147">Al declarar una sección de configuración, básicamente se define un nuevo elemento para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-147">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="a2a39-148">El nuevo elemento contiene la configuración que lee un controlador de sección de configuración (es decir, una clase que implementa la <xref:System.Configuration.IConfigurationSectionHandler> interfaz).</span><span class="sxs-lookup"><span data-stu-id="a2a39-148">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="a2a39-149">Los atributos y elementos secundarios de una sección que se define dependen del controlador de la sección que se usa para leer la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2a39-149">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="a2a39-150">Declarar un controlador de sección de configuración en el archivo *Machine.config* le permite usar la sección de configuración en cualquier archivo de configuración de la aplicación de ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="a2a39-150">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="a2a39-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2a39-151">Example</span></span>

<span data-ttu-id="a2a39-152">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="a2a39-152">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="a2a39-153">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a2a39-153">Configuration file</span></span>

<span data-ttu-id="a2a39-154">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2a39-154">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2a39-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2a39-155">See also</span></span>

- [<span data-ttu-id="a2a39-156">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2a39-156">Configuration file schema for the .NET Framework</span></span>](index.md)
