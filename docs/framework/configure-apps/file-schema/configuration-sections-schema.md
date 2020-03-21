---
title: Esquema de secciones de configuración
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155328"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="9a57c-102">Esquema de secciones de configuración</span><span class="sxs-lookup"><span data-stu-id="9a57c-102">Configuration sections schema</span></span>

<span data-ttu-id="9a57c-103">El esquema de secciones de configuración contiene elementos que definen la configuración personalizada en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9a57c-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="9a57c-104">Para obtener información general sobre los archivos de configuración y los esquemas, vea Esquema de archivos de configuración [para .NET Framework](index.md).</span><span class="sxs-lookup"><span data-stu-id="9a57c-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="9a57c-105">[**\<configuración>** ](configuration-element.md) 
 
 [\*\* \< \*\*](clear-element-for-configsections.md) 
 [\*\* \< \*\*](remove-element-for-configsections.md) 
 [\*\* \< \*\*](section-element.md) 
 [\*\* \<\*\*](sectiongroup-element-for-configsections.md) configSections>borrar>eliminar>sección>sectionGroup>[\*\* \< \*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="9a57c-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="9a57c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a57c-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9a57c-107">>transparente para \*\* \<\*\* \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="9a57c-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="9a57c-108">Borra todas las secciones y grupos de secciones definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9a57c-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="9a57c-109">**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="9a57c-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="9a57c-110">Borra todas las secciones y grupos de secciones definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9a57c-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="9a57c-111">**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="9a57c-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="9a57c-112">Contiene declaraciones de sección de configuración y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9a57c-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="9a57c-113">eliminar>para \*\* \<\*\* \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="9a57c-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="9a57c-114">Quita una sección o un grupo de secciones predefinidos.</span><span class="sxs-lookup"><span data-stu-id="9a57c-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="9a57c-115">sección>para \*\* \<configSections>\*\* y \*\* \<\*\* \*\* \<sectionGroup>\*\*</span><span class="sxs-lookup"><span data-stu-id="9a57c-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="9a57c-116">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="9a57c-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="9a57c-117">sectionGroup>para \*\* \<\*\* \*\* \<configSections>\*\*</span><span class="sxs-lookup"><span data-stu-id="9a57c-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="9a57c-118">Define un espacio de nombres para las secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="9a57c-118">Defines a namespace for configuration sections.</span></span> |
