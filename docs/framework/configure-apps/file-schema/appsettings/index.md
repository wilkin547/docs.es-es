---
description: 'Más información sobre: esquema de configuración de aplicaciones'
title: Esquema de configuración de aplicaciones
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a98a60b0470e0fa2c03313f25de9b310f5fce785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699355"
---
# <a name="app-settings-schema"></a><span data-ttu-id="86772-103">Esquema de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="86772-103">App Settings schema</span></span>

<span data-ttu-id="86772-104">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="86772-104">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="86772-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="86772-105">Element</span></span> | <span data-ttu-id="86772-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="86772-106">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="86772-107">Contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86772-107">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="86772-108">Tiene un atributo opcional **file**.</span><span class="sxs-lookup"><span data-stu-id="86772-108">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="86772-109">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="86772-109">Defines a setting.</span></span> <span data-ttu-id="86772-110">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="86772-110">Child of **\<appSettings>**.</span></span> <span data-ttu-id="86772-111">Requiere atributos **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="86772-111">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="86772-112">Borra toda la configuración.</span><span class="sxs-lookup"><span data-stu-id="86772-112">Clears all settings.</span></span> <span data-ttu-id="86772-113">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="86772-113">Child of **\<appSettings>**.</span></span> <span data-ttu-id="86772-114">No tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="86772-114">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="86772-115">Quita un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="86772-115">Removes a setting.</span></span> <span data-ttu-id="86772-116">Elemento secundario de **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="86772-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="86772-117">Requiere un atributo **key**.</span><span class="sxs-lookup"><span data-stu-id="86772-117">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="86772-118">Elemento \<appSettings></span><span class="sxs-lookup"><span data-stu-id="86772-118">\<appSettings> element</span></span>

<span data-ttu-id="86772-119">Este elemento contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86772-119">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="86772-120">Define un atributo opcional para **file**.</span><span class="sxs-lookup"><span data-stu-id="86772-120">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="86772-121">Elemento \<add></span><span class="sxs-lookup"><span data-stu-id="86772-121">\<add> element</span></span>

<span data-ttu-id="86772-122">Agrega una configuración de aplicación personalizada como par nombre-valor a la colección de configuraciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86772-122">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="86772-123">Define atributos para **key** y **value**.</span><span class="sxs-lookup"><span data-stu-id="86772-123">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="86772-124">Elemento \<clear></span><span class="sxs-lookup"><span data-stu-id="86772-124">\<clear> element</span></span>

<span data-ttu-id="86772-125">Quita todas las referencias a la configuración de la aplicación personalizada heredada y solo permite las referencias que se agregan a los **\<add>** elementos que siguen al **\<clear>** elemento.</span><span class="sxs-lookup"><span data-stu-id="86772-125">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="86772-126">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="86772-126">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="86772-127">Elemento \<remove></span><span class="sxs-lookup"><span data-stu-id="86772-127">\<remove> element</span></span>

<span data-ttu-id="86772-128">Quita de la colección de configuraciones de la aplicación una referencia a una configuración de aplicación personalizada heredada.</span><span class="sxs-lookup"><span data-stu-id="86772-128">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="86772-129">Define un atributo para **key**.</span><span class="sxs-lookup"><span data-stu-id="86772-129">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="86772-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86772-130">Example</span></span>

<span data-ttu-id="86772-131">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="86772-131">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="86772-132">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="86772-132">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="86772-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="86772-133">See also</span></span>

- [<span data-ttu-id="86772-134">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="86772-134">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="86772-135">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="86772-135">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
