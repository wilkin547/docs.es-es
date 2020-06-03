---
title: Introducción a la configuración de la aplicación
ms.date: 03/30/2017
f1_keywords:
- ApplicationsSettingsOverview
helpviewer_keywords:
- application settings [Windows Forms], about application settings
- dynamic properties
- user preferences [Windows Forms], tracking
ms.assetid: 0dd8bca5-a6bf-4ac4-8eec-5725d08b38dc
ms.openlocfilehash: 369495322328350bc06827b87598160469d864bb
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307064"
---
# <a name="application-settings-overview"></a>Introducción a la configuración de la aplicación
En este tema se describe cómo crear y almacenar los datos de configuración en nombre de la aplicación y sus usuarios.

 La característica Configuración de la aplicación de Windows Forms facilita la creación, el almacenamiento y el mantenimiento de las preferencias personalizadas de usuarios y aplicaciones en el equipo cliente. Con Configuración de la aplicación de Windows Forms, no solo puede almacenar datos de las aplicaciones, como cadenas de conexión a bases de datos, sino también datos específicos de los usuarios, como las preferencias de la aplicación de un usuario. Con Visual Studio o código administrado personalizado, puede crear una nueva configuración, leerla y escribirla en el disco, enlazarla a propiedades de los formularios y validar los datos de configuración antes de cargarlos y guardarlos.

 La configuración de la aplicación permite a los desarrolladores guardar el estado en su aplicación con muy poco código personalizado, y sustituye a las propiedades dinámicas de las versiones anteriores del .NET Framework. Configuración de la aplicación ofrece muchas mejoras en comparación con las propiedades dinámicas, que son de solo lectura, se enlazan en tiempo de ejecución y requieren más programación personalizada. Las clases de propiedades dinámicas se han conservado en .NET Framework 2,0, pero solo son clases de Shell que ajustan finos las clases de configuración de la aplicación.

## <a name="what-are-application-settings"></a>¿Qué es Configuración de la aplicación?
 Las aplicaciones de Windows Forms, a menudo, requieren datos que son esenciales para ejecutar la aplicación, pero que no quiere incluir directamente en el código de la aplicación. Si la aplicación utiliza un servicio Web o un servidor de bases de datos, puede que le convenga almacenar esta información en un archivo independiente, para poder cambiarla en el futuro sin tener que volver a compilarla. De manera similar, puede que las aplicaciones necesiten almacenar datos específicos del usuario actual. La mayoría de las aplicaciones, por ejemplo, tienen preferencias del usuario con las que se personalizan la apariencia y el comportamiento de la aplicación.

 La característica Configuración de la aplicación cubre estas dos necesidades proporcionando una manera sencilla de almacenar tanto la configuración del ámbito del usuario como la del ámbito de la aplicación en el equipo cliente. Con Visual Studio o un editor de código, puede definir una configuración para una propiedad determinada especificando su nombre, el tipo de datos y el ámbito (aplicación o usuario). Incluso puede colocar configuraciones relacionadas en grupos con nombres para simplificar su uso y su legibilidad. Una vez definida, esta configuración se conserva y se lee en la memoria automáticamente en tiempo de ejecución. Una arquitectura acoplable permite cambiar el mecanismo de persistencia, pero de forma predeterminada, se utiliza el sistema de archivos local.

 Configuración de la aplicación funciona mediante la persistencia de los datos en XML para archivos de configuración (.config) diferentes, según si la configuración es del ámbito de la aplicación o del ámbito del usuario. En la mayoría de los casos, la configuración del ámbito de la aplicación es de solo lectura. Dado que es información del programa, lo normal es que no tenga que sobrescribirla. Por el contrario, la configuración del ámbito del usuario se puede leer y escribir de manera segura en tiempo de ejecución, aunque la aplicación se ejecute con confianza parcial. Para obtener más información acerca de la confianza parcial, consulte [Security in Windows Forms Overview](../security-in-windows-forms-overview.md).

 Las configuraciones se almacenan como fragmentos XML en archivos de configuración. La configuración del ámbito de la aplicación se representa con el elemento `<applicationSettings>` y, generalmente, se coloca en *aplicación*.exe.config, donde *aplicación* es el nombre del archivo ejecutable principal. La configuración del ámbito del usuario se representa con el elemento `<userSettings>` y se coloca en *usuario*.config, donde *usuario* es el nombre de usuario de la persona que está ejecutando la aplicación. El archivo *aplicación*.exe.config se debe implementar con la aplicación. La arquitectura de la configuración creará los archivos *usuario*.config según sean necesarios la primera vez que la aplicación guarde la configuración de cada usuario. También puede definir un bloque `<userSettings>` en *aplicación*.exe.config para proporcionar los valores predeterminados de la configuración del ámbito del usuario.

 Los controles personalizados también pueden guardar su propia configuración implementando la interfaz <xref:System.Configuration.IPersistComponentSettings> , que expone el método <xref:System.Configuration.IPersistComponentSettings.SaveSettings%2A> . El control <xref:System.Windows.Forms.ToolStrip> de Windows Forms implementa esta interfaz para guardar la posición de las barras de herramientas y los elementos de las barras de herramientas entre una sesión de la aplicación y otra. Para obtener más información acerca de los controles personalizados y la configuración de la aplicación, consulte [Application Settings for Custom Controls](application-settings-for-custom-controls.md).

