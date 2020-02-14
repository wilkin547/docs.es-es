---
title: Elemento <add> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214803"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="3696a-102">\<agregar > elemento para \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="3696a-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="3696a-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="3696a-103">Adds a custom application setting.</span></span>

<span data-ttu-id="3696a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3696a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3696a-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="3696a-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="3696a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<agregar >**</span><span class="sxs-lookup"><span data-stu-id="3696a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3696a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3696a-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="3696a-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3696a-108">Attributes</span></span>

|           | <span data-ttu-id="3696a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3696a-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="3696a-110">**key**</span><span class="sxs-lookup"><span data-stu-id="3696a-110">**key**</span></span>   | <span data-ttu-id="3696a-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3696a-111">Required attribute.</span></span><br><br><span data-ttu-id="3696a-112">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="3696a-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="3696a-113">**value**</span><span class="sxs-lookup"><span data-stu-id="3696a-113">**value**</span></span> | <span data-ttu-id="3696a-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3696a-114">Required attribute.</span></span><br><br><span data-ttu-id="3696a-115">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="3696a-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="3696a-116">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="3696a-116">Parent element</span></span>

|     | <span data-ttu-id="3696a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3696a-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3696a-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="3696a-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="3696a-119">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3696a-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3696a-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3696a-120">Child elements</span></span>

<span data-ttu-id="3696a-121">None</span><span class="sxs-lookup"><span data-stu-id="3696a-121">None</span></span>

## <a name="example"></a><span data-ttu-id="3696a-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3696a-122">Example</span></span>

<span data-ttu-id="3696a-123">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3696a-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="3696a-124">En el ejemplo siguiente se usa el elemento `<add>` para definir dos valores de compatibilidad en una aplicación ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="3696a-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3696a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3696a-125">See also</span></span>

- [<span data-ttu-id="3696a-126">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3696a-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
