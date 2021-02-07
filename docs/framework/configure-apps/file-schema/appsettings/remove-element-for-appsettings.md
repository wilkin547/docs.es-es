---
description: 'Más información sobre: <remove> elemento para <appSettings>'
title: Elemento <remove> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: a67003d310377ee4b896843003306201353dae91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699277"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="5520b-103">Elemento \<remove> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="5520b-103">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="5520b-104">Quita la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="5520b-104">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="5520b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5520b-105">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="5520b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="5520b-106">Attribute</span></span>

|         | <span data-ttu-id="5520b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5520b-107">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="5520b-108">**key**</span><span class="sxs-lookup"><span data-stu-id="5520b-108">**key**</span></span> | <span data-ttu-id="5520b-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5520b-109">Required attribute.</span></span><br><br><span data-ttu-id="5520b-110">Especifica el nombre de la clave que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="5520b-110">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="5520b-111">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="5520b-111">Parent element</span></span>

|     | <span data-ttu-id="5520b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5520b-112">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="5520b-113">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5520b-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5520b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5520b-114">Child elements</span></span>

<span data-ttu-id="5520b-115">None</span><span class="sxs-lookup"><span data-stu-id="5520b-115">None</span></span>

## <a name="example"></a><span data-ttu-id="5520b-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5520b-116">Example</span></span>

<span data-ttu-id="5520b-117">En el ejemplo siguiente se muestra cómo quitar un valor de configuración personalizado para `ApplicationName` :</span><span class="sxs-lookup"><span data-stu-id="5520b-117">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="5520b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5520b-118">See also</span></span>

- [<span data-ttu-id="5520b-119">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5520b-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
