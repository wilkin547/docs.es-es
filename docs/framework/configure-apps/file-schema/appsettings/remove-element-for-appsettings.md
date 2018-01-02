---
title: '&lt;quitar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e803561ef20bb17ed7c637eb487027466b65077
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="d6e8f-102">\<Quitar > (elemento) para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="d6e8f-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="d6e8f-103">Quita la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6e8f-103">Removes custom application settings.</span></span>

<span data-ttu-id="d6e8f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d6e8f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d6e8f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d6e8f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="d6e8f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Quitar >**</span><span class="sxs-lookup"><span data-stu-id="d6e8f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d6e8f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6e8f-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="d6e8f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6e8f-108">Attribute</span></span>

|         | <span data-ttu-id="d6e8f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6e8f-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="d6e8f-110">**key**</span><span class="sxs-lookup"><span data-stu-id="d6e8f-110">**key**</span></span> | <span data-ttu-id="d6e8f-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d6e8f-111">Required attribute.</span></span><br><br><span data-ttu-id="d6e8f-112">Especifica el nombre de la clave que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="d6e8f-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="d6e8f-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="d6e8f-113">Parent element</span></span>

|     | <span data-ttu-id="d6e8f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6e8f-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d6e8f-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="d6e8f-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="d6e8f-116">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6e8f-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d6e8f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6e8f-117">Child elements</span></span>

<span data-ttu-id="d6e8f-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d6e8f-118">None</span></span>

## <a name="example"></a><span data-ttu-id="d6e8f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6e8f-119">Example</span></span>

<span data-ttu-id="d6e8f-120">En el ejemplo siguiente se muestra cómo quitar un valor de configuración personalizado para `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="d6e8f-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="d6e8f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6e8f-121">See also</span></span>

[<span data-ttu-id="d6e8f-122">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d6e8f-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
