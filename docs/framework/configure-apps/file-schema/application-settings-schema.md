---
title: Esquema de configuración de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7a4f60571fb4d30793f64c57317bf0b372ae4812
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701916"
---
# <a name="application-settings-schema"></a><span data-ttu-id="b0409-102">Esquema de configuración de aplicación</span><span class="sxs-lookup"><span data-stu-id="b0409-102">Application Settings schema</span></span>

<span data-ttu-id="b0409-103">Configuración de la aplicación, permitir que una aplicación de Windows Forms o ASP.NET almacenar y recuperar la configuración de ámbito de usuario y el ámbito de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0409-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="b0409-104">En este contexto, un *configuración* es cualquier parte de la información que puede ser específico para la aplicación o específicos del usuario actual, cualquier cosa, desde una cadena de conexión de base de datos al usuario preferida del tamaño de ventana predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b0409-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="b0409-105">De forma predeterminada, usa la configuración de la aplicación en una aplicación Windows Forms el <xref:System.Configuration.LocalFileSettingsProvider> (clase), que usa el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="b0409-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="b0409-106">Para obtener más información acerca de los archivos de configuración de la aplicación, consulte [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="b0409-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="b0409-107">Configuración de la aplicación define los siguientes elementos como parte de los archivos de configuración lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="b0409-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="b0409-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0409-108">Element</span></span>                    | <span data-ttu-id="b0409-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0409-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="b0409-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="b0409-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="b0409-111">Todos los contiene  **\<configuración >** etiquetas específicas para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0409-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="b0409-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="b0409-112">**\<userSettings>**</span></span>        | <span data-ttu-id="b0409-113">Todos los contiene  **\<configuración >** etiquetas específicas para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b0409-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="b0409-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="b0409-114">**\<setting>**</span></span>             | <span data-ttu-id="b0409-115">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="b0409-115">Defines a setting.</span></span> <span data-ttu-id="b0409-116">Elemento secundario de  **\<applicationSettings >** o  **\<userSettings >**.</span><span class="sxs-lookup"><span data-stu-id="b0409-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="b0409-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="b0409-117">**\<value>**</span></span>               | <span data-ttu-id="b0409-118">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="b0409-118">Defines a setting's value.</span></span> <span data-ttu-id="b0409-119">Elemento secundario de  **\<configuración >**.</span><span class="sxs-lookup"><span data-stu-id="b0409-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="b0409-120">\<applicationSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="b0409-120">\<applicationSettings> element</span></span>

<span data-ttu-id="b0409-121">Este elemento contiene todos los  **\<configuración >** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="b0409-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="b0409-122">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="b0409-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="b0409-123">\<userSettings > elemento</span><span class="sxs-lookup"><span data-stu-id="b0409-123">\<userSettings> element</span></span>

<span data-ttu-id="b0409-124">Este elemento contiene todos los  **\<configuración >** etiquetas que son específicas del usuario que está usando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0409-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="b0409-125">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="b0409-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="b0409-126">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="b0409-126">\<setting> element</span></span>

<span data-ttu-id="b0409-127">Este elemento define una configuración.</span><span class="sxs-lookup"><span data-stu-id="b0409-127">This element defines a setting.</span></span> <span data-ttu-id="b0409-128">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="b0409-128">It has the following attributes.</span></span>

| <span data-ttu-id="b0409-129">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0409-129">Attribute</span></span>        | <span data-ttu-id="b0409-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0409-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="b0409-131">**name**</span><span class="sxs-lookup"><span data-stu-id="b0409-131">**name**</span></span>         | <span data-ttu-id="b0409-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0409-132">Required.</span></span> <span data-ttu-id="b0409-133">El identificador único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b0409-133">The unique ID of the setting.</span></span> <span data-ttu-id="b0409-134">La configuración creada a través de Visual Studio se guarda con el nombre `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="b0409-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="b0409-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="b0409-135">**serializedAs**</span></span> | <span data-ttu-id="b0409-136">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0409-136">Required.</span></span> <span data-ttu-id="b0409-137">El formato que se usará para serializar el valor en texto.</span><span class="sxs-lookup"><span data-stu-id="b0409-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="b0409-138">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="b0409-138">Valid values are:</span></span><br><br><span data-ttu-id="b0409-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="b0409-139">- `string`.</span></span> <span data-ttu-id="b0409-140">El valor se serializa como una cadena con un <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="b0409-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="b0409-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="b0409-141">- `xml`.</span></span> <span data-ttu-id="b0409-142">El valor se serializa utilizando serialización XML.</span><span class="sxs-lookup"><span data-stu-id="b0409-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="b0409-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="b0409-143">- `binary`.</span></span> <span data-ttu-id="b0409-144">El valor se serializa como texto codificado binario utiliza la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="b0409-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="b0409-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="b0409-145">- `custom`.</span></span> <span data-ttu-id="b0409-146">El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y lo deserializa.</span><span class="sxs-lookup"><span data-stu-id="b0409-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="b0409-147">\<valor > elemento</span><span class="sxs-lookup"><span data-stu-id="b0409-147">\<value> element</span></span>

<span data-ttu-id="b0409-148">Este elemento contiene el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="b0409-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="b0409-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0409-149">Example</span></span>

<span data-ttu-id="b0409-150">El ejemplo siguiente muestra un archivo de configuración de aplicación que define dos configuraciones de ámbito de la aplicación y dos configuraciones de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="b0409-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b0409-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0409-151">See also</span></span>

- [<span data-ttu-id="b0409-152">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b0409-152">Application Settings Overview</span></span>](~/docs/framework/winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="b0409-153">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b0409-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
