---
title: Arquitectura de configuración de la aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 078b5f3fc1cd4273af282580f41e68ca9bd8ff51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182619"
---
# <a name="application-settings-architecture"></a>Arquitectura de configuración de la aplicación
Este tema describe cómo funciona la arquitectura de la configuración de la aplicación y explora las características avanzadas de la arquitectura, como valores de configuración agrupados y claves de configuración.

 La arquitectura de configuración de la aplicación admite la definición de parámetros de configuración fuertemente tipados tanto de ámbito de aplicación como de usuario, así como la conservación de dichos parámetros entre las sesiones de la aplicación. La arquitectura proporciona un motor de persistencia predeterminado para guardar la configuración en el sistema de archivos local y cargarla después desde este. La arquitectura también define las interfaces para proporcionar un motor de persistencia personalizado.

 Las interfaces se proporcionan para habilitar los componentes personalizados con el fin de que conserven su propia configuración cuando se hospedan en una aplicación. Mediante el uso de claves de configuración, los componentes pueden conservar la configuración para varias instancias del componente independiente.

## <a name="defining-settings"></a>Definir la configuración
 La arquitectura de configuración de la aplicación se usa en ASP.NET y Windows Forms, y contiene una serie de clases base que se comparten entre ambos entornos. El más <xref:System.Configuration.SettingsBase>importante es , que proporciona acceso a la configuración a través de una colección y proporciona métodos de bajo nivel para cargar y guardar la configuración. Cada entorno implementa su propia <xref:System.Configuration.SettingsBase> clase derivada de para proporcionar funcionalidad de configuración adicional para ese entorno. En una aplicación basada en formularios Windows Forms, toda la <xref:System.Configuration.ApplicationSettingsBase> configuración de la aplicación debe definirse en una clase derivada de la clase, que agrega la siguiente funcionalidad a la clase base:

- Operaciones de almacenamiento y de carga de nivel superior

- Compatibilidad de la configuración de ámbito de usuario

- Revertir la configuración de un usuario a los valores predeterminados

- Actualizar la configuración de una versión de aplicación anterior

