---
title: '&lt;agregar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bcdac76528e7a8b07b56b6fd1d827c3c8072c371
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46529585"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="a9df3-102">\<Agregar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="a9df3-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="a9df3-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9df3-103">Adds a custom application setting.</span></span>

<span data-ttu-id="a9df3-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a9df3-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a9df3-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="a9df3-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="a9df3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="a9df3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a9df3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9df3-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="a9df3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9df3-108">Attributes</span></span>

|           | <span data-ttu-id="a9df3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9df3-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a9df3-110">**key**</span><span class="sxs-lookup"><span data-stu-id="a9df3-110">**key**</span></span>   | <span data-ttu-id="a9df3-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a9df3-111">Required attribute.</span></span><br><br><span data-ttu-id="a9df3-112">Especifica el nombre de la clave para agregar.</span><span class="sxs-lookup"><span data-stu-id="a9df3-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="a9df3-113">**value**</span><span class="sxs-lookup"><span data-stu-id="a9df3-113">**value**</span></span> | <span data-ttu-id="a9df3-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a9df3-114">Required attribute.</span></span><br><br><span data-ttu-id="a9df3-115">Especifica el valor de la clave para agregar.</span><span class="sxs-lookup"><span data-stu-id="a9df3-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a9df3-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a9df3-116">Parent element</span></span>

|     | <span data-ttu-id="a9df3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9df3-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a9df3-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="a9df3-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="a9df3-119">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9df3-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a9df3-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9df3-120">Child elements</span></span>

<span data-ttu-id="a9df3-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a9df3-121">None</span></span>

## <a name="example"></a><span data-ttu-id="a9df3-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9df3-122">Example</span></span>

<span data-ttu-id="a9df3-123">El ejemplo siguiente muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a9df3-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="a9df3-124">En el ejemplo siguiente se usa el `<add>` elemento para definir dos configuraciones de compatibilidad de una aplicación ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="a9df3-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="a9df3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9df3-125">See also</span></span>

[<span data-ttu-id="a9df3-126">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9df3-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
