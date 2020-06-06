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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153740"
---
# <a name="section-element"></a><span data-ttu-id="4041a-102">Elemento \<section></span><span class="sxs-lookup"><span data-stu-id="4041a-102">\<section> element</span></span>

<span data-ttu-id="4041a-103">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-103">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="4041a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4041a-104">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="4041a-105">Atributos necesarios</span><span class="sxs-lookup"><span data-stu-id="4041a-105">Required attributes</span></span>

|           | <span data-ttu-id="4041a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4041a-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4041a-107">**name**</span><span class="sxs-lookup"><span data-stu-id="4041a-107">**name**</span></span>  | <span data-ttu-id="4041a-108">Especifica el nombre de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-108">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="4041a-109">**type**</span><span class="sxs-lookup"><span data-stu-id="4041a-109">**type**</span></span>  | <span data-ttu-id="4041a-110">Especifica el nombre de la clase de controlador de la sección de configuración que lee la sección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-110">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="4041a-111">El valor de tipo tiene la sintaxis "Full-Qualified-Section-Handler-Class-Name, simple-Assembly-name".</span><span class="sxs-lookup"><span data-stu-id="4041a-111">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="4041a-112">El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *. dll* .</span><span class="sxs-lookup"><span data-stu-id="4041a-112">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="4041a-113">Atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="4041a-113">Optional attributes</span></span>

<span data-ttu-id="4041a-114">Los atributos siguientes solo son aplicables a las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4041a-114">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="4041a-115">El sistema de configuración omite estos atributos para otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4041a-115">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="4041a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4041a-116">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="4041a-117">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="4041a-117">**allowDefinition**</span></span> | <span data-ttu-id="4041a-118">Especifica el archivo de configuración en el que se puede usar la sección.</span><span class="sxs-lookup"><span data-stu-id="4041a-118">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="4041a-119">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4041a-119">Use one of the following values:</span></span><br><br><span data-ttu-id="4041a-120">**En todas partes**</span><span class="sxs-lookup"><span data-stu-id="4041a-120">**Everywhere**</span></span><br><span data-ttu-id="4041a-121">Permite que la sección se use en cualquier archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-121">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="4041a-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4041a-122">This is the default.</span></span><br><span data-ttu-id="4041a-123">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="4041a-123">**MachineOnly**</span></span><br><span data-ttu-id="4041a-124">Permite que la sección se use solo en el archivo de configuración del equipo (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="4041a-124">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="4041a-125">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="4041a-125">**MachineToApplication**</span></span><br><span data-ttu-id="4041a-126">Permite usar la sección en el archivo de configuración del equipo o en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4041a-126">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="4041a-127">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="4041a-127">**allowLocation**</span></span>   | <span data-ttu-id="4041a-128">Determina si la sección se puede usar dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4041a-128">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="4041a-129">Utilice uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4041a-129">Use one of the following values:</span></span><br><br><span data-ttu-id="4041a-130">**true**</span><span class="sxs-lookup"><span data-stu-id="4041a-130">**true**</span></span><br><span data-ttu-id="4041a-131">Permite que la sección se use dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4041a-131">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="4041a-132">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4041a-132">This is the default.</span></span><br><span data-ttu-id="4041a-133">**false**</span><span class="sxs-lookup"><span data-stu-id="4041a-133">**false**</span></span><br><span data-ttu-id="4041a-134">No permite el uso de la sección dentro del **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4041a-134">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="4041a-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4041a-135">Parent elements</span></span>

|     | <span data-ttu-id="4041a-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="4041a-136">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4041a-137">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="4041a-137">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="4041a-138">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4041a-138">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="4041a-139">**\<sectionGroup>** Element</span><span class="sxs-lookup"><span data-stu-id="4041a-139">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="4041a-140">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-140">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="4041a-141">Un **\<section>** elemento es un elemento secundario de **\<configSections>** o, **\<sectionGroup>** pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="4041a-141">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="4041a-142">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4041a-142">Child elements</span></span>

<span data-ttu-id="4041a-143">None</span><span class="sxs-lookup"><span data-stu-id="4041a-143">None</span></span>

## <a name="remarks"></a><span data-ttu-id="4041a-144">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4041a-144">Remarks</span></span>

<span data-ttu-id="4041a-145">Al declarar una sección de configuración, básicamente se define un nuevo elemento para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-145">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="4041a-146">El nuevo elemento contiene la configuración que lee un controlador de sección de configuración (es decir, una clase que implementa la <xref:System.Configuration.IConfigurationSectionHandler> interfaz).</span><span class="sxs-lookup"><span data-stu-id="4041a-146">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="4041a-147">Los atributos y elementos secundarios de una sección que se define dependen del controlador de la sección que se usa para leer la configuración.</span><span class="sxs-lookup"><span data-stu-id="4041a-147">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="4041a-148">Declarar un controlador de sección de configuración en el archivo *Machine. config* permite usar la sección de configuración en cualquier archivo de configuración de la aplicación de ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="4041a-148">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="4041a-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4041a-149">Example</span></span>

<span data-ttu-id="4041a-150">En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:</span><span class="sxs-lookup"><span data-stu-id="4041a-150">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="4041a-151">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4041a-151">Configuration file</span></span>

<span data-ttu-id="4041a-152">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4041a-152">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4041a-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4041a-153">See also</span></span>

- [<span data-ttu-id="4041a-154">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4041a-154">Configuration file schema for the .NET Framework</span></span>](index.md)
