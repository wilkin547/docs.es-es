---
title: Elemento <add> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 594ba4f289012e775e93acba98056b60bdd94cbd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927746"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="453fa-102">\<Agregar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="453fa-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="453fa-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="453fa-103">Adds a custom application setting.</span></span>

<span data-ttu-id="453fa-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="453fa-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="453fa-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="453fa-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="453fa-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="453fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="453fa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="453fa-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="453fa-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="453fa-108">Attributes</span></span>

|           | <span data-ttu-id="453fa-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="453fa-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="453fa-110">**key**</span><span class="sxs-lookup"><span data-stu-id="453fa-110">**key**</span></span>   | <span data-ttu-id="453fa-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="453fa-111">Required attribute.</span></span><br><br><span data-ttu-id="453fa-112">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="453fa-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="453fa-113">**value**</span><span class="sxs-lookup"><span data-stu-id="453fa-113">**value**</span></span> | <span data-ttu-id="453fa-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="453fa-114">Required attribute.</span></span><br><br><span data-ttu-id="453fa-115">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="453fa-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="453fa-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="453fa-116">Parent element</span></span>

|     | <span data-ttu-id="453fa-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="453fa-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="453fa-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="453fa-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="453fa-119">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="453fa-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="453fa-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="453fa-120">Child elements</span></span>

<span data-ttu-id="453fa-121">None</span><span class="sxs-lookup"><span data-stu-id="453fa-121">None</span></span>

## <a name="example"></a><span data-ttu-id="453fa-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="453fa-122">Example</span></span>

<span data-ttu-id="453fa-123">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="453fa-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="453fa-124">En el ejemplo siguiente se `<add>` usa el elemento para definir dos valores de compatibilidad en una aplicación ASP.net:</span><span class="sxs-lookup"><span data-stu-id="453fa-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="453fa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="453fa-125">See also</span></span>

- [<span data-ttu-id="453fa-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="453fa-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
