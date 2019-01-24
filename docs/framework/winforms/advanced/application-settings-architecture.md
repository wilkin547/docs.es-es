---
title: Arquitectura de configuración de la aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 0e26684933ee2e35dfb0daa52588c2c87505f3f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687250"
---
# <a name="application-settings-architecture"></a>Arquitectura de configuración de la aplicación
Este tema describe cómo funciona la arquitectura de la configuración de la aplicación y explora las características avanzadas de la arquitectura, como valores de configuración agrupados y claves de configuración.  
  
 La arquitectura de configuración de la aplicación admite la definición de parámetros de configuración fuertemente tipados tanto de ámbito de aplicación como de usuario, así como la conservación de dichos parámetros entre las sesiones de la aplicación. La arquitectura proporciona un motor de persistencia predeterminado para guardar la configuración en el sistema de archivos local y cargarla después desde este. La arquitectura también define las interfaces para proporcionar un motor de persistencia personalizado.  
  
 Las interfaces se proporcionan para habilitar los componentes personalizados con el fin de que conserven su propia configuración cuando se hospedan en una aplicación. Mediante el uso de claves de configuración, los componentes pueden conservar la configuración para varias instancias del componente independiente.  
  
## <a name="defining-settings"></a>Definir la configuración  
 La arquitectura de configuración de la aplicación se utiliza en [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y en Windows Forms, y contiene un número de clases base que comparten ambos entornos. Lo más importante es <xref:System.Configuration.SettingsBase>, que proporciona acceso a la configuración a través de una colección y proporciona métodos de bajo nivel para cargar y guardar la configuración. Cada entorno implementa su propia clase derivada de <xref:System.Configuration.SettingsBase> para proporcionar funcionalidad de configuración adicional para ese entorno. En una aplicación basada en Windows Forms, toda la configuración de aplicación debe definirse en una clase derivada de la <xref:System.Configuration.ApplicationSettingsBase> (clase), que agrega la siguiente funcionalidad a la clase base:  
  
-   Operaciones de almacenamiento y de carga de nivel superior  
  
-   Compatibilidad de la configuración de ámbito de usuario  
  
-   Revertir la configuración de un usuario a los valores predeterminados  
  
-   Actualizar la configuración de una versión de aplicación anterior  
  
-   Validar la configuración antes de modificarla o después de guardarla  
  
 La configuración se puede describir utilizando varios atributos definidos dentro de la <xref:System.Configuration> espacio de nombres; estos se describen en [Application Settings Attributes](../../../../docs/framework/winforms/advanced/application-settings-attributes.md). Al definir una configuración, debe aplicar con cualquiera <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, que describe si la configuración se aplica a toda la aplicación o sólo para el usuario actual.  
  
 En el ejemplo de código siguiente se define una clase de configuración personalizada con una configuración única, `BackgroundColor`.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## <a name="settings-persistence"></a>Conservar la configuración  
 El <xref:System.Configuration.ApplicationSettingsBase> clase no propio guardar o cargar la configuración; este trabajo lo realiza el proveedor de configuración, una clase que deriva de <xref:System.Configuration.SettingsProvider>. Si una clase derivada de <xref:System.Configuration.ApplicationSettingsBase> no especifica un proveedor de configuración a través de la <xref:System.Configuration.SettingsProviderAttribute>, a continuación, el proveedor predeterminado, <xref:System.Configuration.LocalFileSettingsProvider>, se utiliza.  
  
 El sistema de configuración incluido originalmente en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admite proporcionar datos de configuración de la aplicación estáticos mediante un archivo machine.config del equipo local o dentro de un archivo `app.`exe.config que implemente con su aplicación. La <xref:System.Configuration.LocalFileSettingsProvider> clase expande esta compatibilidad nativa de las maneras siguientes:  
  
-   La configuración de ámbito de aplicación se puede almacenar en los archivos machine.config o `app.`.exe.config. Machine.config siempre es de solo lectura, mientras que `app`.exe.config está restringido por razones de seguridad a solo lectura para la mayoría de las aplicaciones.  
  
-   La configuración de ámbito de usuario se puede almacenar en archivos `app`.exe.config, en cuyo caso se tratan como valores predeterminados estáticos.  
  
-   La configuración de ámbito de usuario no predeterminada se almacena en un nuevo archivo, *usuario*.config, donde *usuario* es el nombre de usuario de la persona que actualmente ejecuta la aplicación. Puede especificar un valor predeterminado para una configuración con ámbito de usuario con <xref:System.Configuration.DefaultSettingValueAttribute>. Puesto que la configuración de ámbito de usuario cambia a menudo durante la ejecución de la aplicación, `user`.config siempre es de lectura y escritura.  
  
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
  
 Para obtener una definición de los elementos incluidos en la sección de configuración de aplicación de un archivo de configuración, consulte [Esquema de la configuración de la aplicación](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md).  
  
### <a name="settings-bindings"></a>Enlaces de configuración  
 La configuración de aplicación utiliza la arquitectura de enlace de datos de Windows Forms para proporcionar una comunicación bidireccional de actualizaciones de parámetros de configuración entre el objeto de configuración y los componentes. Si utiliza Visual Studio para crear configuraciones de aplicación y asignarlas a las propiedades de componente, estos enlaces se generarán automáticamente.  
  
 Configuración de la aplicación sólo puede enlazar a un componente que admita el <xref:System.Windows.Forms.IBindableComponent> interfaz. Además, el componente debe implementar un evento de cambio de propiedad enlazada a un determinado, o notificar a la configuración que ha cambiado la propiedad a través de la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Si el componente no implementa <xref:System.Windows.Forms.IBindableComponent> y enlaza a través de Visual Studio, las propiedades enlazadas se establecerán la primera vez, pero no se actualizarán. Si el componente implementa <xref:System.Windows.Forms.IBindableComponent> pero las notificaciones de cambios de propiedad de soporte técnico no, el enlace no se actualizará en el archivo de configuración cuando se cambia la propiedad.  
  
 Algunos componentes de Windows Forms, como <xref:System.Windows.Forms.ToolStripItem>, no se admiten enlaces de configuración.  
  
### <a name="settings-serialization"></a>Serialización de la configuración  
 Cuando <xref:System.Configuration.LocalFileSettingsProvider> debe guardar la configuración en el disco, realiza las acciones siguientes:  
  
1.  Usa la reflexión para examinar todas las propiedades definidas en su <xref:System.Configuration.ApplicationSettingsBase> clase derivada, encontrando aquellas que se aplican con cualquiera <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>.  
  
2.  Serializa la propiedad en el disco. Primero intenta llamar a la <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> o <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> en el tipo de asociado del <xref:System.ComponentModel.TypeConverter>. Si esto no tiene éxito, en su lugar utiliza la serialización XML.  
  
3.  Determina qué configuración corresponde a cada archivo, basándose en el atributo de la configuración.  
  
 Si implementa su propia clase de configuración, puede usar el <xref:System.Configuration.SettingsSerializeAsAttribute> para marcar una configuración para la serialización binaria o personalizada utilizando el <xref:System.Configuration.SettingsSerializeAs> enumeración. Para obtener más información sobre cómo crear su propia clase de configuración en código, vea [Cómo: Crear configuración de la aplicación](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### <a name="settings-file-locations"></a>Ubicaciones del archivo de configuración  
 La ubicación de los archivos `app`.exe.config y *usuario*.config diferirá según cómo se instale la aplicación. Para una aplicación basada en formularios de Windows se copian en el equipo local, `app`. exe.config residirá en el mismo directorio que el directorio base del archivo ejecutable principal de la aplicación, y *usuario*.config residirá en el ubicación especificada por el <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> propiedad. Para una aplicación instalada mediante [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], los dos archivos residirán en el directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] en %InstallRoot%\Documents and Settings\\*nombreDeUsuario*\Local Settings.  
  
 La ubicación de almacenamiento de estos archivos es diferente si un usuario habilita perfiles móviles, lo que permite a dicho usuario definir diferentes configuraciones de aplicación y de Windows cuando utilice otros equipos dentro de un dominio. En ese caso, tanto las aplicaciones de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] como las que no sean de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] tendrán archivos `app`.exe.config y *usuario*.config almacenados en %InstallRoot%\Documents and Settings\\*nombreDeUsuario*\Application Data.  
  
 Para más información sobre cómo funciona la característica Configuración de la aplicación con la nueva tecnología de implementación, vea [ClickOnce y configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings). Para más información sobre el directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], vea [Obtener acceso local o remoto a los datos en aplicaciones ClickOnce](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).  
  
