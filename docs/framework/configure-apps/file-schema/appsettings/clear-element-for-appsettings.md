---
title: '&lt;Borrar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54479cab9abc2c1a107cd055341404c0fe1308fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="338ed-102">\<Borrar > (elemento) para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="338ed-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="338ed-103">Borra la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="338ed-103">Clears custom application settings.</span></span>

<span data-ttu-id="338ed-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="338ed-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="338ed-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="338ed-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="338ed-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Borrar >**</span><span class="sxs-lookup"><span data-stu-id="338ed-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="338ed-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="338ed-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="338ed-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="338ed-108">Attributes</span></span>

<span data-ttu-id="338ed-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="338ed-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="338ed-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="338ed-110">Parent element</span></span>

|     | <span data-ttu-id="338ed-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="338ed-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="338ed-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="338ed-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="338ed-113">Contiene la configuración de aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="338ed-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="338ed-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="338ed-114">Child elements</span></span>

<span data-ttu-id="338ed-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="338ed-115">None</span></span>

## <a name="example"></a><span data-ttu-id="338ed-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="338ed-116">Example</span></span>

<span data-ttu-id="338ed-117">En el ejemplo siguiente se muestra cómo borrar valores de configuración personalizados:</span><span class="sxs-lookup"><span data-stu-id="338ed-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="338ed-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="338ed-118">See also</span></span>

[<span data-ttu-id="338ed-119">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="338ed-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
