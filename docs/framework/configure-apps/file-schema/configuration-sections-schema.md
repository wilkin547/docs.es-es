---
title: "Esquema de secciones de configuración"
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c668cf3d2f2c0bcffda185cea01edfb9e55c6d6c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="3370c-102">Esquema de secciones de configuración</span><span class="sxs-lookup"><span data-stu-id="3370c-102">Configuration sections schema</span></span>

<span data-ttu-id="3370c-103">El esquema de secciones de configuración contiene elementos que definen los valores personalizados en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="3370c-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="3370c-104">Para obtener información general sobre los archivos de configuración y los esquemas, vea [esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="3370c-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="3370c-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3370c-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="3370c-106">[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3370c-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="3370c-107">[**\<Borrar >**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="3370c-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="3370c-108">[**\<Quitar >**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="3370c-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="3370c-109">[**\<sección >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="3370c-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="3370c-110">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="3370c-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="3370c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3370c-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3370c-112">**\<Borrar >** para  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="3370c-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="3370c-113">Borra todas las secciones definidas anteriormente y grupos de sección.</span><span class="sxs-lookup"><span data-stu-id="3370c-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="3370c-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="3370c-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="3370c-115">Borra todas las secciones definidas anteriormente y grupos de sección.</span><span class="sxs-lookup"><span data-stu-id="3370c-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="3370c-116">**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="3370c-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="3370c-117">Contiene las declaraciones de espacio de nombres y la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="3370c-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="3370c-118">**\<Quitar >** para  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="3370c-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="3370c-119">Quita una sección predefinido o un grupo de sección.</span><span class="sxs-lookup"><span data-stu-id="3370c-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="3370c-120">**\<sección >** para  **\<configSections >** y  **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="3370c-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="3370c-121">Contiene una declaración de sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="3370c-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="3370c-122">**\<sectionGroup >** para  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="3370c-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="3370c-123">Define un espacio de nombres de secciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="3370c-123">Defines a namespace for configuration sections.</span></span> |
