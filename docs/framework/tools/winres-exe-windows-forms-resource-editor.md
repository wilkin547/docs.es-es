---
title: Winres.exe (Editor de recursos para localización de Windows)
description: Use Winres.exe, el Editor de recursos para localización de Windows. Esta herramienta de diseño visual ayuda a los expertos en localización a localizar los recursos de la interfaz de usuario de Windows Forms que se usan en los formularios.
ms.date: 08/15/2018
helpviewer_keywords:
- Winres.exe
- Windows Forms Resource Editor
- Windows Resource Localization Editor
- localization
- Windows Forms, localization
- forms, localizing
- resx files
- .resx files
ms.assetid: cb8bc835-9221-4888-af53-1a4f5fad6c48
ms.openlocfilehash: 35d1324d5ea7a72ffd5ea594530d1312e717cd7c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543230"
---
# <a name="winresexe-windows-resource-localization-editor"></a>Winres.exe (Editor de recursos para localización de Windows)

El Editor de recursos para localización de Windows, Winres.exe, es una herramienta de diseño visual que ayuda a los expertos en localización a traducir los recursos de la interfaz de usuario (IU) de Windows Forms que usan los formularios. Los archivos .resx o .resources que se utilizan como entrada en Winres.exe se pueden crear mediante un entorno de diseño visual como Microsoft Visual Studio. Para obtener información sobre cómo implementar recursos en aplicaciones .NET Framework, vea [Recursos en aplicaciones .NET](../resources/index.md).

Winres.exe se instala con Visual Studio. Para ejecutar la herramienta, use el Símbolo del sistema para desarrolladores de Visual Studio. Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

## <a name="syntax"></a>Sintaxis

```console
winres resourceFile
winres /?
```

## <a name="arguments"></a>Argumentos

|Argumento|Descripción|
|--------------|-----------------|
|`resourceFile`|Archivo de recursos que se va a adaptar. Este archivo debe ser un archivo .resx o .resources de Windows Forms generado por el diseñador de Visual Studio. Winres.exe no puede abrir archivos .resx o .resources genéricos.|

|Opción|Descripción|
|------------|-----------------|
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|

## <a name="remarks"></a>Comentarios

El estado de los elementos de la interfaz de usuario de un formulario de un proyecto de Windows Forms se almacena generalmente en archivos de recursos, que pueden ser archivos basados en XML con la extensión .resx o las correspondientes versiones binarias compiladas con la extensión .resources. Winres.exe es una herramienta que permite editar de manera limitada cualquier tipo de archivo fuera del entorno de diseño de Visual Studio. Específicamente, permite las siguientes operaciones de edición:

- Se pueden editar archivos de recursos de referencia cultural neutros o específicos para cambiar las propiedades de la interfaz de usuario del formulario o de sus controles, como el texto, el tamaño o la posición.

- Los recursos de archivos de referencia cultural neutros o específicos se pueden generar a partir del archivo de recursos predeterminado.

- Un archivo de recursos de referencia cultural se puede guardar como otro archivo de recursos de referencia cultural. Por ejemplo, se puede guardar un archivo de recursos de inglés (EE. UU.) como un archivo de recursos de polaco. Normalmente, el nuevo archivo se editaría más adelante para admitir la nueva referencia cultural.

Vea también [Organización jerárquica de recursos para la localización](/previous-versions/visualstudio/visual-studio-2012/756hydy4(v=vs.110)) u [Organización jerárquica de recursos para la localización](/previous-versions/visualstudio/visual-studio-2013/756hydy4(v=vs.120)).

Winres.exe no puede convertir un archivo .resx en el archivo .resources correspondiente; en su lugar, utilice la herramienta Resgen.exe. Para obtener más información sobre Resgen.exe, vea [Resgen.exe (Generador de archivos de recursos)](resgen-exe-resource-file-generator.md).

Winres.exe es una aplicación gráfica que vuelve a crear una versión en tiempo de diseño de un formulario de Windows Forms a partir del archivo de recursos, sin tener acceso al código fuente. Winres.exe hospeda el **Diseñador de Windows Forms** y la ventana **Propiedades** de Visual Studio. Estas características permiten la edición visual de archivos .resources o .resx que contengan un formulario de Windows Forms. Generalmente, los localizadores utilizan Winres.exe para editar etiquetas de control y ajustar la ubicación y el tamaño de los mismos a fin de organizar las etiquetas según la referencia cultural de destino.

