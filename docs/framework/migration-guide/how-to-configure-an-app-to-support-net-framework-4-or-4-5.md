---
title: Procedimiento Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores
ms.date: 03/30/2017
helpviewer_keywords:
- configuring apps to support .NET Framework
- .NET Framework, configuring apps
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
ms.openlocfilehash: 586f39fc9b50dcd45bb959ebd0063e3c38d9c3ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716245"
---
# <a name="how-to-configure-an-app-to-support-net-framework-4-or-later-versions"></a>Procedimiento Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores

Todas las aplicaciones que hospedan Common Language Runtime (CLR) necesitan iniciar o *activar* CLR para ejecutar código administrado. Normalmente, una aplicación de .NET Framework se ejecuta en la versión de CLR en la que se compiló, pero puede cambiar este comportamiento para las aplicaciones de escritorio mediante un archivo de configuración de la aplicación (que suele recibir el nombre de archivo app.config). Sin embargo, no puede cambiar el comportamiento predeterminado de activación para las aplicaciones de la Tienda Windows o Windows Phone mediante un archivo de configuración de la aplicación. En este artículo se explica cómo permitir que la aplicación de escritorio se ejecute en otra versión de .NET Framework y se proporciona un ejemplo de cómo establecer la versión 4 o versiones posteriores como destino.

 La versión de .NET Framework en la que se ejecuta una aplicación se determina en el orden siguiente:

- Archivo de configuración.

     Si el archivo de configuración de la aplicación incluye entradas [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) que especifican una o varias versiones de .NET Framework y una de estas versiones está presente en el equipo del usuario, la aplicación se ejecuta en esa versión. El archivo de configuración lee las entradas [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) en el orden en que aparecen y utiliza la primera versión de .NET Framework de la lista que esté presente en el equipo del usuario. (Use el [elemento \<requiredRuntime>](../configure-apps/file-schema/startup/requiredruntime-element.md) para la versión 1.0.).

- Versión compilada.

     Si no hay ningún archivo de configuración pero la versión de .NET Framework en la que se compiló la aplicación está presente en el equipo del usuario, la aplicación se ejecuta en esa versión.

- Última versión instalada.

     Si la versión de .NET Framework en la que se compiló la aplicación no está presente y el archivo de configuración no especifica ninguna versión en el [elemento \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md), la aplicación intenta ejecutarse en la última versión de .NET Framework que esté presente en el equipo del usuario.

     Sin embargo, las aplicaciones de .NET Framework 1.0, 1.1, 2.0, 3.0 y 3.5 no se ejecutan automáticamente en .NET Framework 4 o posterior, y en algunos casos, puede que aparezca un error y que se le solicite instalar .NET Framework 3.5. El comportamiento de activación también puede depender del sistema operativo del usuario, ya que las distintas versiones del sistema Windows incluyen diferentes versiones de .NET Framework. Si la aplicación admite .NET Framework 3.5 y 4 o posterior, es recomendable que lo indique con varias entradas en el archivo de configuración para evitar errores de inicialización de .NET Framework. Para más información, vea [Versiones y dependencias](versions-and-dependencies.md).

 Tal vez quiera también configurar las aplicaciones .NET Framework 3.5 para que se ejecuten en .NET Framework 4 o versiones posteriores, incluso en equipos que tengan instalado .NET Framework 3.5, para aprovechar las mejoras de rendimiento de las versiones 4 y posteriores.

> [!IMPORTANT]
> Se recomienda probar siempre la aplicación en cada versión de .NET Framework admitida. Vea [Compatibilidad de versiones](version-compatibility.md) para obtener información sobre cómo actualizar la aplicación para admitir versiones posteriores de .NET Framework.

 Para obtener información sobre cómo modificar las aplicaciones de .NET Framework 1.0 y 1.1 para admitir Windows 7 y Windows 8, vea [Migrar desde .NET Framework 1.1](migrating-from-the-net-framework-1-1.md).

