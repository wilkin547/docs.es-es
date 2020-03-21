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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154535"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="7a73e-102">\<eliminar> \<elemento para configSections></span><span class="sxs-lookup"><span data-stu-id="7a73e-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="7a73e-103">Quita una sección o un grupo de secciones predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7a73e-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="7a73e-104">[**\<configuración>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a73e-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="7a73e-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="7a73e-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="7a73e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="7a73e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7a73e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a73e-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="7a73e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="7a73e-108">Attribute</span></span>

|           | <span data-ttu-id="7a73e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a73e-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7a73e-110">**nombre**</span><span class="sxs-lookup"><span data-stu-id="7a73e-110">**name**</span></span>  | <span data-ttu-id="7a73e-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7a73e-111">Required attribute.</span></span><br><br><span data-ttu-id="7a73e-112">Especifica el nombre de la sección o grupo de secciones que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="7a73e-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7a73e-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="7a73e-113">Parent element</span></span>

|     | <span data-ttu-id="7a73e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a73e-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a73e-115">\*\* \<configSections>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="7a73e-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="7a73e-116">Contiene declaraciones de sección de configuración y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7a73e-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7a73e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a73e-117">Child elements</span></span>

<span data-ttu-id="7a73e-118">None</span><span class="sxs-lookup"><span data-stu-id="7a73e-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7a73e-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a73e-119">Remarks</span></span>

<span data-ttu-id="7a73e-120">Puede usar \*\* \<\*\* el elemento remove>para quitar secciones y grupos de secciones de la aplicación que se definieron en un nivel superior en la jerarquía de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="7a73e-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="7a73e-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a73e-121">Example</span></span>

<span data-ttu-id="7a73e-122">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el elemento remove>en un archivo de configuración de aplicación para quitar una sección definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="7a73e-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="7a73e-123">El siguiente código de archivo de configuración del equipo declara la sección \*\* \<sampleSection>: \*\*</span><span class="sxs-lookup"><span data-stu-id="7a73e-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="7a73e-124">El siguiente código de archivo \*\* \<\*\* de configuración de la aplicación quita la sección sampleSection>.</span><span class="sxs-lookup"><span data-stu-id="7a73e-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="7a73e-125">Después de la eliminación, la aplicación no puede recuperar la configuración de \*\* \<sampleSection>\*\*.</span><span class="sxs-lookup"><span data-stu-id="7a73e-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7a73e-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7a73e-126">Configuration file</span></span>

<span data-ttu-id="7a73e-127">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a73e-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a73e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a73e-128">See also</span></span>

- [<span data-ttu-id="7a73e-129">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a73e-129">Configuration file schema for the .NET Framework</span></span>](index.md)
