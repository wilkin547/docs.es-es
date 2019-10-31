---
title: Esquema de configuración de aplicaciones
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b931b76aa09b3f62fbd799990975268af4f7293
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119218"
---
# <a name="app-settings-schema"></a><span data-ttu-id="c81af-102">Esquema de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c81af-102">App Settings schema</span></span>

<span data-ttu-id="c81af-103">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c81af-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="c81af-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c81af-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="c81af-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c81af-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="c81af-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="c81af-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="c81af-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="c81af-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="c81af-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="c81af-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="c81af-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="c81af-109">Element</span></span> | <span data-ttu-id="c81af-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c81af-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="c81af-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="c81af-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="c81af-112">Contiene etiquetas **\<add>** , **\<clear>** y **\<remove>** para controlar la configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c81af-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c81af-113">Tiene un atributo opcional **file**.</span><span class="sxs-lookup"><span data-stu-id="c81af-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="c81af-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="c81af-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="c81af-115">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="c81af-115">Defines a setting.</span></span> <span data-ttu-id="c81af-116">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c81af-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c81af-117">Requiere atributos **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="c81af-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="c81af-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="c81af-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="c81af-119">Borra toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="c81af-119">Clears all settings.</span></span> <span data-ttu-id="c81af-120">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c81af-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c81af-121">No tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="c81af-121">Has no attributes.</span></span> |
| [<span data-ttu-id="c81af-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="c81af-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="c81af-123">Quita un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="c81af-123">Removes a setting.</span></span> <span data-ttu-id="c81af-124">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="c81af-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c81af-125">Requiere un atributo **key**.</span><span class="sxs-lookup"><span data-stu-id="c81af-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="c81af-126">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="c81af-126">\<appSettings> element</span></span>

<span data-ttu-id="c81af-127">Este elemento contiene etiquetas **\<add>** , **\<clear>** y **\<remove>** para controlar la configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c81af-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c81af-128">Define un atributo opcional para **file**.</span><span class="sxs-lookup"><span data-stu-id="c81af-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="c81af-129">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="c81af-129">\<add> element</span></span>

<span data-ttu-id="c81af-130">Agrega una configuración de aplicación personalizada como par nombre-valor a la colección de configuraciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c81af-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="c81af-131">Define atributos para **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="c81af-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="c81af-132">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="c81af-132">\<clear> element</span></span>

<span data-ttu-id="c81af-133">Quita todas las referencias a la configuración de aplicación personalizada heredada y solo permite las referencias que se agregan mediante los elementos **\<add>** que siguen al elemento **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="c81af-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="c81af-134">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="c81af-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="c81af-135">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="c81af-135">\<remove> element</span></span>

<span data-ttu-id="c81af-136">Quita de la colección de configuraciones de la aplicación una referencia a una configuración de aplicación personalizada heredada.</span><span class="sxs-lookup"><span data-stu-id="c81af-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="c81af-137">Define un atributo para **key**.</span><span class="sxs-lookup"><span data-stu-id="c81af-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="c81af-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c81af-138">Example</span></span>

<span data-ttu-id="c81af-139">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="c81af-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="c81af-140">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c81af-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c81af-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="c81af-141">See also</span></span>

- [<span data-ttu-id="c81af-142">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c81af-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="c81af-143">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c81af-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
