---
title: Esquema de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "81242834"
---
# <a name="application-settings-schema"></a><span data-ttu-id="00849-102">Esquema de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="00849-102">Application Settings schema</span></span>

<span data-ttu-id="00849-103">La configuración de la aplicación permite que una aplicación Windows Forms o ASP.NET almacene y recupere la configuración del ámbito de la aplicación y del ámbito del usuario.</span><span class="sxs-lookup"><span data-stu-id="00849-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="00849-104">En este contexto, un *valor* es cualquier parte de la información que pueda ser específica de la aplicación o específica del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.</span><span class="sxs-lookup"><span data-stu-id="00849-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="00849-105">De forma predeterminada, la configuración de la aplicación en una aplicación Windows Forms usa la <xref:System.Configuration.LocalFileSettingsProvider> clase, que utiliza el sistema de configuración de .net para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="00849-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="00849-106">Para obtener más información acerca de los archivos que usa la configuración de la aplicación, consulte [arquitectura de configuración](../../winforms/advanced/application-settings-architecture.md)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="00849-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="00849-107">La configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que usa.</span><span class="sxs-lookup"><span data-stu-id="00849-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="00849-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="00849-108">Element</span></span>                    | <span data-ttu-id="00849-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="00849-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | <span data-ttu-id="00849-110">Contiene todas las **\<setting>** etiquetas específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="00849-110">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| **\<userSettings>**        | <span data-ttu-id="00849-111">Contiene todas las **\<setting>** etiquetas específicas del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="00849-111">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| **\<setting>**             | <span data-ttu-id="00849-112">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="00849-112">Defines a setting.</span></span> <span data-ttu-id="00849-113">Elemento secundario de **\<applicationSettings>** o **\<userSettings>** .</span><span class="sxs-lookup"><span data-stu-id="00849-113">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| **\<value>**               | <span data-ttu-id="00849-114">Define el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="00849-114">Defines a setting's value.</span></span> <span data-ttu-id="00849-115">Elemento secundario de **\<setting>** .</span><span class="sxs-lookup"><span data-stu-id="00849-115">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="00849-116">Elemento \<applicationSettings></span><span class="sxs-lookup"><span data-stu-id="00849-116">\<applicationSettings> element</span></span>

<span data-ttu-id="00849-117">Este elemento contiene todas las **\<setting>** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="00849-117">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="00849-118">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="00849-118">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="00849-119">Elemento \<userSettings></span><span class="sxs-lookup"><span data-stu-id="00849-119">\<userSettings> element</span></span>

<span data-ttu-id="00849-120">Este elemento contiene todas las **\<setting>** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="00849-120">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="00849-121">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="00849-121">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="00849-122">Elemento \<setting></span><span class="sxs-lookup"><span data-stu-id="00849-122">\<setting> element</span></span>

<span data-ttu-id="00849-123">Este elemento define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="00849-123">This element defines a setting.</span></span> <span data-ttu-id="00849-124">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="00849-124">It has the following attributes.</span></span>

| <span data-ttu-id="00849-125">Atributo</span><span class="sxs-lookup"><span data-stu-id="00849-125">Attribute</span></span>        | <span data-ttu-id="00849-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="00849-126">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="00849-127">**name**</span><span class="sxs-lookup"><span data-stu-id="00849-127">**name**</span></span>         | <span data-ttu-id="00849-128">Necesario.</span><span class="sxs-lookup"><span data-stu-id="00849-128">Required.</span></span> <span data-ttu-id="00849-129">IDENTIFICADOR único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="00849-129">The unique ID of the setting.</span></span> <span data-ttu-id="00849-130">La configuración creada a través de Visual Studio se guarda con el nombre `ProjectName.Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="00849-130">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="00849-131">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="00849-131">**serializeAs**</span></span> | <span data-ttu-id="00849-132">Necesario.</span><span class="sxs-lookup"><span data-stu-id="00849-132">Required.</span></span> <span data-ttu-id="00849-133">Formato que se va a usar para serializar el valor en el texto.</span><span class="sxs-lookup"><span data-stu-id="00849-133">The format to use for serializing the value to text.</span></span> <span data-ttu-id="00849-134">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="00849-134">Valid values are:</span></span><br><br><span data-ttu-id="00849-135">- `string`.</span><span class="sxs-lookup"><span data-stu-id="00849-135">- `string`.</span></span> <span data-ttu-id="00849-136">El valor se serializa como una cadena mediante <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="00849-136">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="00849-137">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="00849-137">- `xml`.</span></span> <span data-ttu-id="00849-138">El valor se serializa mediante la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="00849-138">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="00849-139">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="00849-139">- `binary`.</span></span> <span data-ttu-id="00849-140">El valor se serializa como binario codificado por texto mediante la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="00849-140">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="00849-141">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="00849-141">- `custom`.</span></span> <span data-ttu-id="00849-142">El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa.</span><span class="sxs-lookup"><span data-stu-id="00849-142">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="00849-143">Elemento \<value></span><span class="sxs-lookup"><span data-stu-id="00849-143">\<value> element</span></span>

<span data-ttu-id="00849-144">Este elemento contiene el valor de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="00849-144">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="00849-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00849-145">Example</span></span>

<span data-ttu-id="00849-146">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="00849-146">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="00849-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00849-147">See also</span></span>

- [<span data-ttu-id="00849-148">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="00849-148">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="00849-149">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="00849-149">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
