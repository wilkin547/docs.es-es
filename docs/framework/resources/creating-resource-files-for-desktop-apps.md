---
title: Creación de archivos de recursos para aplicaciones .NET
description: Cree archivos de recursos para aplicaciones .NET. Compile archivos de texto con recursos de cadena, archivos XML o binarios mediante programación, o archivos XML con datos de cadena, imagen u objeto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resources files
- .resources files
- application resources, creating files
- resource files, creating
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
ms.openlocfilehash: d10af40420c1ab9ab177514c0babeaf5cea96922
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259081"
---
# <a name="create-resource-files-for-net-apps"></a>Creación de archivos de recursos para aplicaciones .NET

Puede incluir recursos, como cadenas, imágenes o datos de objeto, en los archivos de recursos para hacer que estén disponibles fácilmente en su aplicación. .NET Framework ofrece cinco mecanismos para crear archivos de recursos:

- Cree un archivo de texto que contenga recursos de cadena. Puede usar el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para convertir el archivo de texto en un archivo de recursos binario (.resources). Después, puede insertar el archivo de recursos binario en el ejecutable de una aplicación o en una biblioteca de aplicaciones mediante un compilador del lenguaje, o bien puede insertarlo en un ensamblado satélite mediante [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md). Para obtener más información, vea la sección [Recursos en archivos de texto](creating-resource-files-for-desktop-apps.md#TextFiles).

- Cree un archivo de recursos XML (.resx) que contenga una cadena, una imagen o datos de objeto. Puede usar el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para convertir el archivo .resx en un archivo de recursos binario (.resources). Después, puede insertar el archivo de recursos binario en el ejecutable de una aplicación o en una biblioteca de aplicaciones mediante un compilador del lenguaje, o bien puede insertarlo en un ensamblado satélite mediante [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md). Para obtener más información, vea la sección [Recursos en archivos .resx](creating-resource-files-for-desktop-apps.md#ResxFiles).

- Cree un archivo de recursos XML (.resx) mediante programación utilizando los tipos del espacio de nombres <xref:System.Resources>. Puede crear un archivo .resx, enumerar sus recursos y recuperar recursos específicos por nombre. Para obtener más información, vea [Working with .resx Files Programmatically](working-with-resx-files-programmatically.md) (Trabajar con archivos .resx mediante programación).

- Cree un archivo de recursos binario (.resources) mediante programación. Después, puede insertar el archivo en el ejecutable de una aplicación o en una biblioteca de aplicaciones mediante un compilador del lenguaje, o bien puede insertarlo en un ensamblado satélite mediante [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md). Para obtener más información, vea la sección [Recursos en archivos .resources](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

- Use [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) para crear un archivo de recursos e incluirlo en el proyecto. Visual Studio proporciona un editor de recursos que le permite agregar, eliminar y modificar recursos. En tiempo de compilación, el archivo de recursos se convierte automáticamente en un archivo .resources binario y se incrusta en un ensamblado de la aplicación o un ensamblado satélite. Para obtener más información, vea la sección [Archivos de recursos en Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles).

<a name="TextFiles"></a>

## <a name="resources-in-text-files"></a>Recursos en archivos de texto

Puede usar archivos de texto (.txt o .restext) únicamente para almacenar recursos de cadena. Para los recursos que no son de cadena, use archivos .resx o créelos mediante programación. Los archivos de texto que contienen recursos de cadena tienen el siguiente formato:

```text
# This is an optional comment.
name = value

; This is another optional comment.
name = value

; The following supports conditional compilation if X is defined.
#ifdef X
name1=value1
name2=value2
#endif

# The following supports conditional compilation if Y is undefined.
#if !Y
name1=value1
name2=value2
#endif
```

 El formato de archivo de recursos de los archivos .txt y .restext es idéntico. La extensión de archivo .restext solo sirve para permitir que los archivos de texto se identifiquen de forma inmediata como archivos de recursos basados ​​en texto.

 Los recursos de cadena aparecen como pares *name/value*, donde *name* es una cadena que identifica el recurso y *value* es la cadena de recurso que se devuelve al pasar *name* a un método de recuperación de recursos como <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>. *name* y *value* deben separarse mediante el signo igual (=). Por ejemplo:

```text
FileMenuName=File
EditMenuName=Edit
ViewMenuName=View
HelpMenuName=Help
```

> [!CAUTION]
> No utilice archivos de recursos para almacenar contraseñas, información relativa a la seguridad o datos privados.

 Las cadenas vacías (es decir, un recurso cuyo valor es <xref:System.String.Empty?displayProperty=nameWithType>) se permiten en los archivos de texto. Por ejemplo:

```text
EmptyString=
```

 A partir de .NET Framework 4.5 y en todas las versiones de .NET Core, los archivos de texto admiten compilación condicional con las construcciones `#ifdef`*symbol*... `#endif` y `#if !`*symbol*... `#endif`. Se puede usar el modificador `/define` con el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para definir símbolos. Cada recurso requiere su propia construcción `#ifdef`*symbol*... `#endif` o `#if !`*symbol*... `#endif`. Si se usa una instrucción `#ifdef` y se ha definido *symbol*, el recurso asociado se incluye en el archivo .resources. En caso contrario, no se incluye. Si se usa una instrucción `#if !` y no se ha definido *symbol*, el recurso asociado se incluye en el archivo .resources. En caso contrario, no se incluye.

 En los archivos de texto, los comentarios son opcionales y se incluyen al principio de la línea precedidos por un símbolo de punto y coma (;) o un signo de número (#). Las líneas que contienen los comentarios se pueden colocar en cualquier parte del archivo. Los comentarios no se incluirán en un archivo .resources compilado que se crea mediante el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md).

 Las líneas en blanco de los archivos de texto se consideran espacios en blanco y no se tienen en cuenta.

 En el ejemplo siguiente se definen dos recursos de cadena denominados `OKButton` y `CancelButton`.

```text
#Define resources for buttons in the user interface.
OKButton=OK
CancelButton=Cancel
```

 Si el archivo de texto contiene instancias duplicadas de *name*, el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) muestra una advertencia y omite el segundo nombre.

 *value* no puede contener caracteres de nueva línea, pero se pueden usar caracteres de escape del estilo del lenguaje C, como `\n` para representar una línea nueva y `\t` para representar una tabulación. También se puede incluir un carácter de barra diagonal inversa si se añade el carácter de escape (por ejemplo, "\\\\"). Además, se admite el uso de una cadena vacía.

 Guarde los recursos en formato de archivo de texto utilizando la codificación UTF-8 o UTF-16 con el orden de bytes little endian o big endian. Pero el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), que convierte un archivo .txt en un archivo .resources, trata los archivos como UTF-8 de forma predeterminada. Si desea que Resgen.exe reconozca un archivo codificado con UTF-16, es preciso incluir una marca de orden de bytes Unicode (U+FEFF) al principio del archivo.

 Para insertar un archivo de recursos en formato de texto en un ensamblado .NET, debe convertirlo en un archivo de recursos binario (.resources) mediante el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Después, puede insertar el archivo .resources en un ensamblado .NET mediante un compilador del lenguaje o insertarlo en un ensamblado satélite mediante [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md).

 En el siguiente ejemplo se utiliza un archivo de recursos en formato de texto denominado GreetingResources.txt para una sencilla aplicación de consola "Hello World". El archivo de texto define dos cadenas, `prompt` y `greeting`, que solicitan al usuario que escriba su nombre y muestran un saludo.

```text
# GreetingResources.txt
# A resource file in text format for a "Hello World" application.
#
# Initial prompt to the user.
prompt=Enter your name:
# Format string to display the result.
greeting=Hello, {0}!
```

El archivo de texto se convierte en un archivo .resources a través del siguiente comando:

```console
resgen GreetingResources.txt
```

 En el ejemplo siguiente se muestra el código fuente de una aplicación de consola que utiliza el archivo .resources para mostrar mensajes al usuario.

 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]

 Si está utilizando Visual Basic y el archivo de código fuente se denomina Greeting.vb, el siguiente comando crea un archivo ejecutable que incluye el archivo .resources incrustado:

```console
vbc greeting.vb -resource:GreetingResources.resources
```

 Si está utilizando C# y el archivo de código fuente se denomina Greeting.cs, el comando siguiente crea un archivo ejecutable que incluye el archivo .resources incrustado:

```console
csc greeting.cs -resource:GreetingResources.resources
```

<a name="ResxFiles"></a>

## <a name="resources-in-resx-files"></a>Recursos en archivos .resx

 A diferencia de los archivos de texto, que solo pueden almacenar recursos de cadena, los archivos de recursos XML (.resx) pueden almacenar cadenas, datos binarios (como imágenes, iconos y clips de sonido) y objetos de programación. Los archivos .resx contienen un encabezado estándar, en el que se describe el formato de las entradas de los recursos y se especifica la información sobre el control de versiones correspondiente al código XML que se usa para analizar los datos. Los datos del archivo de recursos siguen lo establecido en el encabezado XML. Cada elemento de datos se compone de un par nombre/valor incluido en una etiqueta `data`. Su atributo `name` define el nombre del recurso y la etiqueta `value` anidada contiene el valor del recurso. En el caso de los datos de cadena, la etiqueta `value` contiene la cadena.

 Por ejemplo, la etiqueta `data` siguiente define un recurso de cadena denominado `prompt` cuyo valor es "Enter your name:".

```xml
<data name="prompt" xml:space="preserve">
  <value>Enter your name:</value>
</data>
```

> [!WARNING]
> No utilice archivos de recursos para almacenar contraseñas, información relativa a la seguridad o datos privados.

 En el caso de los objetos de recursos, la etiqueta **data** contiene un atributo `type` que indica el tipo de datos del recurso. En el caso de los objetos que se componen de datos binarios, la etiqueta `data` contiene también un atributo `mimetype`, que indica el tipo `base64` de los datos binarios.

> [!NOTE]
> Todos los archivos .resx utilizan un formateador de serialización binaria para generar y analizar los datos binarios de un tipo especificado. Como resultado, un archivo .resx puede convertirse en un archivo no válido si el formato de serialización binaria de un objeto cambia de manera que sea incompatible.

 En el siguiente ejemplo se muestra una parte de un archivo .resx que contiene un recurso <xref:System.Int32> y una imagen de mapa de bits.

```xml
<data name="i1" type="System.Int32, mscorlib">
  <value>20</value>
</data>

<data name="flag" type="System.Drawing.Bitmap, System.Drawing,
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
    mimetype="application/x-microsoft.net.object.bytearray.base64">
  <value>
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…
  </value>
</data>
```

> [!IMPORTANT]
> Como los archivos .resx deben componerse de código XML con formato correcto y tener un formato predefinido, no resulta recomendable trabajar manualmente con este tipo de archivos, sobre todo cuando contienen recursos que no son cadenas. En cambio, [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) proporciona una interfaz transparente para crear y manipular archivos. resx. Para obtener más información, vea la sección [Archivos de recursos en Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles). También puede crear y manipular archivos .resx mediante programación. Para obtener más información, vea [Working with .resx Files Programmatically](working-with-resx-files-programmatically.md) (Trabajar con archivos .resx mediante programación).

<a name="ResourcesFiles"></a>

## <a name="resources-in-resources-files"></a>Recursos en archivos .resources

Puede usar la clase <xref:System.Resources.ResourceWriter?displayProperty=nameWithType> para crear mediante programación un archivo de recursos binario (.resources) directamente desde el código. También puede usar el [Generador de archivos de recursos (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) para crear un archivo .resources a partir de un archivo de texto o un archivo .resx. El archivo .resources puede contener datos binarios (matrices de bytes) y datos de objeto además de datos de cadena. Al crear un archivo .resources mediante programación, se requieren los siguientes pasos:

1. Cree un objeto <xref:System.Resources.ResourceWriter> con un nombre de archivo único. Puede hacerlo especificando el nombre de archivo o una secuencia de archivos en un constructor de clase <xref:System.Resources.ResourceWriter>.

2. Llame a una de las sobrecargas del método <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=nameWithType> para que cada recurso con nombre se agregue al archivo. El recurso puede ser una cadena, un objeto o una colección de datos binarios (una matriz de bytes).

3. Llame al método <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=nameWithType> para que escriba los recursos en el archivo y cierre el objeto <xref:System.Resources.ResourceWriter>.

> [!NOTE]
> No utilice archivos de recursos para almacenar contraseñas, información relativa a la seguridad o datos privados.

 En el ejemplo siguiente se crea mediante programación un archivo .resources denominado CarResources.resources que almacena seis cadenas, un icono y dos objetos definidos por la aplicación (dos objetos `Automobile`). La clase `Automobile`, que se define y de la que se crean instancias en el ejemplo, está etiquetada con el atributo <xref:System.SerializableAttribute>, lo que permite que el formateador de serialización binaria la mantenga.

 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]

 Después de crear el archivo .resources, puede insertarlo en un ejecutable o una biblioteca en tiempo de ejecución si incluye el modificador `/resource` del compilador del lenguaje o insertarlo en un ensamblado satélite mediante [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md).

<a name="VSResFiles"></a>

## <a name="resource-files-in-visual-studio"></a>Archivos de recursos en Visual Studio

Cuando agrega un archivo de recursos a su proyecto de [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), Visual Studio crea un archivo .resx en el directorio del proyecto. Visual Studio proporciona editores de recursos que permiten agregar cadenas, imágenes y objetos binarios. Dado que los editores están diseñados para administrar únicamente datos estáticos, no se pueden utilizar para almacenar objetos de programación; debe escribir mediante programación los datos de objeto en un archivo .resx o un archivo .resources. Para más información, consulte el tema [Trabajar con archivos .resx mediante programación](working-with-resx-files-programmatically.md) y la sección [Recursos en archivos .resources](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

Si va a agregar recursos localizados, asígneles el mismo nombre de archivo raíz que el archivo de recursos principal. También deberá designar su referencia cultural en el nombre de archivo. Por ejemplo, si agrega un archivo de recursos denominado Resources.resx, también podrá crear los archivos de recursos denominados Resources.en-US.resx y Resources.fr-FR.resx para incluir los recursos localizados en las referencias culturales inglés (Estados Unidos) y francés (Francia), respectivamente. También deberá designar la referencia cultural predeterminada de la aplicación. Esta es la referencia cultural cuyos recursos van a usarse si no se encuentran recursos localizados en una determinada referencia cultural. Para especificar la referencia cultural predeterminada, en el Explorador de soluciones de Visual Studio, haga clic con el botón derecho en el nombre del proyecto, elija Aplicación, haga clic en **Información de ensamblado** y seleccione el idioma o la referencia cultural apropiada en la lista **Idioma neutro**.

En tiempo de compilación, Visual Studio convierte primero los archivos .resx de un proyecto en archivos de recursos binarios (.resources) y los almacena en un subdirectorio del directorio *obj* del proyecto. Visual Studio incrusta los archivos de recursos que no contienen recursos localizados en el ensamblado principal que el proyecto genera. Si los archivos de recursos contienen recursos localizados, Visual Studio los incrusta en un ensamblado satélite distinto para cada referencia cultural localizada. Después, almacena cada ensamblado satélite en un directorio cuyo nombre se corresponde con la referencia cultural localizada. Por ejemplo, los recursos localizados en inglés (Estados Unidos) se almacenan en un ensamblado satélite del subdirectorio en-US.

## <a name="see-also"></a>Vea también

- <xref:System.Resources>
- [Recursos en aplicaciones .NET](index.md)
- [Empaquetar e implementar recursos](packaging-and-deploying-resources-in-desktop-apps.md)
