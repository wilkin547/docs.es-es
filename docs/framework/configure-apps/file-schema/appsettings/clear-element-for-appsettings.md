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
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214810"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="3b3ce-102">\<borrar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="3b3ce-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="3b3ce-103">Borra la configuración personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b3ce-103">Clears custom application settings.</span></span>

<span data-ttu-id="3b3ce-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3b3ce-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3b3ce-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="3b3ce-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="3b3ce-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="3b3ce-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3b3ce-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b3ce-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="3b3ce-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b3ce-108">Attributes</span></span>

<span data-ttu-id="3b3ce-109">None</span><span class="sxs-lookup"><span data-stu-id="3b3ce-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="3b3ce-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="3b3ce-110">Parent element</span></span>

|     | <span data-ttu-id="3b3ce-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b3ce-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3b3ce-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="3b3ce-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="3b3ce-113">Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="3b3ce-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3b3ce-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b3ce-114">Child elements</span></span>

<span data-ttu-id="3b3ce-115">None</span><span class="sxs-lookup"><span data-stu-id="3b3ce-115">None</span></span>

## <a name="example"></a><span data-ttu-id="3b3ce-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b3ce-116">Example</span></span>

<span data-ttu-id="3b3ce-117">En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:</span><span class="sxs-lookup"><span data-stu-id="3b3ce-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3b3ce-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b3ce-118">See also</span></span>

- [<span data-ttu-id="3b3ce-119">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3b3ce-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