Si Winres.exe no puede resolver el tipo de un control, crea un control de marcador de posición en el archivo .resx o .resources adaptado. El control de marcador de posición aparece en el formulario de Windows Forms como una ventana sombreada. El tamaño y la posición de la ventana sombreada coinciden con los del control real. Todas las propiedades adaptables disponibles para el control de marcador de posición aparecen en la ventana **Propiedades**. Los cambios que se realicen en el control de marcador de posición se guardan en el control real.

## <a name="winresexe-versus-visual-studio"></a>Comparación entre Winres.exe y Visual Studio

En general, antes de empezar a adaptar los formularios de Windows Forms de una aplicación, se debe decidir si se desea utilizar Visual Studio o Winres.exe como herramienta de localización. La compatibilidad de la versión, como se describe posteriormente, puede impedir que se cambie de una herramienta a otra.

Visual Studio tiene la ventaja de que se puede utilizar tanto para desarrollar una aplicación como para adaptarla. Para adaptar un formulario, una vez completado su desarrollo, establezca la propiedad <xref:System.ComponentModel.LocalizableAttribute> del formulario (la propiedad **Localizable** en el **Editor de propiedades**) en `true` y cambie la propiedad **Language** a la referencia cultural de destino que quiera. A continuación, edite las cadenas y ajuste la ubicación y el tamaño de los controles para que las cadenas quepan en ellos dependiendo de la referencia cultural de destino. Cuando se guarda el archivo .resx adaptado, Visual Studio escribe en el mismo solo las propiedades localizables (propiedades que han cambiado en la referencia cultural de destino). Visual Studio crea automáticamente un ensamblado satélite para el archivo .resx adaptado en la ubicación de directorio correcta.

Aunque Visual Studio proporciona un entorno de desarrollo y de localización integrado, Winres.exe es la herramienta que se recomienda utilizar si otros localizadores van a realizar la localización. Como Winres.exe es solo una herramienta de localización, proporciona una separación más nítida entre el código de una aplicación y los formularios que se van a adaptar, lo que resulta más práctico para la administración de proyectos grandes.

## <a name="using-winresexe"></a>Uso de Winres.exe

Para adaptar mediante Winres.exe, primero se debe desarrollar una aplicación con un diseñador visual, como el **Diseñador de Windows Forms** de Visual Studio. Una vez completado el desarrollo, establezca la propiedad <xref:System.ComponentModel.LocalizableAttribute> del formulario (la propiedad **Localizable** en el **Editor de propiedades**) en `true` y, después, transfiera el archivo .resx de la referencia cultural predeterminada a un localizador de terceros. El archivo .resx contiene información adicional que Winres.exe usa para crear una nueva versión en tiempo de diseño del formulario original.

> [!NOTE]
> Winres.exe no se puede utilizar para editar el archivo de recursos predeterminado. Winres.exe interpreta todas las propiedades cambiadas como propiedades adaptadas y las guarda en el archivo de recursos de la referencia cultural de destino.

Las versiones finales de los archivos de recursos de referencia cultural se pueden utilizar para crear versiones localizadas de la aplicación. Para obtener más información, vea [Recursos en aplicaciones .NET](../resources/index.md).

Winres.exe incluye las siguientes características y funciones:

- Winres puede funcionar en modo de un solo archivo (SFM) o en modo de archivo de Visual Studio (VSFM). SFM es el modo heredado donde la información completa sobre el formulario y su contenido se almacena en el archivo de recursos. VSFM solo almacena los cambios culturales en el archivo de recursos.

- Una ventana de informe de errores, acoplada en la parte inferior izquierda de la ventana principal.

- Se pueden buscar duplicados de las teclas de acceso rápido: en el menú **Formato**, haga clic en el comando **Comprobar las teclas de acceso rápido**.

## <a name="version-compatibility"></a>Compatibilidad de versiones

Debe utilizar la versión de Winres.exe que se comercializó con la versión de .NET Framework que vaya a utilizar. En la siguiente tabla se identifican las versiones compatibles:

