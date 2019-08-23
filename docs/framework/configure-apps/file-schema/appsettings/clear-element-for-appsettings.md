---
title: Elemento <clear> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921308"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="f9c4e-102">\<borrar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="f9c4e-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="f9c4e-103">Borra la configuración personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-103">Clears custom application settings.</span></span>

<span data-ttu-id="f9c4e-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f9c4e-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="f9c4e-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f9c4e-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="f9c4e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="f9c4e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f9c4e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9c4e-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="f9c4e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9c4e-108">Attributes</span></span>

<span data-ttu-id="f9c4e-109">None</span><span class="sxs-lookup"><span data-stu-id="f9c4e-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="f9c4e-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="f9c4e-110">Parent element</span></span>

|     | <span data-ttu-id="f9c4e-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f9c4e-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f9c4e-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="f9c4e-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="f9c4e-113">Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f9c4e-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f9c4e-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9c4e-114">Child elements</span></span>

<span data-ttu-id="f9c4e-115">None</span><span class="sxs-lookup"><span data-stu-id="f9c4e-115">None</span></span>

## <a name="example"></a><span data-ttu-id="f9c4e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9c4e-116">Example</span></span>

<span data-ttu-id="f9c4e-117">En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:</span><span class="sxs-lookup"><span data-stu-id="f9c4e-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="f9c4e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9c4e-118">See also</span></span>

- [<span data-ttu-id="f9c4e-119">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9c4e-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
