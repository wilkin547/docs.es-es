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
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242834"
---
# <a name="application-settings-schema"></a><span data-ttu-id="97e98-102">Esquema de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="97e98-102">Application Settings schema</span></span>

<span data-ttu-id="97e98-103">La configuración de la aplicación permite que una aplicación de Windows Forms o ASP.NET almacene y recupere la configuración de ámbito de aplicación y de ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="97e98-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="97e98-104">En este contexto, una *configuración* es cualquier elemento de información que puede ser específico de la aplicación o específico del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.</span><span class="sxs-lookup"><span data-stu-id="97e98-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="97e98-105">De forma predeterminada, la configuración de <xref:System.Configuration.LocalFileSettingsProvider> la aplicación en una aplicación de windows Forms usa la clase, que usa el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="97e98-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="97e98-106">Para obtener más información acerca de los archivos utilizados por la configuración de la aplicación, consulte Arquitectura de [configuración](../../winforms/advanced/application-settings-architecture.md)de la aplicación .</span><span class="sxs-lookup"><span data-stu-id="97e98-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="97e98-107">La configuración de la aplicación define los siguientes elementos como parte de los archivos de configuración que utiliza.</span><span class="sxs-lookup"><span data-stu-id="97e98-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="97e98-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="97e98-108">Element</span></span>                    | <span data-ttu-id="97e98-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="97e98-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="97e98-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="97e98-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="97e98-111">Contiene \*\* \<\*\* todas las>etiquetas específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="97e98-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="97e98-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="97e98-112">**\<userSettings>**</span></span>        | <span data-ttu-id="97e98-113">Contiene \*\* \<\*\* todas las etiquetas de>de configuración específicas del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="97e98-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="97e98-114">**\<ajuste de>**</span><span class="sxs-lookup"><span data-stu-id="97e98-114">**\<setting>**</span></span>             | <span data-ttu-id="97e98-115">Define un valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="97e98-115">Defines a setting.</span></span> <span data-ttu-id="97e98-116">Hijo de \*\* \<applicationSettings>\*\* o \*\* \<userSettings>\*\*.</span><span class="sxs-lookup"><span data-stu-id="97e98-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="97e98-117">**\<>de valor**</span><span class="sxs-lookup"><span data-stu-id="97e98-117">**\<value>**</span></span>               | <span data-ttu-id="97e98-118">Define el valor de una configuración.</span><span class="sxs-lookup"><span data-stu-id="97e98-118">Defines a setting's value.</span></span> <span data-ttu-id="97e98-119">Hijo \*\* \< \*\*de la configuración>.</span><span class="sxs-lookup"><span data-stu-id="97e98-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="97e98-120">\<applicationSettings> elemento</span><span class="sxs-lookup"><span data-stu-id="97e98-120">\<applicationSettings> element</span></span>

<span data-ttu-id="97e98-121">Este elemento \*\* \<\*\* contiene todas las etiquetas de configuración>que son específicas de una instancia de la aplicación en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="97e98-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="97e98-122">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="97e98-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="97e98-123">\<userSettings> elemento</span><span class="sxs-lookup"><span data-stu-id="97e98-123">\<userSettings> element</span></span>

<span data-ttu-id="97e98-124">Este elemento \*\* \<\*\* contiene todas las etiquetas de>de configuración que son específicas del usuario que está utilizando actualmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="97e98-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="97e98-125">No define atributos.</span><span class="sxs-lookup"><span data-stu-id="97e98-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="97e98-126">\<ajuste> elemento</span><span class="sxs-lookup"><span data-stu-id="97e98-126">\<setting> element</span></span>

<span data-ttu-id="97e98-127">Este elemento define un valor.</span><span class="sxs-lookup"><span data-stu-id="97e98-127">This element defines a setting.</span></span> <span data-ttu-id="97e98-128">Tiene los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="97e98-128">It has the following attributes.</span></span>

| <span data-ttu-id="97e98-129">Atributo</span><span class="sxs-lookup"><span data-stu-id="97e98-129">Attribute</span></span>        | <span data-ttu-id="97e98-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="97e98-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="97e98-131">**name**</span><span class="sxs-lookup"><span data-stu-id="97e98-131">**name**</span></span>         | <span data-ttu-id="97e98-132">Necesario.</span><span class="sxs-lookup"><span data-stu-id="97e98-132">Required.</span></span> <span data-ttu-id="97e98-133">El identificador único de la configuración.</span><span class="sxs-lookup"><span data-stu-id="97e98-133">The unique ID of the setting.</span></span> <span data-ttu-id="97e98-134">La configuración creada a través `ProjectName.Properties.Settings`de Visual Studio se guarda con el nombre .</span><span class="sxs-lookup"><span data-stu-id="97e98-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="97e98-135">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="97e98-135">**serializeAs**</span></span> | <span data-ttu-id="97e98-136">Necesario.</span><span class="sxs-lookup"><span data-stu-id="97e98-136">Required.</span></span> <span data-ttu-id="97e98-137">El formato que se va a utilizar para serializar el valor en texto.</span><span class="sxs-lookup"><span data-stu-id="97e98-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="97e98-138">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="97e98-138">Valid values are:</span></span><br><br><span data-ttu-id="97e98-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="97e98-139">- `string`.</span></span> <span data-ttu-id="97e98-140">El valor se serializa como <xref:System.ComponentModel.TypeConverter>una cadena mediante un archivo .</span><span class="sxs-lookup"><span data-stu-id="97e98-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="97e98-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="97e98-141">- `xml`.</span></span> <span data-ttu-id="97e98-142">El valor se serializa mediante la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="97e98-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="97e98-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="97e98-143">- `binary`.</span></span> <span data-ttu-id="97e98-144">El valor se serializa como binario codificado por texto mediante la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="97e98-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="97e98-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="97e98-145">- `custom`.</span></span> <span data-ttu-id="97e98-146">El proveedor de configuración tiene un conocimiento inherente de esta configuración y la serializa y deserializa.</span><span class="sxs-lookup"><span data-stu-id="97e98-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="97e98-147">\<valor> elemento</span><span class="sxs-lookup"><span data-stu-id="97e98-147">\<value> element</span></span>

<span data-ttu-id="97e98-148">Este elemento contiene el valor de un valor.</span><span class="sxs-lookup"><span data-stu-id="97e98-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="97e98-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97e98-149">Example</span></span>

<span data-ttu-id="97e98-150">En el ejemplo siguiente se muestra un archivo de configuración de aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:</span><span class="sxs-lookup"><span data-stu-id="97e98-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="97e98-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97e98-151">See also</span></span>

- [<span data-ttu-id="97e98-152">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="97e98-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="97e98-153">Arquitectura de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="97e98-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