## <a name="limitations-of-application-settings"></a>Limitaciones de Configuración de la aplicación
 No se puede usar la configuración de la aplicación en una aplicación no administrada que hospede el .NET Framework. La configuración no funciona en entornos como los complementos de Visual Studio, C++ para Microsoft Office, el hospedaje de controles en Internet Explorer o los complementos y proyectos de Microsoft Outlook.

 Actualmente, no es posible enlazar a algunas propiedades en Windows Forms. El ejemplo más notable es la propiedad <xref:System.Windows.Forms.Form.ClientSize%2A> : si se enlaza a esta propiedad, puede producirse un comportamiento impredecible en tiempo de ejecución. Normalmente, puede solucionar estos problemas guardando y cargando estas opciones con programación.

 Configuración de la aplicación no tiene ninguna funcionalidad integrada para cifrar la información de forma automática. Nunca debe almacenar información relacionada con la seguridad, como contraseñas de bases de datos, en texto no cifrado. Si quiere almacenar ese tipo de información confidencial, como desarrollador de la aplicación, es usted el responsable de asegurarse de que esté protegida. Si quiere almacenar cadenas de conexión, le recomendamos que utilice la seguridad integrada de Windows y que no recurra a especificar las contraseñas de forma rígida en la dirección URL. Para obtener más información, consulta [Code Access Security and ADO.NET](../../data/adonet/code-access-security.md).

## <a name="getting-started-with-application-settings"></a>Introducción a Configuración de la aplicación
 Si utiliza Visual Studio, puede definir la configuración en el Diseñador de Windows Forms con la propiedad **(ApplicationSettings)** en la ventana **Propiedades** . Al definir la configuración de esta forma, Visual Studio crea automáticamente una clase contenedora administrada personalizada que asocia cada ajuste a una propiedad de clase. Visual Studio también se ocupa de enlazar el ajuste a una propiedad de un formulario o control para que la configuración del control se restaure automáticamente cuando se muestre su formulario y se guarde automáticamente al cerrar el formulario.

 Si quiere controlar la configuración con más precisión, puede definir su propia clase contenedora de configuración de la aplicación personalizada. Para hacerlo, derive una clase de <xref:System.Configuration.ApplicationSettingsBase>, agregue una propiedad que corresponda a cada ajuste y aplique atributos especiales a estas propiedades. Para obtener más información acerca de cómo crear clases contenedoras, consulte [Application Settings Architecture](application-settings-architecture.md).

 También puede utilizar la clase <xref:System.Windows.Forms.Binding> para enlazar la configuración con programación a las propiedades de formularios y controles.

## <a name="see-also"></a>Vea también

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- <xref:System.Configuration.IPersistComponentSettings>
- [Procedimiento para validar la configuración de la aplicación](how-to-validate-application-settings.md)
- [Administrar la configuración de la aplicación (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
- [Cómo leer valores de configuración en tiempo de ejecución con C#](how-to-read-settings-at-run-time-with-csharp.md)
- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Arquitectura de configuración de la aplicación](application-settings-architecture.md)
- [Configuración de la aplicación para controles personalizados](application-settings-for-custom-controls.md)
