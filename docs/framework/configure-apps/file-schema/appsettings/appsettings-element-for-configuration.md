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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155536"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="6716a-102">Elemento \<appSettings> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="6716a-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="6716a-103">Contiene la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="6716a-103">Contains custom application settings.</span></span> <span data-ttu-id="6716a-104">Se trata de una sección de configuración predefinida proporcionada por el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6716a-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="6716a-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="6716a-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6716a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6716a-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="6716a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="6716a-107">Attribute</span></span>

|           | <span data-ttu-id="6716a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6716a-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6716a-109">**filesystem**</span><span class="sxs-lookup"><span data-stu-id="6716a-109">**file**</span></span>  | <span data-ttu-id="6716a-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="6716a-110">Optional attribute.</span></span><br><br><span data-ttu-id="6716a-111">Especifica una ruta de acceso relativa a un archivo externo que contiene opciones de configuración de la aplicación personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6716a-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="6716a-112">El archivo especificado contiene el mismo tipo de configuración que se especifica en los **\<add>** **\<remove>** elementos, y **\<clear>** y usa el mismo formato de par clave-valor que los elementos.</span><span class="sxs-lookup"><span data-stu-id="6716a-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="6716a-113">La ruta de acceso especificada es relativa al archivo de configuración principal.</span><span class="sxs-lookup"><span data-stu-id="6716a-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="6716a-114">En el caso de una aplicación Windows Forms, esta es la carpeta binaria (por ejemplo, */bin/Debug*), no la ubicación del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6716a-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="6716a-115">En el caso de las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="6716a-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="6716a-116">El tiempo de ejecución omite el atributo si no se encuentra el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6716a-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6716a-117">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="6716a-117">Parent element</span></span>

|     | <span data-ttu-id="6716a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="6716a-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6716a-119">**\<configuration>** Element</span><span class="sxs-lookup"><span data-stu-id="6716a-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="6716a-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6716a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6716a-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6716a-121">Child elements</span></span>

|     | <span data-ttu-id="6716a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="6716a-122">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="6716a-123">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="6716a-123">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="6716a-124">Borra todos los valores de configuración de la aplicación definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="6716a-124">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="6716a-125">Quita una configuración de aplicación definida previamente.</span><span class="sxs-lookup"><span data-stu-id="6716a-125">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6716a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6716a-126">Remarks</span></span>

<span data-ttu-id="6716a-127">El **\<appSettings>** elemento almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6716a-127">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="6716a-128">Se tiene acceso a los pares clave-valor especificados en el **\<appSettings>** elemento en el código mediante la <xref:System.Configuration.ConfigurationSettings> clase.</span><span class="sxs-lookup"><span data-stu-id="6716a-128">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="6716a-129">Puede usar el atributo **File** en el **\<appSettings>** elemento de los archivos *Web. config* y de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6716a-129">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="6716a-130">Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el **\<appSettings>** elemento.</span><span class="sxs-lookup"><span data-stu-id="6716a-130">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="6716a-131">El atributo de **archivo** se puede utilizar en escenarios de desarrollo del equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6716a-131">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="6716a-132">Los archivos de configuración especificados por el atributo **File** deben tener un nodo raíz de **\<appSettings>** en lugar de **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="6716a-132">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="6716a-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6716a-133">Example</span></span>

<span data-ttu-id="6716a-134">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="6716a-134">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="6716a-135">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6716a-135">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6716a-136">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="6716a-136">Configuration file</span></span>

<span data-ttu-id="6716a-137">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6716a-137">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6716a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6716a-138">See also</span></span>

- [<span data-ttu-id="6716a-139">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6716a-139">Configuration file schema for the .NET Framework</span></span>](../index.md)
