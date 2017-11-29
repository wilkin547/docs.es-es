---
title: "Esquema de la configuración de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: "3"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d93a18b17e0d6b8e413903fb84dc6b427d94f6af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="application-settings-schema"></a><span data-ttu-id="4fe94-102">Esquema de la configuración de aplicación</span><span class="sxs-lookup"><span data-stu-id="4fe94-102">Application Settings schema</span></span>

<span data-ttu-id="4fe94-103">Configuración de la aplicación que una aplicación de formularios Windows Forms o ASP.NET almacenar y recuperar la configuración de ámbito de la aplicación y ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="4fe94-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="4fe94-104">En este contexto, un *configuración* es cualquier fragmento de información que puede ser específicos de la aplicación o específica del usuario actual, cualquier cosa, desde una cadena de conexión de base de datos al usuario preferido del tamaño de ventana predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4fe94-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="4fe94-105">De forma predeterminada, usa la configuración de la aplicación en una aplicación de formularios Windows Forms el <xref:System.Configuration.LocalFileSettingsProvider> (clase), que utiliza el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="4fe94-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="4fe94-106">Para obtener más información acerca de los archivos utilizados por la configuración de la aplicación, consulte [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="4fe94-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="4fe94-107">Configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="4fe94-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="4fe94-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe94-108">Element</span></span>                    | <span data-ttu-id="4fe94-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe94-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="4fe94-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="4fe94-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="4fe94-111">Todos los contiene  **\<configuración >** etiquetas específicas para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fe94-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="4fe94-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="4fe94-112">**\<userSettings>**</span></span>        | <span data-ttu-id="4fe94-113">Todos los contiene  **\<configuración >** etiquetas específicas para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4fe94-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="4fe94-114">**\<Configuración >**</span><span class="sxs-lookup"><span data-stu-id="4fe94-114">**\<setting>**</span></span>             | <span data-ttu-id="4fe94-115">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe94-115">Defines a setting.</span></span> <span data-ttu-id="4fe94-116">Elemento secundario del  **\<applicationSettings >** o  **\<userSettings >**.</span><span class="sxs-lookup"><span data-stu-id="4fe94-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="4fe94-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="4fe94-117">**\<value>**</span></span>               | <span data-ttu-id="4fe94-118">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe94-118">Defines a setting's value.</span></span> <span data-ttu-id="4fe94-119">Elemento secundario de  **\<configuración >**.</span><span class="sxs-lookup"><span data-stu-id="4fe94-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="4fe94-120">\<applicationSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="4fe94-120">\<applicationSettings> element</span></span>

<span data-ttu-id="4fe94-121">Este elemento contiene todas las  **\<configuración >** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="4fe94-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="4fe94-122">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="4fe94-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="4fe94-123">\<userSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="4fe94-123">\<userSettings> element</span></span>

<span data-ttu-id="4fe94-124">Este elemento contiene todas las  **\<configuración >** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fe94-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="4fe94-125">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="4fe94-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="4fe94-126">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="4fe94-126">\<setting> element</span></span>

<span data-ttu-id="4fe94-127">Este elemento define un valor.</span><span class="sxs-lookup"><span data-stu-id="4fe94-127">This element defines a setting.</span></span> <span data-ttu-id="4fe94-128">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="4fe94-128">It has the following attributes.</span></span>

| <span data-ttu-id="4fe94-129">Atributo</span><span class="sxs-lookup"><span data-stu-id="4fe94-129">Attribute</span></span>        | <span data-ttu-id="4fe94-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe94-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="4fe94-131">**name**</span><span class="sxs-lookup"><span data-stu-id="4fe94-131">**name**</span></span>         | <span data-ttu-id="4fe94-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4fe94-132">Required.</span></span> <span data-ttu-id="4fe94-133">El identificador único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe94-133">The unique ID of the setting.</span></span> <span data-ttu-id="4fe94-134">La configuración creada con Visual Studio se guarda con el nombre `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="4fe94-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="4fe94-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="4fe94-135">**serializedAs**</span></span> | <span data-ttu-id="4fe94-136">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4fe94-136">Required.</span></span> <span data-ttu-id="4fe94-137">Formato que se va a usar para serializar el valor en texto.</span><span class="sxs-lookup"><span data-stu-id="4fe94-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="4fe94-138">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="4fe94-138">Valid values are:</span></span><br><br><span data-ttu-id="4fe94-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="4fe94-139">- `string`.</span></span> <span data-ttu-id="4fe94-140">El valor se serializa como una cadena con un <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="4fe94-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="4fe94-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="4fe94-141">- `xml`.</span></span> <span data-ttu-id="4fe94-142">El valor se serializa utilizando la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="4fe94-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="4fe94-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="4fe94-143">- `binary`.</span></span> <span data-ttu-id="4fe94-144">El valor se serializa como binario codificado en texto utilizando la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="4fe94-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="4fe94-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="4fe94-145">- `custom`.</span></span> <span data-ttu-id="4fe94-146">El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa lo.</span><span class="sxs-lookup"><span data-stu-id="4fe94-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="4fe94-147">\<valor > elemento</span><span class="sxs-lookup"><span data-stu-id="4fe94-147">\<value> element</span></span>

<span data-ttu-id="4fe94-148">Este elemento contiene el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe94-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="4fe94-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fe94-149">Example</span></span>

<span data-ttu-id="4fe94-150">En el ejemplo siguiente se muestra un archivo de configuración de aplicación que define dos configuraciones de ámbito de la aplicación y dos configuraciones de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="4fe94-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4fe94-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe94-151">See also</span></span>

<span data-ttu-id="4fe94-152">[Introducción a la configuración de la aplicación](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4fe94-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="4fe94-153">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4fe94-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
