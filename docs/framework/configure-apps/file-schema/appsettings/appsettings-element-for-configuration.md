---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 47d7648aae08544890a4dd2e42cedbf68a8acc72
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214735"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="1690b-102">\<elemento > appSettings para la configuración de \<></span><span class="sxs-lookup"><span data-stu-id="1690b-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="1690b-103">Contiene la configuración de la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="1690b-103">Contains custom application settings.</span></span> <span data-ttu-id="1690b-104">Se trata de una sección de configuración predefinida proporcionada por el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1690b-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="1690b-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1690b-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="1690b-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="1690b-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1690b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1690b-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="1690b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1690b-108">Attribute</span></span>

|           | <span data-ttu-id="1690b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1690b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="1690b-110">**file**</span><span class="sxs-lookup"><span data-stu-id="1690b-110">**file**</span></span>  | <span data-ttu-id="1690b-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1690b-111">Optional attribute.</span></span><br><br><span data-ttu-id="1690b-112">Especifica una ruta de acceso relativa a un archivo externo que contiene opciones de configuración de la aplicación personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1690b-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="1690b-113">El archivo especificado contiene el mismo tipo de configuración que se especifica en el **\<agregar >** , **\<quitar >** y **\<borrar** elementos de > y usa el mismo formato de par clave-valor que los elementos.</span><span class="sxs-lookup"><span data-stu-id="1690b-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="1690b-114">La ruta de acceso especificada es relativa al archivo de configuración principal.</span><span class="sxs-lookup"><span data-stu-id="1690b-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="1690b-115">En el caso de una aplicación Windows Forms, esta es la carpeta binaria (por ejemplo, */bin/Debug*), no la ubicación del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1690b-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="1690b-116">En el caso de las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="1690b-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="1690b-117">Tenga en cuenta que el tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="1690b-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="1690b-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="1690b-118">Parent element</span></span>

|     | <span data-ttu-id="1690b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1690b-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1690b-120"> **> de configuración de\<** Element</span><span class="sxs-lookup"><span data-stu-id="1690b-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="1690b-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1690b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1690b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1690b-122">Child elements</span></span>

|     | <span data-ttu-id="1690b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="1690b-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1690b-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="1690b-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="1690b-125">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="1690b-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="1690b-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="1690b-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="1690b-127">Borra todos los valores de configuración de la aplicación definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="1690b-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="1690b-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="1690b-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="1690b-129">Quita una configuración de aplicación definida previamente.</span><span class="sxs-lookup"><span data-stu-id="1690b-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1690b-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1690b-130">Remarks</span></span>

<span data-ttu-id="1690b-131">El elemento **\<appSettings >** almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1690b-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="1690b-132">Se tiene acceso a los pares clave-valor especificados en el elemento **\<appSettings >** en el código mediante la clase <xref:System.Configuration.ConfigurationSettings>.</span><span class="sxs-lookup"><span data-stu-id="1690b-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="1690b-133">Puede usar el atributo **File** en el elemento **\<appSettings >** de los archivos *Web. config* y de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1690b-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="1690b-134">Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el elemento **\<appSettings >** .</span><span class="sxs-lookup"><span data-stu-id="1690b-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="1690b-135">El atributo de **archivo** se puede utilizar en escenarios de desarrollo del equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1690b-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="1690b-136">Los archivos de configuración especificados por el atributo **File** deben tener un nodo raíz de **\<appSettings >** en lugar de **\<> de configuración**.</span><span class="sxs-lookup"><span data-stu-id="1690b-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="1690b-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1690b-137">Example</span></span>

<span data-ttu-id="1690b-138">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="1690b-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="1690b-139">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1690b-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="1690b-140">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1690b-140">Configuration file</span></span>

<span data-ttu-id="1690b-141">Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1690b-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1690b-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1690b-142">See also</span></span>

- [<span data-ttu-id="1690b-143">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1690b-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
