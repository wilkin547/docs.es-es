---
title: "Application Settings Architecture | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "application settings [Windows Forms], architecture"
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Application Settings Architecture
Este tema describe cómo funciona la arquitectura de la configuración de la aplicación y explora las características avanzadas de la arquitectura, como valores de configuración agrupados y claves de configuración.  
  
 La arquitectura de configuración de la aplicación admite la definición de parámetros de configuración fuertemente tipados tanto de ámbito de aplicación como de usuario, así como conservar dichos parámetros entre las sesiones de la aplicación.  La arquitectura proporciona un motor de persistencia predeterminado para guardar la configuración y cargarla desde el sistema de archivos local.  La arquitectura también define las interfaces para proporcionar un motor de persistencia personalizado.  
  
 Las interfaces se proporcionan para habilitar los componentes personalizados con el fin de que conserven su propia configuración cuando se hospedan en una aplicación.  Mediante el uso de claves de valores de configuración, los componentes pueden conservar la configuración para varias instancias del componente independiente.  
  
## Definir valores de configuración  
 La arquitectura de configuración de la aplicación se utiliza en [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y en formularios Windows Forms, y contiene un número de clases base que comparten ambos entornos.  La más importante es <xref:System.Configuration.SettingsBase>, que proporciona el acceso a la configuración a través de una colección y proporciona los métodos de bajo nivel para cargar y guardar la configuración.  Cada entorno implementa su propia clase derivada de <xref:System.Configuration.SettingsBase> para proporcionar la funcionalidad de la configuración adicional para ese entorno.  En una aplicación basada en formularios Windows Forms, toda la configuración de la aplicación debe definirse en una clase derivada de <xref:System.Configuration.ApplicationSettingsBase>, que agrega la siguiente funcionalidad a la clase base:  
  
-   Operaciones de almacenamiento y de carga de nivel superior  
  
-   Compatibilidad de la configuración de ámbito de usuario  
  
-   Revertir los valores de configuración del usuario a los valores predeterminados  
  
-   Actualizar la configuración de una versión de aplicación anterior  
  
-   Validar los valores de configuración antes de modificarlos o después de guardarlos  
  
 Los valores de configuración se puede describir utilizando varios atributos definidos dentro del espacio de nombres <xref:System.Configuration>; éstos se describen en [Application Settings Attributes](../../../../docs/framework/winforms/advanced/application-settings-attributes.md).  Cuando se define un valor de configuración, debe aplicarse con <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>, que especifican si la configuración se aplica a toda la aplicación o sólo para el usuario actual.  
  
 El ejemplo de código siguiente define una clase de valores de configuración personalizados con una configuración única,  `BackgroundColor`.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## Conservar la configuración  
 La clase <xref:System.Configuration.ApplicationSettingsBase> no se conserva ni carga la configuración; este trabajo lo realiza el proveedor de valores de configuración, una clase que deriva de <xref:System.Configuration.SettingsProvider>.  Si una clase derivada de <xref:System.Configuration.ApplicationSettingsBase> no especifica un proveedor de valores de configuración a través de <xref:System.Configuration.SettingsProviderAttribute>, entonces debe utilizar el proveedor predeterminado <xref:System.Configuration.LocalFileSettingsProvider>.  
  
 El sistema de configuración incluido originalmente en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admite proporcionar datos de configuración de la aplicación estáticos mediante un archivo machine.config del equipo local o dentro de un archivo `app.`exe.config file que implemente con su aplicación.  La clase <xref:System.Configuration.LocalFileSettingsProvider> expande esta compatibilidad nativa de las siguientes formas:  
  
-   La configuración de ámbito de aplicación se puede almacenar en los archivos machine.config o `app.`exe.config.  Machine.config siempre es de sólo lectura, mientras que `app`.exe.config está restringido por razones de seguridad a sólo lectura para la mayoría de las aplicaciones.  
  
-   La configuración de ámbito de usuario se puede almacenar en archivos `app`.exe.config, en cuyo caso se tratan como valores predeterminados estáticos.  
  
-   La configuración de ámbito de usuario no predeterminada se almacena en un nuevo archivo, *usuario*.config, donde *usuario* es el nombre de usuario de la persona que actualmente ejecuta la aplicación.  Puede especificar un valor predeterminado para una configuración de ámbito de usuario con <xref:System.Configuration.DefaultSettingValueAttribute>.  Puesto que la configuración de ámbito de usuario cambia a menudo durante la ejecución de la aplicación, `user`.config siempre es de lectura y escritura.  
  
 Los tres archivos de configuración almacenan la configuración en formato XML.  El elemento XML de nivel superior para la configuración de ámbito de la aplicación es `<appSettings>`, mientras que `<userSettings>` se utiliza para la configuración de ámbito de usuario.  Un archivo `app`.exe.config que contiene la configuración de ámbito de la aplicación y los valores predeterminados para la configuración de ámbito de usuario tendría el siguiente aspecto:  
  
```  
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
  
 Para obtener una definición de los elementos incluidos en la sección de configuración de aplicación de un archivo de configuración, vea [Esquema de la configuración de la aplicación](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md).  
  
### Enlaces de parámetros de configuración  
 Los parámetros de configuración de aplicación utilizan la arquitectura de enlace de datos de los formularios Windows Forms para proporcionar una comunicación bidireccional de actualizaciones de parámetros de configuración entre el objeto de los parámetros de configuración y los componentes.  Si utiliza Visual Studio para crear parámetros de configuración de aplicación y asignarlos a las propiedades de componente, estos enlaces se generarán automáticamente.  
  
 Sólo puede enlazar un parámetro de configuración de aplicación a un componente que admita la interfaz <xref:System.Windows.Forms.IBindableComponent>.  A su vez, el componente debe implementar un evento de cambio para una propiedad enlazada específica, o notificar a los parámetros de configuración que la propiedad ha cambiado a través de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  Si el componente no implementa <xref:System.Windows.Forms.IBindableComponent> y usted enlaza a través de Visual Studio, las propiedades enlazadas se establecerán la primera vez, pero no se actualizarán.  Si el componente implementa <xref:System.Windows.Forms.IBindableComponent> pero no admite las notificaciones de cambio de propiedades, el enlace no se actualizará en el archivo de parámetros de configuración cuando cambie la propiedad.  
  
 Algunos componentes de formularios Windows Forms, como <xref:System.Windows.Forms.ToolStripItem>, no admiten enlaces de parámetros de configuración.  
  
### Serialización de los valores de configuración  
 Cuando <xref:System.Configuration.LocalFileSettingsProvider> debe guardar la configuración en el disco, realiza las acciones siguientes:  
  
1.  Utiliza la reflexión para examinar todas las propiedades definidas en su clase derivada <xref:System.Configuration.ApplicationSettingsBase>, encontrando aquellos que se aplican con <xref:System.Configuration.ApplicationScopedSettingAttribute> o <xref:System.Configuration.UserScopedSettingAttribute>.  
  
2.  Serializa la propiedad en el disco.  Primero intenta llamar al <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> o <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> en la clase <xref:System.ComponentModel.TypeConverter> asociada del tipo.  Si esto no tiene éxito, en su lugar utiliza la serialización XML.  
  
3.  Determina qué configuración corresponde a cada archivo, basándose en el atributo de la configuración.  
  
 Si implementa su propia clase de parámetros de configuración, puede usar <xref:System.Configuration.SettingsSerializeAsAttribute> para marcar un parámetro de configuración para una serialización binaria o personalizada mediante la enumeración <xref:System.Configuration.SettingsSerializeAs>.  Para obtener más información sobre cómo crear su propia clase de parámetros de configuración en código, vea [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### Ubicaciones del archivo de configuración  
 La ubicación de los archivos `app`.exe.config y *usuario*.config diferirá según cómo se instale la aplicación.  Para una aplicación basada en formularios Windows Forms copiada en el equipo local, `app`.exe.config residirá en el mismo directorio que el directorio base del archivo ejecutable principal de la aplicación, y el archivo *usuario*.config residirá en la ubicación especificada por la propiedad <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=fullName>.  Para una aplicación instalada mediante [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], los dos archivos residirán en el directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] en %raízDeInstalación%\\Documents and Settings\\*nombreDeUsuario*\\Local Settings.  
  
 La ubicación de almacenamiento de estos archivos es diferente a si un usuario habilita perfiles móviles, lo que permite a un usuario definir diferentes configuraciones de aplicación y de Windows cuando utilice otros equipos dentro de un dominio.  En ese caso, tanto las aplicaciones de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] como las que no sean de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] tendrán archivos `app`.exe.config y *usuario*.config almacenados en %raízDeInstalación%\\Documents and Settings\\*nombreDeUsuario*\\Application Data.  
  
 Para obtener más información sobre cómo funciona la característica Configuración de la aplicación con la nueva tecnología de implementación, vea [ClickOnce y configuración de la aplicación](../Topic/ClickOnce%20and%20Application%20Settings.md).  Para obtener más información sobre el Directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], vea [Obtener acceso local o remoto a los datos en aplicaciones ClickOnce](../Topic/Accessing%20Local%20and%20Remote%20Data%20in%20ClickOnce%20Applications.md).  
  
## Configuración de la aplicación y seguridad  
 La configuración de la aplicación está diseñada para trabajar con confianza parcial, un entorno restringido predeterminado en las aplicaciones de Windows Forms hospedadas en la intranet y en Internet.  No es necesario ningún permiso especial más allá de la confianza parcial para utilizar la configuración de la aplicación con el proveedor de configuración predeterminado.  
  
 Cuando los parámetros de configuración de la aplicación se utilizan en una aplicación de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], el archivo `user`.config se almacena en el directorio de datos de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)].  El tamaño del archivo `user`.config de la aplicación no puede superar la cuota de directorio de datos establecida por [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)].  Para obtener más información, vea [ClickOnce y configuración de la aplicación](../Topic/ClickOnce%20and%20Application%20Settings.md).  
  
## Proveedores de valores de configuración personalizados  
 En la arquitectura de la configuración de la aplicación, existe una correspondencia imprecisa entre la clase contenedora de la configuración de la aplicación, derivada de <xref:System.Configuration.ApplicationSettingsBase>, y el proveedor o proveedores de los valores de configuración asociados, derivados de <xref:System.Configuration.SettingsProvider>.  Esta asociación está definida sólo por la clase <xref:System.Configuration.SettingsProviderAttribute> aplicada a la clase contenedora o a sus propiedades individuales.  Si no se especifica un proveedor de valores de configuración, se utiliza el proveedor predeterminado <xref:System.Configuration.LocalFileSettingsProvider>.  Como resultado, esta arquitectura admite la creación y el uso de proveedores de valores de configuración personalizados.  
  
 Por ejemplo, suponga que desea desarrollar y utilizar `SqlSettingsProvider`, un proveedor que almacenará todos los valores de configuración en una base de datos de Microsoft SQL Server.  La clase derivada de <xref:System.Configuration.SettingsProvider> recibiría esta información en su método  `Initialize` como un parámetro de tipo <xref:System.Collections.Specialized.NameValueCollection?displayProperty=fullName>.  A continuación implementaría el método <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> para recuperar los valores de configuración del almacén de datos y <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> para guardarlos.  El proveedor puede usar la <xref:System.Configuration.SettingsPropertyCollection> proporcionada a <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> para determinar el nombre de la propiedad, el tipo y el ámbito, así como cualquier otro atributo de los valores de configuración definidos para esa propiedad.  
  
 El proveedor necesitará implementar una propiedad y un método cuyas implementaciones pueden no ser evidentes.  La propiedad <xref:System.Configuration.SettingsProvider.ApplicationName%2A> es una propiedad abstracta de <xref:System.Configuration.SettingsProvider>; debería programarlo para devolver lo siguiente:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 Su clase derivada también debe implementar un método `Initialize` que no toma ningún argumento y no devuelve ningún valor.  <xref:System.Configuration.SettingsProvider> no define este método.  
  
 Finalmente, implemente <xref:System.Configuration.IApplicationSettingsProvider> en el proveedor para proporcionar compatibilidad con la actualización de los valores de configuración, revertiendo los valores de configuración a los predeterminados y actualizándolos de una versión de la aplicación a otra.  
  
 Una vez implementado y compilado su proveedor, es necesario indicar a su clase de configuración que debe utilizar este proveedor en lugar del predeterminado.  Esto se consigue mediante la clase <xref:System.Configuration.SettingsProviderAttribute>.  Si se aplica a una clase de configuración completa, se utiliza el proveedor para cada valor de configuración que defina la clase; si se aplica a valores de configuración independientes, la arquitectura de la Configuración de la aplicación sólo utiliza ese proveedor para esos valores concretos y <xref:System.Configuration.LocalFileSettingsProvider> para el resto.  El ejemplo de código siguiente muestra cómo indicar a la clase de configuración que utilice su proveedor personalizado.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Se puede llamar a un proveedor simultáneamente desde varios subprocesos, pero siempre se escribe en la misma ubicación de almacenamiento; por tanto, la arquitectura de la configuración de la aplicación sólo creará una única instancia de la clase del proveedor.  
  
> [!IMPORTANT]
>  Debería asegurarse de que su proveedor es seguro para subprocesos y que sólo permite un subproceso al mismo tiempo que escribe en los archivos de configuración.  
  
 El proveedor no necesita ser compatible con todos los atributos de los valores de configuración definidos en el espacio de nombres <xref:System.Configuration?displayProperty=fullName>, aunque debe existir un mínimo de compatibilidad con <xref:System.Configuration.ApplicationScopedSettingAttribute> y <xref:System.Configuration.UserScopedSettingAttribute>, y también debería ser compatible con <xref:System.Configuration.DefaultSettingValueAttribute>.  Para esos atributos que no admite, el proveedor sólo debería enviar un mensaje de error sin notificación, no producir una excepción.  Si la clase de configuración utiliza una combinación de atributos no válida, como aplicar <xref:System.Configuration.ApplicationScopedSettingAttribute> y <xref:System.Configuration.UserScopedSettingAttribute> al mismo valor de configuración, el proveedor debería producir una excepción y detenerse.  
  
## Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 <xref:System.Configuration.LocalFileSettingsProvider>   
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Application Settings for Custom Controls](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)   
 [ClickOnce y configuración de la aplicación](../Topic/ClickOnce%20and%20Application%20Settings.md)   
 [Esquema de la configuración de la aplicación](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)