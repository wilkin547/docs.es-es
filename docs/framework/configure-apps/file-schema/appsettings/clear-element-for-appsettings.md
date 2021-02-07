---
description: 'Más información sobre: <clear> elemento para <appSettings>'
title: Elemento <clear> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 88c6a02441c038619cb74947c024de7712189915
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699342"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="d5e28-103">Elemento \<clear> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="d5e28-103">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="d5e28-104">Borra la configuración personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5e28-104">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="d5e28-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5e28-105">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="d5e28-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5e28-106">Attributes</span></span>

<span data-ttu-id="d5e28-107">None</span><span class="sxs-lookup"><span data-stu-id="d5e28-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d5e28-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="d5e28-108">Parent element</span></span>

|     | <span data-ttu-id="d5e28-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5e28-109">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="d5e28-110">Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="d5e28-110">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d5e28-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5e28-111">Child elements</span></span>

<span data-ttu-id="d5e28-112">None</span><span class="sxs-lookup"><span data-stu-id="d5e28-112">None</span></span>

## <a name="example"></a><span data-ttu-id="d5e28-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5e28-113">Example</span></span>

<span data-ttu-id="d5e28-114">En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:</span><span class="sxs-lookup"><span data-stu-id="d5e28-114">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="d5e28-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5e28-115">See also</span></span>

- [<span data-ttu-id="d5e28-116">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5e28-116">Configuration file schema for the .NET Framework</span></span>](../index.md)
