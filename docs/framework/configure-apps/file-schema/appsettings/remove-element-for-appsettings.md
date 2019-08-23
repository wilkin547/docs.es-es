---
title: Elemento <remove> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 121b1c4b124ba07ff3bd312fd3832d3da592f486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921281"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="a2725-102">\<quitar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="a2725-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="a2725-103">Quita la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a2725-103">Removes custom application settings.</span></span>

<span data-ttu-id="a2725-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a2725-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="a2725-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="a2725-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="a2725-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="a2725-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a2725-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2725-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="a2725-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="a2725-108">Attribute</span></span>

|         | <span data-ttu-id="a2725-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2725-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="a2725-110">**key**</span><span class="sxs-lookup"><span data-stu-id="a2725-110">**key**</span></span> | <span data-ttu-id="a2725-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a2725-111">Required attribute.</span></span><br><br><span data-ttu-id="a2725-112">Especifica el nombre de la clave que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="a2725-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="a2725-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a2725-113">Parent element</span></span>

|     | <span data-ttu-id="a2725-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2725-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a2725-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="a2725-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="a2725-116">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2725-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a2725-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2725-117">Child elements</span></span>

<span data-ttu-id="a2725-118">None</span><span class="sxs-lookup"><span data-stu-id="a2725-118">None</span></span>

## <a name="example"></a><span data-ttu-id="a2725-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2725-119">Example</span></span>

<span data-ttu-id="a2725-120">En el ejemplo siguiente se muestra cómo quitar un valor de configuración `ApplicationName`personalizado para:</span><span class="sxs-lookup"><span data-stu-id="a2725-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="a2725-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2725-121">See also</span></span>

- [<span data-ttu-id="a2725-122">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2725-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