## <a name="application-settings-and-security"></a>Configuración de la aplicación y seguridad  
 La configuración de la aplicación está diseñada para trabajar con confianza parcial, un entorno restringido predeterminado en las aplicaciones de Windows Forms hospedadas en la intranet y en Internet. No es necesario ningún permiso especial más allá de la confianza parcial para utilizar la configuración de la aplicación con el proveedor de configuración predeterminado.  
  
 Cuando los parámetros de configuración de la aplicación se utilizan en una aplicación de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], el archivo `user`.config se almacena en el directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]. El tamaño del archivo `user`.config de la aplicación no puede superar la cuota de directorio de datos establecida por [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]. Para más información, consulte [ClickOnce y configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings).  
  
## <a name="custom-settings-providers"></a>Proveedores de configuración personalizados  
 En la arquitectura de configuración de la aplicación, hay una correspondencia imprecisa entre la configuración de aplicaciones clase contenedora, derivado de <xref:System.Configuration.ApplicationSettingsBase>, y el proveedor de configuración asociado o proveedores, deriva <xref:System.Configuration.SettingsProvider>. Esta asociación se define únicamente por la <xref:System.Configuration.SettingsProviderAttribute> aplicado a la clase contenedora o a sus propiedades individuales. Si especifica una configuración de proveedor no está explícitamente, el proveedor predeterminado, <xref:System.Configuration.LocalFileSettingsProvider>, se utiliza. Como resultado, esta arquitectura admite la creación y el uso de proveedores de valores de configuración personalizados.  
  
 Por ejemplo, suponga que desea desarrollar y utilizar `SqlSettingsProvider`, un proveedor que almacenará todos los valores de configuración en una base de datos de Microsoft SQL Server. Su <xref:System.Configuration.SettingsProvider>-clase derivada recibiría esta información en su `Initialize` método como un parámetro de tipo <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>. A continuación implementaría el <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> método para recuperar la configuración del almacén de datos, y <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> para guardarlas. El proveedor puede usar el <xref:System.Configuration.SettingsPropertyCollection> proporcionado a <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> para determinar el nombre, tipo y ámbito de la propiedad, así como cualquier otro atributo de configuración definidos para esa propiedad.  
  
 El proveedor necesitará implementar una propiedad y un método cuyas implementaciones pueden no ser evidentes. El <xref:System.Configuration.SettingsProvider.ApplicationName%2A> es una propiedad abstracta del <xref:System.Configuration.SettingsProvider>; debería programarla para devolver lo siguiente:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 Su clase derivada también debe implementar un método `Initialize` que no toma ningún argumento y no devuelve ningún valor. Este método no está definido por <xref:System.Configuration.SettingsProvider>.  
  
 Finalmente, implemente <xref:System.Configuration.IApplicationSettingsProvider> en su proveedor para proporcionar compatibilidad para actualizar la configuración, revertiendo la configuración a sus valores predeterminados y actualizar la configuración de la versión de una aplicación a otro.  
  
 Una vez implementado y compilado su proveedor, es necesario indicar a su clase de configuración que debe utilizar este proveedor en lugar del predeterminado. Para ello, a través de la <xref:System.Configuration.SettingsProviderAttribute>. Si se aplica a una clase de configuración completa, se utiliza el proveedor para cada configuración que define la clase; Si se aplica a configuraciones independientes, arquitectura de configuración de la aplicación utiliza ese proveedor para ver esas configuraciones solo y utiliza <xref:System.Configuration.LocalFileSettingsProvider> para el resto. El ejemplo de código siguiente muestra cómo indicar a la clase de configuración que utilice su proveedor personalizado.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Se puede llamar a un proveedor simultáneamente desde varios subprocesos, pero siempre se escribe en la misma ubicación de almacenamiento; por tanto, la arquitectura de la Configuración de la aplicación solo creará una única instancia de la clase del proveedor.  
  
> [!IMPORTANT]
>  Debería asegurarse de que su proveedor es seguro para subprocesos y que solo permite un subproceso al mismo tiempo que escribe en los archivos de configuración.  
  
 El proveedor no necesita admitir todos los valores de atributos definidos en el <xref:System.Configuration?displayProperty=nameWithType> espacio de nombres, aunque debe un soporte mínimo <xref:System.Configuration.ApplicationScopedSettingAttribute> y <xref:System.Configuration.UserScopedSettingAttribute>y también debe admitir <xref:System.Configuration.DefaultSettingValueAttribute>. Para esos atributos que no admite, el proveedor solo debería enviar un mensaje de error sin notificación, no producir una excepción. Si la clase de configuración utiliza una combinación no válida de atributos, sin embargo, como la aplicación <xref:System.Configuration.ApplicationScopedSettingAttribute> y <xref:System.Configuration.UserScopedSettingAttribute> a la misma configuración, el proveedor debe producir una excepción y dejara de funcionar.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
- [Application Settings for Custom Controls](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)
- [ClickOnce y la configuración de la aplicación](/visualstudio/deployment/clickonce-and-application-settings)
- [Esquema de la configuración de la aplicación](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)
