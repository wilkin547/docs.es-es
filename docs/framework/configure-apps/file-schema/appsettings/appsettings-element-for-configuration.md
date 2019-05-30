---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e8f85be2efe972fc45230855d18649a89f2fbd61
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300818"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="5e677-102">\<appSettings > (elemento) para \<configuración ></span><span class="sxs-lookup"><span data-stu-id="5e677-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="5e677-103">Contiene la configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="5e677-103">Contains custom application settings.</span></span> <span data-ttu-id="5e677-104">Se trata de una sección de configuración predefinidos proporcionada por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e677-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="5e677-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5e677-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5e677-106">&nbsp;&nbsp; **\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="5e677-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5e677-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e677-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="5e677-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="5e677-108">Attribute</span></span>

|           | <span data-ttu-id="5e677-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e677-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5e677-110">**file**</span><span class="sxs-lookup"><span data-stu-id="5e677-110">**file**</span></span>  | <span data-ttu-id="5e677-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="5e677-111">Optional attribute.</span></span><br><br><span data-ttu-id="5e677-112">Especifica una ruta de acceso relativa a un archivo externo que contiene los valores de configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="5e677-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="5e677-113">El archivo especificado contiene el mismo tipo de configuración que se especifican en el  **\<Agregar >** ,  **\<quitar >** , y  **\<borrar >** elementos y utiliza el mismo par de clave/valor de formato que dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="5e677-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="5e677-114">La ruta de acceso especificada es relativa al archivo de configuración principal.</span><span class="sxs-lookup"><span data-stu-id="5e677-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="5e677-115">Para una aplicación Windows Forms, esta es la carpeta binaria (como */bin/debug*), no la ubicación del archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e677-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="5e677-116">Las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde el *web.config* archivo se encuentra.</span><span class="sxs-lookup"><span data-stu-id="5e677-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="5e677-117">Tenga en cuenta que el tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5e677-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5e677-118">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="5e677-118">Parent element</span></span>

|     | <span data-ttu-id="5e677-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e677-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5e677-120"> *\*\<Configuración >** elemento</span><span class="sxs-lookup"><span data-stu-id="5e677-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="5e677-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e677-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5e677-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5e677-122">Child elements</span></span>

|     | <span data-ttu-id="5e677-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e677-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5e677-124"> *\*\<add>** </span><span class="sxs-lookup"><span data-stu-id="5e677-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="5e677-125">Agrega una configuración de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="5e677-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="5e677-126"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="5e677-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="5e677-127">Borra todas las configuraciones de aplicación definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e677-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="5e677-128"> *\*\<remove>** </span><span class="sxs-lookup"><span data-stu-id="5e677-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="5e677-129">Quita una configuración de aplicación definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e677-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5e677-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e677-130">Remarks</span></span>

<span data-ttu-id="5e677-131">El  **\<appSettings >** elemento almacena información de configuración de aplicación personalizada, como las cadenas de conexión de base de datos, las rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para un aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e677-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="5e677-132">Los pares clave/valor especificados en el  **\<appSettings >** elemento son accesibles desde código mediante la <xref:System.Configuration.ConfigurationSettings> clase.</span><span class="sxs-lookup"><span data-stu-id="5e677-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="5e677-133">Puede usar el **archivo** atributo en el  **\<appSettings >** elemento de la *Web.config* y archivos de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e677-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="5e677-134">Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el  **\<appSettings >** elemento.</span><span class="sxs-lookup"><span data-stu-id="5e677-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="5e677-135">El **archivo** atributo se puede usar en escenarios de desarrollo en equipo de control de origen, como cuando un usuario desea invalidar la configuración de proyecto especificada en un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e677-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="5e677-136">Los archivos de configuración especificados por el **archivo** atributo debe tener un nodo raíz de  **\<appSettings >** lugar  **\<configuración >** .</span><span class="sxs-lookup"><span data-stu-id="5e677-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="5e677-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e677-137">Example</span></span>

<span data-ttu-id="5e677-138">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:</span><span class="sxs-lookup"><span data-stu-id="5e677-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="5e677-139">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="5e677-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5e677-140">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5e677-140">Configuration file</span></span>

<span data-ttu-id="5e677-141">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e677-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e677-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e677-142">See also</span></span>

- [<span data-ttu-id="5e677-143">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5e677-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