- Validar la configuración antes de modificarla o después de guardarla

 La configuración se puede describir mediante una <xref:System.Configuration> serie de atributos definidos dentro del espacio de nombres; estos se describen en [Atributos](application-settings-attributes.md)de configuración de la aplicación . Al definir una configuración, debe aplicarla con uno <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, que describe si la configuración se aplica a toda la aplicación o solo al usuario actual.

 En el ejemplo de código siguiente se define una clase de configuración personalizada con una configuración única, `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Conservar la configuración
 La <xref:System.Configuration.ApplicationSettingsBase> clase no conserva ni carga la configuración; este trabajo corresponde al proveedor de configuración, <xref:System.Configuration.SettingsProvider>una clase que deriva de . Si una clase <xref:System.Configuration.ApplicationSettingsBase> derivada de no especifica <xref:System.Configuration.SettingsProviderAttribute>un proveedor de <xref:System.Configuration.LocalFileSettingsProvider>configuración a través de la , a continuación, se utiliza el proveedor predeterminado, , .

 El sistema de configuración que se publicó originalmente con .NET Framework admite proporcionar datos de `app.`configuración de aplicaciones estáticas a través del archivo machine.config del equipo local o dentro de un archivo exe.config que implemente con la aplicación. La <xref:System.Configuration.LocalFileSettingsProvider> clase expande esta compatibilidad nativa de las siguientes maneras:

- La configuración de ámbito de aplicación se puede almacenar en los archivos machine.config o `app.`.exe.config. Machine.config siempre es de solo lectura, mientras que `app`.exe.config está restringido por razones de seguridad a solo lectura para la mayoría de las aplicaciones.

- La configuración de ámbito de usuario se puede almacenar en archivos `app`.exe.config, en cuyo caso se tratan como valores predeterminados estáticos.

- La configuración de ámbito de usuario no predeterminada se almacena en un nuevo archivo, *usuario*.config, donde *usuario* es el nombre de usuario de la persona que actualmente ejecuta la aplicación. Puede especificar un valor predeterminado para una <xref:System.Configuration.DefaultSettingValueAttribute>configuración de ámbito de usuario con . Puesto que la configuración de ámbito de usuario cambia a menudo durante la ejecución de la aplicación, `user`.config siempre es de lectura y escritura.

 Los tres archivos de configuración almacenan la configuración en formato XML. El elemento XML de nivel superior para la configuración de ámbito de la aplicación es `<appSettings>`, mientras que `<userSettings>` se utiliza para la configuración de ámbito de usuario. Un archivo `app`.exe.config que contiene la configuración de ámbito de la aplicación y los valores predeterminados para la configuración de ámbito de usuario tendría el siguiente aspecto:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
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

 Para obtener una definición de los elementos incluidos en la sección de configuración de aplicación de un archivo de configuración, consulte [Esquema de la configuración de la aplicación](../../configure-apps/file-schema/application-settings-schema.md).

### <a name="settings-bindings"></a>Enlaces de configuración
 La configuración de aplicación utiliza la arquitectura de enlace de datos de Windows Forms para proporcionar una comunicación bidireccional de actualizaciones de parámetros de configuración entre el objeto de configuración y los componentes. Si utiliza Visual Studio para crear configuraciones de aplicación y asignarlas a las propiedades de componente, estos enlaces se generarán automáticamente.

 Solo puede enlazar una configuración de aplicación <xref:System.Windows.Forms.IBindableComponent> a un componente que admita la interfaz. Además, el componente debe implementar un evento de cambio para una propiedad <xref:System.ComponentModel.INotifyPropertyChanged> enlazada específica o notificar a la configuración de la aplicación que la propiedad ha cambiado a través de la interfaz. Si el componente <xref:System.Windows.Forms.IBindableComponent> no se implementa y se enlaza a través de Visual Studio, las propiedades enlazadas se establecerán la primera vez, pero no se actualizarán. Si el componente <xref:System.Windows.Forms.IBindableComponent> implementa pero no admite notificaciones de cambio de propiedad, el enlace no se actualizará en el archivo de configuración cuando se cambie la propiedad.

 Algunos componentes de <xref:System.Windows.Forms.ToolStripItem>Windows Forms, como , no admiten enlaces de configuración.

### <a name="settings-serialization"></a>Serialización de la configuración
 Cuando <xref:System.Configuration.LocalFileSettingsProvider> debe guardar la configuración en el disco, realiza las siguientes acciones:

1. Utiliza la reflexión para examinar todas <xref:System.Configuration.ApplicationSettingsBase> las propiedades definidas en la <xref:System.Configuration.ApplicationScopedSettingAttribute> clase <xref:System.Configuration.UserScopedSettingAttribute>derivada, buscando las que se aplican con cualquiera o .

2. Serializa la propiedad en el disco. Primero intenta llamar <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> al <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> <xref:System.ComponentModel.TypeConverter>archivo . Si esto no tiene éxito, en su lugar utiliza la serialización XML.

3. Determina qué configuración corresponde a cada archivo, basándose en el atributo de la configuración.

 Si implementa su propia clase de <xref:System.Configuration.SettingsSerializeAsAttribute> configuración, puede usar para marcar una <xref:System.Configuration.SettingsSerializeAs> configuración para la serialización binaria o personalizada mediante la enumeración. Para más información sobre cómo crear su propia clase de parámetros de configuración en código, vea [How to: Create Application Settings](how-to-create-application-settings.md) (Creación de la configuración de la aplicación).

### <a name="settings-file-locations"></a>Ubicaciones del archivo de configuración
 La ubicación de los archivos `app`.exe.config y *usuario*.config diferirá según cómo se instale la aplicación. Para una aplicación basada en formularios Windows Forms `app`copiada en el equipo local, .exe.config residirá en el mismo directorio que el directorio base <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> del archivo ejecutable principal de la aplicación y el *usuario*.config residirá en la ubicación especificada por la propiedad. Para una aplicación instalada por medio de ClickOnce, ambos archivos residirán en el directorio\\de datos ClickOnce debajo de %InstallRoot%-Documents and Settings nombre de*usuario*.

 La ubicación de almacenamiento de estos archivos es ligeramente diferente si un usuario ha habilitado perfiles móviles, lo que permite a un usuario definir diferentes configuraciones de Windows y aplicaciones cuando utilizan otros equipos dentro de un dominio. En ese caso, tanto las aplicaciones ClickOnce como `app`las aplicaciones que no son ClickOnce tendrán sus\\archivos .exe.config y .config de *usuario*almacenados en %InstallRoot%-Documents and Settings nombre de usuario .Application*Data.*

 Para más información sobre cómo funciona la característica Configuración de la aplicación con la nueva tecnología de implementación, vea [ClickOnce y configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings). Para obtener más información sobre el directorio de datos ClickOnce, vea [Acceso a datos locales y remotos en aplicaciones ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Configuración de la aplicación y seguridad
 La configuración de la aplicación está diseñada para trabajar con confianza parcial, un entorno restringido predeterminado en las aplicaciones de Windows Forms hospedadas en la intranet y en Internet. No es necesario ningún permiso especial más allá de la confianza parcial para utilizar la configuración de la aplicación con el proveedor de configuración predeterminado.

 Cuando se utiliza la configuración de `user`la aplicación en una aplicación ClickOnce, el archivo .config se almacena en el directorio de datos ClickOnce. El tamaño del archivo `user`.config de la aplicación no puede superar la cuota de directorio de datos establecida por ClickOnce. Para más información, consulte [ClickOnce y configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Proveedores de configuración personalizados
 En la arquitectura Configuración de la aplicación, hay un acoplamiento <xref:System.Configuration.ApplicationSettingsBase>flexible entre la clase contenedora de <xref:System.Configuration.SettingsProvider>configuración de aplicaciones, derivada de , y el proveedor o proveedores de configuración asociados, derivados de . Esta asociación solo <xref:System.Configuration.SettingsProviderAttribute> se define mediante la aplicada a la clase contenedora o sus propiedades individuales. Si no se especifica explícitamente un proveedor <xref:System.Configuration.LocalFileSettingsProvider>de configuración, se usa el proveedor predeterminado , , . Como resultado, esta arquitectura admite la creación y el uso de proveedores de valores de configuración personalizados.

 Por ejemplo, suponga que desea desarrollar y utilizar `SqlSettingsProvider`, un proveedor que almacenará todos los valores de configuración en una base de datos de Microsoft SQL Server. La <xref:System.Configuration.SettingsProvider>clase derivada recibiría esta `Initialize` información en su <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>método como un parámetro de tipo . A continuación, <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> implementaría el método para recuperar <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> la configuración del almacén de datos y guardarla. El proveedor puede <xref:System.Configuration.SettingsPropertyCollection> usar <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> el proporcionado para determinar el nombre, el tipo y el ámbito de la propiedad, así como cualquier otro atributo de configuración definido para esa propiedad.

 El proveedor necesitará implementar una propiedad y un método cuyas implementaciones pueden no ser evidentes. La <xref:System.Configuration.SettingsProvider.ApplicationName%2A> propiedad es una <xref:System.Configuration.SettingsProvider>propiedad abstracta de ; debe programarlo para devolver lo siguiente:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 Su clase derivada también debe implementar un método `Initialize` que no toma ningún argumento y no devuelve ningún valor. Este método no <xref:System.Configuration.SettingsProvider>está definido por .

 Por último, <xref:System.Configuration.IApplicationSettingsProvider> implemente en el proveedor para proporcionar compatibilidad con la actualización de la configuración, revertir la configuración a sus valores predeterminados y actualizar la configuración de una versión de la aplicación a otra.

 Una vez implementado y compilado su proveedor, es necesario indicar a su clase de configuración que debe utilizar este proveedor en lugar del predeterminado. Lo logras <xref:System.Configuration.SettingsProviderAttribute>a través del archivo . Si se aplica a una clase de configuración completa, el proveedor se utiliza para cada configuración que define la clase; Si se aplica a la configuración individual, la arquitectura <xref:System.Configuration.LocalFileSettingsProvider> de configuración de la aplicación usa ese proveedor solo para esa configuración y se usa para el resto. El ejemplo de código siguiente muestra cómo indicar a la clase de configuración que utilice su proveedor personalizado.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Se puede llamar a un proveedor simultáneamente desde varios subprocesos, pero siempre se escribe en la misma ubicación de almacenamiento; por tanto, la arquitectura de la Configuración de la aplicación solo creará una única instancia de la clase del proveedor.

> [!IMPORTANT]
> Debería asegurarse de que su proveedor es seguro para subprocesos y que solo permite un subproceso al mismo tiempo que escribe en los archivos de configuración.

 El proveedor no necesita admitir todos los atributos de configuración definidos <xref:System.Configuration?displayProperty=nameWithType> <xref:System.Configuration.ApplicationScopedSettingAttribute> en <xref:System.Configuration.UserScopedSettingAttribute>el espacio <xref:System.Configuration.DefaultSettingValueAttribute>de nombres, aunque debe admitir un valor mínimo y , y también debe admitir . Para esos atributos que no admite, el proveedor solo debería enviar un mensaje de error sin notificación, no producir una excepción. Sin embargo, si la clase de configuración utiliza <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> una combinación no válida de atributos, como aplicar y a la misma configuración, el proveedor debe producir una excepción y cesar la operación.

## <a name="see-also"></a>Consulte también

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
- [Configuración de la aplicación para controles personalizados](application-settings-for-custom-controls.md)
- [ClickOnce y configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings)
- [Esquema de configuración de la aplicación](../../configure-apps/file-schema/application-settings-schema.md)