|Programa para la mejora|.NET Framework|Winres.exe|
|-------------------|--------------------|----------------|
|Visual Studio .NET 2002|1.0|1.0|
|Visual Studio .NET 2003|1.1|1.1|
|Visual Studio 2005|2.0|2.0|
|Visual Studio 2008|3.0 y 3.5|3.0 y 3.5|
|Visual Studio 2010|4.0|4.0|
|Visual Studio 2017|4.6|4.6|

> [!NOTE]
> Aunque VSFM tiene la ventaja de ser compatible con Visual Studio, ya que almacena solo los valores que han cambiado en el archivo de recursos, Winres.exe requiere que los elementos primarios del archivo de recursos actual se encuentren en el mismo directorio. Por ejemplo, para editar `TestApp.de-DE.resources`, un archivo de recursos de alemán de Alemania, se requiere la presencia del archivo de recursos predeterminado, `TestApp.resx`, y posiblemente el archivo de recursos de referencias culturales neutras, `TestApp.de.resources`.

## <a name="examples"></a>Ejemplos

### <a name="to-localize-a-resx-or-resources-file-associated-with-a-form"></a>Cómo adaptar un archivo .resx o .resources asociado a un formulario

1. Escriba `winres` en el símbolo del sistema para desarrolladores para ejecutar Winres.exe.

2. Para abrir los recursos predeterminados de un formulario que quiera adaptar, haga clic en el comando **Abrir** del menú **Archivo** y navegue hasta el archivo que quiera abrir.

     o bien

     Especifique el archivo que desee abrir en la línea de comandos al iniciar Winres.exe.

     El siguiente comando inicia Winres.exe y carga el formulario asociado a `TestApp.resx` en el diseñador de formularios.

    ```console
    winres TestApp.resx
    ```

     El siguiente comando inicia Winres.exe y carga el formulario asociado a `TestApp.resources` en el diseñador de formularios.

    ```console
    winres TestApp.resources
    ```

    > [!NOTE]
    > Si el formulario cuyos recursos va a editar es un formulario heredado, tanto el ensamblado que contiene el formulario heredado como el que contiene el formulario que hereda (derivado) deben estar registrados en la caché global de ensamblados (GAC), o deben residir en el mismo directorio que WinRes.exe. Para obtener más información sobre cómo instalar componentes de .NET Framework en la caché global de ensamblados, vea [Global Assembly Cache](../app-domains/gac.md) (Caché global de ensamblados).

3. Seleccione los controles en el formulario y cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> y otras propiedades para reflejar la referencia cultural adaptada y su lenguaje. Desplace o cambie el tamaño de los controles según sea necesario para que quepa el texto adaptado.

4. Para guardar la versión adaptada del archivo .resx o .resources, haga clic en el icono **Guardar** o en el mismo comando en el menú **Archivo**. En la herramienta se mostrará la ventana **Seleccionar referencia cultural**.

5. Seleccione la referencia cultural adecuada y el modo de archivo y haga clic en **Aceptar**.

   La herramienta guardará el archivo con la convención de nomenclatura que el motor en tiempo de ejecución espera para los archivos de recursos adaptados. Por ejemplo, si adapta `TestApp.resources` para alemán de Alemania, la herramienta guardará el archivo como `TestApp.de-DE.resources`. Si adapta `TestApp.resx` para alemán de Alemania, la herramienta guardará el archivo como `TestApp.de-DE.resx`. Para obtener más información sobre las convenciones de nomenclatura de recursos, vea [Empaquetado e implementación de recursos en aplicaciones .NET](../resources/packaging-and-deploying-resources-in-desktop-apps.md). Para obtener una lista de los nombres de referencias culturales predefinidos que usa el tiempo de ejecución, vea la clase <xref:System.Globalization.CultureInfo>.

## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.LocalizableAttribute>
- <xref:System.Globalization.CultureInfo>
- <xref:System.Resources.ResourceManager>
- <xref:System.Resources.ResourceReader>
- <xref:System.Resources.ResourceWriter>
- [Herramientas](index.md)
- [Recursos de aplicaciones de escritorio](../resources/index.md)
- [Globalización y localización](../../standard/globalization-localization/index.md)
