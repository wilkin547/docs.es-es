---
title: Elemento <clear> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088736"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="42131-102">\<borrar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="42131-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="42131-103">Borra la configuración personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42131-103">Clears custom application settings.</span></span>

<span data-ttu-id="42131-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="42131-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="42131-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="42131-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="42131-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="42131-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="42131-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42131-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="42131-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="42131-108">Attributes</span></span>

<span data-ttu-id="42131-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="42131-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="42131-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="42131-110">Parent element</span></span>

|     | <span data-ttu-id="42131-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="42131-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="42131-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="42131-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="42131-113">Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="42131-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="42131-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42131-114">Child elements</span></span>

<span data-ttu-id="42131-115">Ninguno</span><span class="sxs-lookup"><span data-stu-id="42131-115">None</span></span>

## <a name="example"></a><span data-ttu-id="42131-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42131-116">Example</span></span>

<span data-ttu-id="42131-117">En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:</span><span class="sxs-lookup"><span data-stu-id="42131-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="42131-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42131-118">See also</span></span>

- [<span data-ttu-id="42131-119">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="42131-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
