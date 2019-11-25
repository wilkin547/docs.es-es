---
title: Elemento <remove> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efc7208aa51cbf6abdb2fe151d48071c0aa95b5c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089044"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="f455d-102">\<quitar > elemento de \<configSections ></span><span class="sxs-lookup"><span data-stu-id="f455d-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="f455d-103">Quita una sección o grupo de sección predefinido.</span><span class="sxs-lookup"><span data-stu-id="f455d-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="f455d-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f455d-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="f455d-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="f455d-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="f455d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**</span><span class="sxs-lookup"><span data-stu-id="f455d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f455d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f455d-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="f455d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f455d-108">Attribute</span></span>

|           | <span data-ttu-id="f455d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f455d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f455d-110">**name**</span><span class="sxs-lookup"><span data-stu-id="f455d-110">**name**</span></span>  | <span data-ttu-id="f455d-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f455d-111">Required attribute.</span></span><br><br><span data-ttu-id="f455d-112">Especifica el nombre de la sección o grupo de secciones que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="f455d-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f455d-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="f455d-113">Parent element</span></span>

|     | <span data-ttu-id="f455d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f455d-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f455d-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="f455d-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="f455d-116">Contiene la sección de configuración y las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f455d-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f455d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f455d-117">Child elements</span></span>

<span data-ttu-id="f455d-118">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f455d-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f455d-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f455d-119">Remarks</span></span>

<span data-ttu-id="f455d-120">Puede usar el elemento **\<remove >** para quitar secciones y grupos de secciones de la aplicación que se definieron en un nivel superior en la jerarquía del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f455d-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="f455d-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f455d-121">Example</span></span>

<span data-ttu-id="f455d-122">En el ejemplo siguiente se muestra cómo usar el elemento **\<remove >** en un archivo de configuración de la aplicación para quitar una sección definida previamente en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="f455d-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="f455d-123">El siguiente código de archivo de configuración de máquina declara la sección **\<sampleSection >** :</span><span class="sxs-lookup"><span data-stu-id="f455d-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="f455d-124">El siguiente código de archivo de configuración de la aplicación quita la sección **\<sampleSection >** .</span><span class="sxs-lookup"><span data-stu-id="f455d-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="f455d-125">Después de la eliminación, la aplicación no puede recuperar la configuración en **\<> sampleSection**.</span><span class="sxs-lookup"><span data-stu-id="f455d-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f455d-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f455d-126">Configuration file</span></span>

<span data-ttu-id="f455d-127">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f455d-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f455d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f455d-128">See also</span></span>

- [<span data-ttu-id="f455d-129">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f455d-129">Configuration file schema for the .NET Framework</span></span>](index.md)
