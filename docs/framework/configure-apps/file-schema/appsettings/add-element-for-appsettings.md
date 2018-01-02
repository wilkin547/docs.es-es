---
title: '&lt;agregar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d080a7c63ddda0577e66d2e7ddd433c7fd5fdbd1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="78229-102">\<Agregar > (elemento) para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="78229-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="78229-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="78229-103">Adds a custom application setting.</span></span>

<span data-ttu-id="78229-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="78229-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="78229-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="78229-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="78229-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="78229-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="78229-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78229-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="78229-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="78229-108">Attributes</span></span>

|           | <span data-ttu-id="78229-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="78229-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="78229-110">**key**</span><span class="sxs-lookup"><span data-stu-id="78229-110">**key**</span></span>   | <span data-ttu-id="78229-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="78229-111">Required attribute.</span></span><br><br><span data-ttu-id="78229-112">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="78229-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="78229-113">**value**</span><span class="sxs-lookup"><span data-stu-id="78229-113">**value**</span></span> | <span data-ttu-id="78229-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="78229-114">Required attribute.</span></span><br><br><span data-ttu-id="78229-115">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="78229-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="78229-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="78229-116">Parent element</span></span>

|     | <span data-ttu-id="78229-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="78229-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78229-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="78229-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="78229-119">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="78229-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="78229-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78229-120">Child elements</span></span>

<span data-ttu-id="78229-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="78229-121">None</span></span>

## <a name="example"></a><span data-ttu-id="78229-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78229-122">Example</span></span>

<span data-ttu-id="78229-123">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de aplicación:</span><span class="sxs-lookup"><span data-stu-id="78229-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="78229-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="78229-124">See also</span></span>

[<span data-ttu-id="78229-125">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78229-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
