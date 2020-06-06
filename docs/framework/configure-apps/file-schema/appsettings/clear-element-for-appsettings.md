---
title: Elemento <clear> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214810"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="59583-102">Elemento \<clear> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="59583-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="59583-103">Borra la configuración personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59583-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="59583-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59583-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="59583-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="59583-105">Attributes</span></span>

<span data-ttu-id="59583-106">None</span><span class="sxs-lookup"><span data-stu-id="59583-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="59583-107">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="59583-107">Parent element</span></span>

|     | <span data-ttu-id="59583-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="59583-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="59583-109">Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="59583-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="59583-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59583-110">Child elements</span></span>

<span data-ttu-id="59583-111">None</span><span class="sxs-lookup"><span data-stu-id="59583-111">None</span></span>

## <a name="example"></a><span data-ttu-id="59583-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59583-112">Example</span></span>

<span data-ttu-id="59583-113">En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:</span><span class="sxs-lookup"><span data-stu-id="59583-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="59583-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59583-114">See also</span></span>

- [<span data-ttu-id="59583-115">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="59583-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
