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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214803"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="745db-102">Elemento \<add> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="745db-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="745db-103">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="745db-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="745db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="745db-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="745db-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="745db-105">Attributes</span></span>

|           | <span data-ttu-id="745db-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="745db-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="745db-107">**key**</span><span class="sxs-lookup"><span data-stu-id="745db-107">**key**</span></span>   | <span data-ttu-id="745db-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="745db-108">Required attribute.</span></span><br><br><span data-ttu-id="745db-109">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="745db-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="745db-110">**value**</span><span class="sxs-lookup"><span data-stu-id="745db-110">**value**</span></span> | <span data-ttu-id="745db-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="745db-111">Required attribute.</span></span><br><br><span data-ttu-id="745db-112">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="745db-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="745db-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="745db-113">Parent element</span></span>

|     | <span data-ttu-id="745db-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="745db-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="745db-115">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="745db-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="745db-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="745db-116">Child elements</span></span>

<span data-ttu-id="745db-117">None</span><span class="sxs-lookup"><span data-stu-id="745db-117">None</span></span>

## <a name="example"></a><span data-ttu-id="745db-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="745db-118">Example</span></span>

<span data-ttu-id="745db-119">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="745db-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="745db-120">En el ejemplo siguiente se usa el `<add>` elemento para definir dos valores de compatibilidad en una aplicación ASP.net:</span><span class="sxs-lookup"><span data-stu-id="745db-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="745db-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="745db-121">See also</span></span>

- [<span data-ttu-id="745db-122">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="745db-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
