---
title: Esquema de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927760"
---
# <a name="application-settings-schema"></a><span data-ttu-id="7cccc-102">Esquema de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="7cccc-102">Application Settings schema</span></span>

<span data-ttu-id="7cccc-103">La configuración de la aplicación permite que una aplicación Windows Forms o ASP.NET almacene y recupere la configuración del ámbito de la aplicación y del ámbito del usuario.</span><span class="sxs-lookup"><span data-stu-id="7cccc-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="7cccc-104">En este contexto, un *valor* es cualquier parte de la información que pueda ser específica de la aplicación o específica del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.</span><span class="sxs-lookup"><span data-stu-id="7cccc-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="7cccc-105">De forma predeterminada, la configuración de la aplicación en una <xref:System.Configuration.LocalFileSettingsProvider> aplicación Windows Forms usa la clase, que utiliza el sistema de configuración de .net para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="7cccc-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="7cccc-106">Para obtener más información acerca de los archivos que usa la configuración de la aplicación, consulte [arquitectura de configuración](../../winforms/advanced/application-settings-architecture.md)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7cccc-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="7cccc-107">La configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que usa.</span><span class="sxs-lookup"><span data-stu-id="7cccc-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="7cccc-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cccc-108">Element</span></span>                    | <span data-ttu-id="7cccc-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7cccc-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="7cccc-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="7cccc-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="7cccc-111">Contiene toda  **\<la configuración >** etiquetas específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7cccc-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="7cccc-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="7cccc-112">**\<userSettings>**</span></span>        | <span data-ttu-id="7cccc-113">Contiene toda  **\<la configuración >** etiquetas específicas del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="7cccc-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="7cccc-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="7cccc-114">**\<setting>**</span></span>             | <span data-ttu-id="7cccc-115">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="7cccc-115">Defines a setting.</span></span> <span data-ttu-id="7cccc-116">Elemento secundario de la  **\<> ApplicationSettings** o  **\<de la > UserSettings**.</span><span class="sxs-lookup"><span data-stu-id="7cccc-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="7cccc-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="7cccc-117">**\<value>**</span></span>               | <span data-ttu-id="7cccc-118">Define el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="7cccc-118">Defines a setting's value.</span></span> <span data-ttu-id="7cccc-119">Secundario de  **\<la configuración >** .</span><span class="sxs-lookup"><span data-stu-id="7cccc-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="7cccc-120">\<applicationSettings (elemento >)</span><span class="sxs-lookup"><span data-stu-id="7cccc-120">\<applicationSettings> element</span></span>

<span data-ttu-id="7cccc-121">Este elemento contiene toda  **\<la configuración >** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="7cccc-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="7cccc-122">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="7cccc-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="7cccc-123">\<elemento > userSettings</span><span class="sxs-lookup"><span data-stu-id="7cccc-123">\<userSettings> element</span></span>

<span data-ttu-id="7cccc-124">Este elemento contiene toda  **\<la configuración >** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7cccc-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="7cccc-125">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="7cccc-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="7cccc-126">\<establecer > elemento</span><span class="sxs-lookup"><span data-stu-id="7cccc-126">\<setting> element</span></span>

<span data-ttu-id="7cccc-127">Este elemento define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="7cccc-127">This element defines a setting.</span></span> <span data-ttu-id="7cccc-128">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="7cccc-128">It has the following attributes.</span></span>

| <span data-ttu-id="7cccc-129">Atributo</span><span class="sxs-lookup"><span data-stu-id="7cccc-129">Attribute</span></span>        | <span data-ttu-id="7cccc-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7cccc-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="7cccc-131">**name**</span><span class="sxs-lookup"><span data-stu-id="7cccc-131">**name**</span></span>         | <span data-ttu-id="7cccc-132">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7cccc-132">Required.</span></span> <span data-ttu-id="7cccc-133">IDENTIFICADOR único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7cccc-133">The unique ID of the setting.</span></span> <span data-ttu-id="7cccc-134">La configuración creada a través de Visual Studio se guarda `ProjectName.Properties.Settings`con el nombre.</span><span class="sxs-lookup"><span data-stu-id="7cccc-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="7cccc-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="7cccc-135">**serializedAs**</span></span> | <span data-ttu-id="7cccc-136">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7cccc-136">Required.</span></span> <span data-ttu-id="7cccc-137">Formato que se va a usar para serializar el valor en el texto.</span><span class="sxs-lookup"><span data-stu-id="7cccc-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="7cccc-138">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="7cccc-138">Valid values are:</span></span><br><br><span data-ttu-id="7cccc-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="7cccc-139">- `string`.</span></span> <span data-ttu-id="7cccc-140">El valor se serializa como una cadena mediante <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="7cccc-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="7cccc-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="7cccc-141">- `xml`.</span></span> <span data-ttu-id="7cccc-142">El valor se serializa mediante la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="7cccc-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="7cccc-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="7cccc-143">- `binary`.</span></span> <span data-ttu-id="7cccc-144">El valor se serializa como binario codificado por texto mediante la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="7cccc-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="7cccc-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="7cccc-145">- `custom`.</span></span> <span data-ttu-id="7cccc-146">El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa.</span><span class="sxs-lookup"><span data-stu-id="7cccc-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="7cccc-147">\<elemento > de valor</span><span class="sxs-lookup"><span data-stu-id="7cccc-147">\<value> element</span></span>

<span data-ttu-id="7cccc-148">Este elemento contiene el valor de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="7cccc-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="7cccc-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cccc-149">Example</span></span>

<span data-ttu-id="7cccc-150">En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="7cccc-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7cccc-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cccc-151">See also</span></span>

- [<span data-ttu-id="7cccc-152">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="7cccc-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="7cccc-153">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="7cccc-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
