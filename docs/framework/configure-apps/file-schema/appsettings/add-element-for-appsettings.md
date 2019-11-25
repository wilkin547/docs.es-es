---
title: Elemento <add> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865c693bf8f23bf050064ac097b72aa6fa3b371e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088743"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="25b5c-102">\<agregar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="25b5c-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="25b5c-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="25b5c-103">Adds a custom application setting.</span></span>

<span data-ttu-id="25b5c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25b5c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25b5c-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="25b5c-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="25b5c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<agregar >**</span><span class="sxs-lookup"><span data-stu-id="25b5c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="25b5c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25b5c-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="25b5c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="25b5c-108">Attributes</span></span>

|           | <span data-ttu-id="25b5c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="25b5c-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="25b5c-110">**key**</span><span class="sxs-lookup"><span data-stu-id="25b5c-110">**key**</span></span>   | <span data-ttu-id="25b5c-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="25b5c-111">Required attribute.</span></span><br><br><span data-ttu-id="25b5c-112">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="25b5c-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="25b5c-113">**valor**</span><span class="sxs-lookup"><span data-stu-id="25b5c-113">**value**</span></span> | <span data-ttu-id="25b5c-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="25b5c-114">Required attribute.</span></span><br><br><span data-ttu-id="25b5c-115">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="25b5c-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="25b5c-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="25b5c-116">Parent element</span></span>

|     | <span data-ttu-id="25b5c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="25b5c-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="25b5c-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="25b5c-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="25b5c-119">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="25b5c-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="25b5c-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="25b5c-120">Child elements</span></span>

<span data-ttu-id="25b5c-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="25b5c-121">None</span></span>

## <a name="example"></a><span data-ttu-id="25b5c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25b5c-122">Example</span></span>

<span data-ttu-id="25b5c-123">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="25b5c-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="25b5c-124">En el ejemplo siguiente se usa el elemento `<add>` para definir dos valores de compatibilidad en una aplicación ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="25b5c-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="25b5c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="25b5c-125">See also</span></span>

- [<span data-ttu-id="25b5c-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="25b5c-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
