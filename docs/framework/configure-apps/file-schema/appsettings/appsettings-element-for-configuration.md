---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155536"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="91380-102">\<appSettings> \<elemento para la configuración></span><span class="sxs-lookup"><span data-stu-id="91380-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="91380-103">Contiene la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="91380-103">Contains custom application settings.</span></span> <span data-ttu-id="91380-104">Esta es una sección de configuración predefinida proporcionada por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91380-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="91380-105">configuración &nbsp; &nbsp;>[\*\* \<\*\*](../configuration-element.md) \*\* \<appSettings>\*\*</span><span class="sxs-lookup"><span data-stu-id="91380-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="91380-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91380-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="91380-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="91380-107">Attribute</span></span>

|           | <span data-ttu-id="91380-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="91380-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="91380-109">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="91380-109">**file**</span></span>  | <span data-ttu-id="91380-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="91380-110">Optional attribute.</span></span><br><br><span data-ttu-id="91380-111">Especifica una ruta de acceso relativa a un archivo externo que contiene valores de configuración de aplicación personalizados.</span><span class="sxs-lookup"><span data-stu-id="91380-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="91380-112">El archivo especificado contiene el mismo tipo de \*\* \< **configuración que se especifica en la>de agregar , \*\* \<quitar>** y \*\* \<borrar>\*\* elementos y utiliza el mismo formato de par clave/valor que esos elementos.</span><span class="sxs-lookup"><span data-stu-id="91380-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="91380-113">La ruta especificada es relativa al archivo de configuración principal.</span><span class="sxs-lookup"><span data-stu-id="91380-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="91380-114">Para una aplicación de windows Forms, esta es la carpeta binaria (como */bin/debug*), no la ubicación del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91380-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="91380-115">Para las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo *web.config.*</span><span class="sxs-lookup"><span data-stu-id="91380-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="91380-116">El tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="91380-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="91380-117">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="91380-117">Parent element</span></span>

|     | <span data-ttu-id="91380-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="91380-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="91380-119">\*\* \<configuración>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="91380-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="91380-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91380-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="91380-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91380-121">Child elements</span></span>

|     | <span data-ttu-id="91380-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="91380-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="91380-123">**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="91380-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="91380-124">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="91380-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="91380-125">**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="91380-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="91380-126">Borra todos los valores de aplicación definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="91380-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="91380-127">**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="91380-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="91380-128">Quita una configuración de aplicación definida previamente.</span><span class="sxs-lookup"><span data-stu-id="91380-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="91380-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91380-129">Remarks</span></span>

<span data-ttu-id="91380-130">El elemento \*\* \<appSettings>\*\* almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL de servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="91380-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="91380-131">Los pares clave/valor especificados en el <xref:System.Configuration.ConfigurationSettings> \*\* \<\*\* elemento de>appSettings se tienen acceso en el código mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="91380-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="91380-132">Puede usar el atributo **file** en el \*\* \<\*\* elemento appSettings>de los archivos *web.config* y de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91380-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="91380-133">Este atributo especifica un archivo de configuración que proporciona valores adicionales o reemplaza la configuración especificada en el \*\* \<elemento de>appSettings.\*\*</span><span class="sxs-lookup"><span data-stu-id="91380-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="91380-134">El atributo **de archivo** se puede usar en escenarios de desarrollo de equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91380-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="91380-135">Los archivos de configuración especificados por el atributo **file** deben tener un nodo raíz de \*\* \<appSettings>\*\* en lugar de \*\* \<la configuración>\*\*.</span><span class="sxs-lookup"><span data-stu-id="91380-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="91380-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91380-136">Example</span></span>

<span data-ttu-id="91380-137">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="91380-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="91380-138">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="91380-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="91380-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="91380-139">Configuration file</span></span>

<span data-ttu-id="91380-140">Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91380-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="91380-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91380-141">See also</span></span>

- [<span data-ttu-id="91380-142">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="91380-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
