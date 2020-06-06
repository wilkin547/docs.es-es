---
title: Elemento <remove> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215493"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="182a9-102">Elemento \<remove> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="182a9-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="182a9-103">Quita la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="182a9-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="182a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="182a9-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="182a9-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="182a9-105">Attribute</span></span>

|         | <span data-ttu-id="182a9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="182a9-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="182a9-107">**key**</span><span class="sxs-lookup"><span data-stu-id="182a9-107">**key**</span></span> | <span data-ttu-id="182a9-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="182a9-108">Required attribute.</span></span><br><br><span data-ttu-id="182a9-109">Especifica el nombre de la clave que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="182a9-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="182a9-110">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="182a9-110">Parent element</span></span>

|     | <span data-ttu-id="182a9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="182a9-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="182a9-112">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="182a9-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="182a9-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="182a9-113">Child elements</span></span>

<span data-ttu-id="182a9-114">None</span><span class="sxs-lookup"><span data-stu-id="182a9-114">None</span></span>

## <a name="example"></a><span data-ttu-id="182a9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="182a9-115">Example</span></span>

<span data-ttu-id="182a9-116">En el ejemplo siguiente se muestra cómo quitar un valor de configuración personalizado para `ApplicationName` :</span><span class="sxs-lookup"><span data-stu-id="182a9-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="182a9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="182a9-117">See also</span></span>

- [<span data-ttu-id="182a9-118">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="182a9-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
