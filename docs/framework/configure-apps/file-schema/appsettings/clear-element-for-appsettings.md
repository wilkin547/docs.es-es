---
title: '&lt;Borrar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bc52e3149c213925ea64a8421ee65befeea4161e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184223"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="ce8cc-102">\<Borrar > (elemento) para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="ce8cc-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="ce8cc-103">Borra la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="ce8cc-103">Clears custom application settings.</span></span>

<span data-ttu-id="ce8cc-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ce8cc-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ce8cc-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ce8cc-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="ce8cc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Borrar >**</span><span class="sxs-lookup"><span data-stu-id="ce8cc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ce8cc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce8cc-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="ce8cc-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce8cc-108">Attributes</span></span>

<span data-ttu-id="ce8cc-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ce8cc-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ce8cc-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="ce8cc-110">Parent element</span></span>

|     | <span data-ttu-id="ce8cc-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce8cc-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ce8cc-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="ce8cc-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="ce8cc-113">Contiene la configuración de aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="ce8cc-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ce8cc-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce8cc-114">Child elements</span></span>

<span data-ttu-id="ce8cc-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ce8cc-115">None</span></span>

## <a name="example"></a><span data-ttu-id="ce8cc-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce8cc-116">Example</span></span>

<span data-ttu-id="ce8cc-117">El ejemplo siguiente muestra cómo borrar la configuración personalizada:</span><span class="sxs-lookup"><span data-stu-id="ce8cc-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="ce8cc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce8cc-118">See also</span></span>

- [<span data-ttu-id="ce8cc-119">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ce8cc-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
