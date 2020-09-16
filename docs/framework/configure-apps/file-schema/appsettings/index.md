---
title: Esquema de configuración de aplicaciones
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a67689bd9757f7586881fd910ef6103b1dffeab8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550454"
---
# <a name="app-settings-schema"></a><span data-ttu-id="dd4e6-102">Esquema de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dd4e6-102">App Settings schema</span></span>

<span data-ttu-id="dd4e6-103">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="dd4e6-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd4e6-104">Element</span></span> | <span data-ttu-id="dd4e6-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd4e6-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="dd4e6-106">Contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="dd4e6-107">Tiene un atributo opcional **file**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="dd4e6-108">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-108">Defines a setting.</span></span> <span data-ttu-id="dd4e6-109">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="dd4e6-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="dd4e6-110">Requiere atributos **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="dd4e6-111">Borra toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-111">Clears all settings.</span></span> <span data-ttu-id="dd4e6-112">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="dd4e6-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="dd4e6-113">No tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="dd4e6-114">Quita un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-114">Removes a setting.</span></span> <span data-ttu-id="dd4e6-115">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="dd4e6-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="dd4e6-116">Requiere un atributo **key**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="dd4e6-117">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="dd4e6-117">\<appSettings> element</span></span>

<span data-ttu-id="dd4e6-118">Este elemento contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="dd4e6-119">Define un atributo opcional para **file**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="dd4e6-120">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="dd4e6-120">\<add> element</span></span>

<span data-ttu-id="dd4e6-121">Agrega una configuración de aplicación personalizada como par nombre-valor a la colección de configuraciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="dd4e6-122">Define atributos para **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="dd4e6-123">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="dd4e6-123">\<clear> element</span></span>

<span data-ttu-id="dd4e6-124">Quita todas las referencias a la configuración de la aplicación personalizada heredada y solo permite las referencias que se agregan a los **\<add>** elementos que siguen al **\<clear>** elemento.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="dd4e6-125">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="dd4e6-126">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="dd4e6-126">\<remove> element</span></span>

<span data-ttu-id="dd4e6-127">Quita de la colección de configuraciones de la aplicación una referencia a una configuración de aplicación personalizada heredada.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="dd4e6-128">Define un atributo para **key**.</span><span class="sxs-lookup"><span data-stu-id="dd4e6-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="dd4e6-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd4e6-129">Example</span></span>

<span data-ttu-id="dd4e6-130">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="dd4e6-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="dd4e6-131">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="dd4e6-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="dd4e6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd4e6-132">See also</span></span>

- [<span data-ttu-id="dd4e6-133">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="dd4e6-133">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="dd4e6-134">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="dd4e6-134">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
