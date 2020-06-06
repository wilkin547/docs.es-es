---
title: Elemento <remove> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154535"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="8f0cf-102">Elemento \<remove> para \<configSections></span><span class="sxs-lookup"><span data-stu-id="8f0cf-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="8f0cf-103">Quita una sección o grupo de sección predefinido.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="8f0cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f0cf-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="8f0cf-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="8f0cf-105">Attribute</span></span>

|           | <span data-ttu-id="8f0cf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f0cf-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8f0cf-107">**name**</span><span class="sxs-lookup"><span data-stu-id="8f0cf-107">**name**</span></span>  | <span data-ttu-id="8f0cf-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-108">Required attribute.</span></span><br><br><span data-ttu-id="8f0cf-109">Especifica el nombre de la sección o grupo de secciones que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8f0cf-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="8f0cf-110">Parent element</span></span>

|     | <span data-ttu-id="8f0cf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f0cf-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f0cf-112">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="8f0cf-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="8f0cf-113">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8f0cf-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8f0cf-114">Child elements</span></span>

<span data-ttu-id="8f0cf-115">None</span><span class="sxs-lookup"><span data-stu-id="8f0cf-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8f0cf-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f0cf-116">Remarks</span></span>

<span data-ttu-id="8f0cf-117">Puede usar el **\<remove>** elemento para quitar secciones y grupos de secciones de la aplicación que se definieron en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="8f0cf-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f0cf-118">Example</span></span>

<span data-ttu-id="8f0cf-119">En el ejemplo siguiente se muestra cómo usar el **\<remove>** elemento en un archivo de configuración de la aplicación para quitar una sección definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="8f0cf-120">El siguiente código de archivo de configuración de máquina declara la sección **\<sampleSection>** :</span><span class="sxs-lookup"><span data-stu-id="8f0cf-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="8f0cf-121">El siguiente código de archivo de configuración de la aplicación quita la **\<sampleSection>** sección.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="8f0cf-122">Después de la eliminación, la aplicación no puede recuperar la configuración en **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="8f0cf-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8f0cf-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8f0cf-123">Configuration file</span></span>

<span data-ttu-id="8f0cf-124">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f0cf-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f0cf-125">See also</span></span>

- [<span data-ttu-id="8f0cf-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f0cf-126">Configuration file schema for the .NET Framework</span></span>](index.md)