## <a name="to-configure-your-app-to-run-on-the-net-framework-4-or-later-versions"></a>Para configurar la aplicación para que se ejecute en .NET Framework 4 o versiones posteriores

1. Agregue o busque el archivo de configuración del proyecto de .NET Framework. El archivo de configuración de una aplicación está en el mismo directorio y tiene el mismo nombre que la aplicación, pero su extensión es .config. Por ejemplo, en el caso de una aplicación denominada MiEjecutable.exe, el nombre del archivo de configuración sería MiEjecutable.exe.config.

     Para agregar un archivo de configuración, en la barra de menús de Visual Studio, elija **Proyecto**, **Agregar nuevo elemento**. Elija **General** en el panel izquierdo y después elija **Archivo de configuración**. Asigne al archivo de configuración el nombre *appName*.exe.config. Estas opciones de menú no están disponibles para los proyectos de aplicaciones de la Tienda Windows o Windows Phone, ya que no se puede cambiar la directiva de activación de estas plataformas.

2. Agregue el elemento [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) de la forma siguiente al archivo de configuración de la aplicación:

    ```xml
    <configuration>
      <startup>
        <supportedRuntime version="<version>"/>
      </startup>
    </configuration>
    ```

     donde *\<version>* especifica la versión de CLR correspondiente a la versión de .NET Framework que admite la aplicación. Use las siguientes cadenas:

    - .NET Framework 1.0: "v1.0.3705"

    - .NET Framework 1.1: "v1.1.4322"

    - .NET Framework 2.0, 3.0 y 3.5: "v2.0.50727"

    - .NET Framework 4 y versiones posteriores: "v4.0"

     Puede agregar varios elementos [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md), indicados por orden de preferencia, para especificar la compatibilidad con varias versiones de .NET Framework.

 En la tabla siguiente se muestra cómo los valores del archivo de configuración de la aplicación y las versiones de .NET Framework instaladas en un equipo determinan la versión en la que se ejecuta una aplicación .NET Framework 3.5. Los ejemplos son específicos de una aplicación de .NET Framework 3.5, pero puede utilizar la misma lógica para aplicaciones compiladas con versiones anteriores de .NET Framework. Observe que el número de versión de .NET Framework 2.0 (v2.0.50727) se usa para especificar .NET Framework 3.5 en el archivo de configuración de la aplicación.

|Valores del archivo app.config|En un equipo con la versión 3.5 instalada|En un equipo con las versiones 3.5 y 4 o posteriores instaladas|En un equipo con la versión 4 o posteriores instaladas|
|-|-|-|-|
|None|Se ejecuta en la versión 3.5|Se ejecuta en la versión 3.5|Muestra un mensaje de error en el que se le pide al usuario que instale la versión correcta*|
|`<supportedRuntime version="v2.0.50727"/>`|Se ejecuta en la versión 3.5|Se ejecuta en la versión 3.5|Muestra un mensaje de error en el que se le pide al usuario que instale la versión correcta*|
|`<supportedRuntime version="v2.0.50727"/>` <br /> `<supportedRuntime version="v4.0"/>`|Se ejecuta en la versión 3.5|Se ejecuta en la versión 3.5|Se ejecuta en la versión 4 o posteriores|
|`<supportedRuntime version="v4.0"/>` <br /> `<supportedRuntime version="v2.0.50727"/>`|Se ejecuta en la versión 3.5|Se ejecuta en la versión 4 o posteriores|Se ejecuta en la versión 4 o posteriores|
|`<supportedRuntime version="v4.0"/>`|Muestra un mensaje de error en el que se le pide al usuario que instale la versión correcta*|Se ejecuta en la versión 4 o posteriores|Se ejecuta en la versión 4 o posteriores|

 \* Para obtener más información sobre este mensaje de error y cómo evitarlo, vea [Errores de inicialización de .NET Framework: Administración de la experiencia del usuario](../deployment/initialization-errors-managing-the-user-experience.md).

## <a name="see-also"></a>Vea también

- [Migración desde .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Guía de migración](index.md)
