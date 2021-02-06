---
description: 'Más información acerca de: esquema de configuración de la aplicación'
title: Esquema de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 24c5771e9d98d07bbdc8dab5fce0f1535bc9b582
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652905"
---
# <a name="application-settings-schema"></a><span data-ttu-id="23e11-103">Esquema de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="23e11-103">Application Settings schema</span></span>

<span data-ttu-id="23e11-104">La configuración de la aplicación permite que una aplicación Windows Forms o ASP.NET almacene y recupere la configuración del ámbito de la aplicación y del ámbito del usuario.</span><span class="sxs-lookup"><span data-stu-id="23e11-104">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="23e11-105">En este contexto, un *valor* es cualquier parte de la información que pueda ser específica de la aplicación o específica del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.</span><span class="sxs-lookup"><span data-stu-id="23e11-105">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="23e11-106">De forma predeterminada, la configuración de la aplicación en una aplicación Windows Forms usa la <xref:System.Configuration.LocalFileSettingsProvider> clase, que utiliza el sistema de configuración de .net para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="23e11-106">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="23e11-107">Para obtener más información acerca de los archivos que usa la configuración de la aplicación, consulte [arquitectura de configuración](/dotnet/desktop/winforms/advanced/application-settings-architecture)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23e11-107">For more information about the files used by application settings, see [Application Settings Architecture](/dotnet/desktop/winforms/advanced/application-settings-architecture).</span></span>

<span data-ttu-id="23e11-108">La configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que usa.</span><span class="sxs-lookup"><span data-stu-id="23e11-108">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="23e11-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="23e11-109">Element</span></span>                    | <span data-ttu-id="23e11-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="23e11-110">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | <span data-ttu-id="23e11-111">Contiene todas las **\<setting>** etiquetas específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23e11-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| **\<userSettings>**        | <span data-ttu-id="23e11-112">Contiene todas las **\<setting>** etiquetas específicas del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="23e11-112">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| **\<setting>**             | <span data-ttu-id="23e11-113">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="23e11-113">Defines a setting.</span></span> <span data-ttu-id="23e11-114">Elemento secundario de **\<applicationSettings>** o **\<userSettings>** .</span><span class="sxs-lookup"><span data-stu-id="23e11-114">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| **\<value>**               | <span data-ttu-id="23e11-115">Define el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="23e11-115">Defines a setting's value.</span></span> <span data-ttu-id="23e11-116">Elemento secundario de **\<setting>** .</span><span class="sxs-lookup"><span data-stu-id="23e11-116">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="23e11-117">Elemento \<applicationSettings></span><span class="sxs-lookup"><span data-stu-id="23e11-117">\<applicationSettings> element</span></span>

<span data-ttu-id="23e11-118">Este elemento contiene todas las **\<setting>** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="23e11-118">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="23e11-119">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="23e11-119">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="23e11-120">Elemento \<userSettings></span><span class="sxs-lookup"><span data-stu-id="23e11-120">\<userSettings> element</span></span>

<span data-ttu-id="23e11-121">Este elemento contiene todas las **\<setting>** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23e11-121">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="23e11-122">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="23e11-122">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="23e11-123">Elemento \<setting></span><span class="sxs-lookup"><span data-stu-id="23e11-123">\<setting> element</span></span>

<span data-ttu-id="23e11-124">Este elemento define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="23e11-124">This element defines a setting.</span></span> <span data-ttu-id="23e11-125">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="23e11-125">It has the following attributes.</span></span>

| <span data-ttu-id="23e11-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="23e11-126">Attribute</span></span>        | <span data-ttu-id="23e11-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="23e11-127">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="23e11-128">**name**</span><span class="sxs-lookup"><span data-stu-id="23e11-128">**name**</span></span>         | <span data-ttu-id="23e11-129">Necesario.</span><span class="sxs-lookup"><span data-stu-id="23e11-129">Required.</span></span> <span data-ttu-id="23e11-130">IDENTIFICADOR único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="23e11-130">The unique ID of the setting.</span></span> <span data-ttu-id="23e11-131">La configuración creada a través de Visual Studio se guarda con el nombre `ProjectName.Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="23e11-131">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="23e11-132">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="23e11-132">**serializeAs**</span></span> | <span data-ttu-id="23e11-133">Necesario.</span><span class="sxs-lookup"><span data-stu-id="23e11-133">Required.</span></span> <span data-ttu-id="23e11-134">Formato que se va a usar para serializar el valor en el texto.</span><span class="sxs-lookup"><span data-stu-id="23e11-134">The format to use for serializing the value to text.</span></span> <span data-ttu-id="23e11-135">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="23e11-135">Valid values are:</span></span><br><br><span data-ttu-id="23e11-136">- `string`.</span><span class="sxs-lookup"><span data-stu-id="23e11-136">- `string`.</span></span> <span data-ttu-id="23e11-137">El valor se serializa como una cadena mediante <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="23e11-137">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="23e11-138">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="23e11-138">- `xml`.</span></span> <span data-ttu-id="23e11-139">El valor se serializa mediante la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="23e11-139">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="23e11-140">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="23e11-140">- `binary`.</span></span> <span data-ttu-id="23e11-141">El valor se serializa como binario codificado por texto mediante la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="23e11-141">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="23e11-142">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="23e11-142">- `custom`.</span></span> <span data-ttu-id="23e11-143">El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa.</span><span class="sxs-lookup"><span data-stu-id="23e11-143">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="23e11-144">Elemento \<value></span><span class="sxs-lookup"><span data-stu-id="23e11-144">\<value> element</span></span>

<span data-ttu-id="23e11-145">Este elemento contiene el valor de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="23e11-145">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="23e11-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23e11-146">Example</span></span>

<span data-ttu-id="23e11-147">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="23e11-147">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="23e11-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="23e11-148">See also</span></span>

- [<span data-ttu-id="23e11-149">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="23e11-149">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="23e11-150">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="23e11-150">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
