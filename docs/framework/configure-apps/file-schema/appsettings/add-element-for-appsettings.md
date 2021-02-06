---
description: 'Más información sobre: <add> elemento para <appSettings>'
title: Elemento <add> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: f10ffe517b3b25543bc7baed0c7d2af13f48ab02
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652892"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="cc3aa-103">Elemento \<add> para \<appSettings></span><span class="sxs-lookup"><span data-stu-id="cc3aa-103">\<add> element for \<appSettings></span></span>

<span data-ttu-id="cc3aa-104">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-104">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="cc3aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc3aa-105">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="cc3aa-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc3aa-106">Attributes</span></span>

|           | <span data-ttu-id="cc3aa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc3aa-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="cc3aa-108">**key**</span><span class="sxs-lookup"><span data-stu-id="cc3aa-108">**key**</span></span>   | <span data-ttu-id="cc3aa-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-109">Required attribute.</span></span><br><br><span data-ttu-id="cc3aa-110">Especifica el nombre de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-110">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="cc3aa-111">**value**</span><span class="sxs-lookup"><span data-stu-id="cc3aa-111">**value**</span></span> | <span data-ttu-id="cc3aa-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-112">Required attribute.</span></span><br><br><span data-ttu-id="cc3aa-113">Especifica el valor de la clave que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-113">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="cc3aa-114">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="cc3aa-114">Parent element</span></span>

|     | <span data-ttu-id="cc3aa-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc3aa-115">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="cc3aa-116">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc3aa-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cc3aa-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc3aa-117">Child elements</span></span>

<span data-ttu-id="cc3aa-118">None</span><span class="sxs-lookup"><span data-stu-id="cc3aa-118">None</span></span>

## <a name="example"></a><span data-ttu-id="cc3aa-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc3aa-119">Example</span></span>

<span data-ttu-id="cc3aa-120">En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="cc3aa-120">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="cc3aa-121">En el ejemplo siguiente se usa el `<add>` elemento para definir dos valores de compatibilidad en una aplicación ASP.net:</span><span class="sxs-lookup"><span data-stu-id="cc3aa-121">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="cc3aa-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc3aa-122">See also</span></span>

- [<span data-ttu-id="cc3aa-123">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc3aa-123">Configuration file schema for the .NET Framework</span></span>](../index.md)
