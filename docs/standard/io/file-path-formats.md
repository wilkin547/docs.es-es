---
title: Formatos de ruta de acceso de archivo en los sistemas Windows
ms.date: 06/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, long paths
- long paths
- path formats, Windows
ms.openlocfilehash: b3510be5d417b555d2db163636eac5ce0c0779e4
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628051"
---
# <a name="file-path-formats-on-windows-systems"></a>Formatos de ruta de acceso de archivo en los sistemas Windows

Los miembros de muchos de los tipos del espacio de nombres <xref:System.IO> incluyen un parámetro `path` que permite especificar una ruta de acceso absoluta o relativa a un recurso de sistema de archivos. Después, esta ruta de acceso se pasa a las [API del sistema de archivos de Windows](/windows/desktop/fileio/file-systems). En este tema se describen los formatos de las rutas de acceso de archivo que se pueden usar en los sistemas Windows.

## <a name="traditional-dos-paths"></a>Rutas de acceso DOS tradicionales

Una ruta de acceso DOS estándar puede constar de tres componentes:

- Una letra de volumen o unidad seguida por el separador de volumen (`:`).
- Un nombre de directorio. El [carácter separador de directorio](<xref:System.IO.Path.DirectorySeparatorChar>) separa los subdirectorios dentro de la jerarquía de directorios anidados.
- Un nombre de archivo opcional. El [carácter separador de directorio](<xref:System.IO.Path.DirectorySeparatorChar>) separa la ruta de acceso y el nombre del archivo.

Si los tres componentes están presentes, la ruta de acceso es absoluta. Si no se especifica la letra de volumen o unidad y el nombre de directorio comienza por el [carácter separador de directorio](<xref:System.IO.Path.DirectorySeparatorChar>), la ruta de acceso es relativa con respecto a la raíz de la unidad actual. En caso contrario, la ruta de acceso es relativa al directorio actual. En la tabla siguiente se muestran algunas rutas de acceso de directorio y archivo posibles.

|Ruta de acceso  |Descripción  |
| -- | -- |
| `C:\Documents\Newsletters\Summer2018.pdf` | Ruta de acceso de archivo absoluta desde la raíz de la unidad C:. |
| `\Program Files\Custom Utilities\StringFinder.exe` | Ruta de acceso absoluta desde la raíz de la unidad actual. |
| `2018\January.xlsx` | Ruta de acceso relativa a un archivo en un subdirectorio del directorio actual. |
| `..\Publications\TravelBrochure.pdf` | Ruta de acceso relativa a un archivo en un directorio del mismo nivel del directorio actual. |
| `C:\Projects\apilibrary\apilibrary.sln` | Ruta de acceso absoluta a un archivo desde la raíz de la unidad C: |
| `C:Projects\apilibrary\apilibrary.sln` | Ruta de acceso relativa desde el directorio actual de la unidad C:. |

> [!IMPORTANT]
> Observe la diferencia entre las dos últimas rutas de acceso. En ambas figura el especificador de volumen opcional (C: en ambos casos), pero la primera comienza por la raíz del volumen especificado, mientras que la segunda, no. Como resultado, la primera es una ruta de acceso absoluta desde el directorio raíz de la unidad C:, mientras que la segunda es una ruta de acceso relativa desde el directorio actual de la unidad C:. El uso de la segunda forma cuando está previsto el de la primera suele ser motivo de errores que implican rutas de acceso de archivo de Windows.

Puede determinar si una ruta de acceso de archivo es un nombre completo (es decir, si la ruta de acceso es independiente del directorio actual y no cambia cuando cambia el directorio actual) mediante una llamada al método <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWthType>. Tenga en cuenta que una ruta de acceso de este tipo puede incluir segmentos de directorio relativos (`.` y `..`) y seguir siendo completa si la ruta de acceso resuelta siempre apunta a la misma ubicación.

En el ejemplo siguiente se muestra la diferencia entre las rutas de acceso absolutas y relativas. Se supone que existe el directorio D:\FY2018\ y que aún no ha establecido ningún directorio actual para D:\ desde el símbolo del sistema antes de ejecutar el ejemplo.

[!code-csharp[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/cs/paths.cs)]
[!code-vb[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/vb/paths.vb)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="unc-paths"></a>Rutas de acceso UNC

Las rutas de acceso de convención de nomenclatura universal (UNC), que se usan para acceder a los recursos de red, tienen el formato siguiente:

- Un nombre de servidor o host que va precedido por \\\\. El nombre del servidor puede ser un nombre de equipo NetBIOS o una dirección IP o FQDN (se admiten tanto IPv4 como v6).
- Un nombre de recurso compartido, que se separa del nombre de host mediante \\. Juntos, el nombre del servidor y el del recurso compartido forman el volumen.
- Un nombre de directorio. El [carácter separador de directorio](<xref:System.IO.Path.DirectorySeparatorChar>) separa los subdirectorios dentro de la jerarquía de directorios anidados.
- Un nombre de archivo opcional. El [carácter separador de directorio](<xref:System.IO.Path.DirectorySeparatorChar>) separa la ruta de acceso y el nombre del archivo.

A continuación se muestran algunos ejemplos de rutas de acceso UNC:

|Ruta de acceso  |Descripción  |
| -- | -- |
| `\\system07\C$\` | Directorio raíz de la unidad C: en `system07`. |
| `\\Server2\Share\Test\Foo.txt` | El archivo Foo.txt en el directorio Test del volumen \\\\Server2\\Share.|

Las rutas de acceso UNC siempre deben ser completas. Pueden incluir segmentos de directorio relativos (`.` y `..`), pero estos deben formar parte de una ruta de acceso completa. Solo puede usar rutas de acceso relativas mediante la asignación de una ruta de acceso UNC a una letra de unidad.

## <a name="dos-device-paths"></a>Rutas de acceso de dispositivo DOS

El sistema operativo Windows tiene un modelo de objetos unificado que apunta a todos los recursos, incluidos los archivos. Estas rutas de acceso de objeto son accesibles desde la ventana de consola y se exponen a la capa de Win32 a través de una carpeta especial para vínculos simbólicos a la que se asignan las rutas de acceso DOS y UNC heredadas. A esta carpeta especial se accede a través de la sintaxis de ruta de acceso de dispositivo DOS, que es una de las siguientes:

`\\.\C:\Test\Foo.txt`
`\\?\C:\Test\Foo.txt`

Además de identificar una unidad por su letra de unidad, puede identificar un volumen mediante su GUID de volumen. Esto toma la forma:

`\\.\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`
`\\?\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`

> [!NOTE]
> La sintaxis de ruta de acceso de dispositivo DOS es compatible con las implementaciones de .NET que se ejecutan en Windows a partir de .NET Core 1.1 y .NET Framework 4.6.2.

La ruta de acceso de dispositivo DOS consta de los componentes siguientes:

- El especificador de ruta de acceso de dispositivo (`\\.\` o `\\?\`), que identifica la ruta de acceso como una ruta de acceso de dispositivo DOS.

   > [!NOTE]
   > `\\?\` se admite en todas las versiones de .NET Core y en .NET Framework a partir de la versión 4.6.2.

- Un vínculo simbólico para el objeto de dispositivo "real" (C: en el caso de un nombre de unidad o Volume{b75e2c83-0000-0000-0000-602f00000000} en el caso de un identificador de volumen).

   El primer segmento de la ruta de acceso de dispositivo DOS, una vez que el especificador de ruta de acceso de dispositivo identifica el volumen o la unidad. (Por ejemplo, `\\?\C:\` y `\\.\BootPartition\`).

   Existe un vínculo específico para las UNC que, de forma lógica, se denomina `UNC`. Por ejemplo:

  `\\.\UNC\Server\Share\Test\Foo.txt`
  `\\?\UNC\Server\Share\Test\Foo.txt`

    Para las UNC de dispositivo, la parte del servidor o recurso compartido forma el volumen. Por ejemplo, en `\\?\server1\e:\utilities\\filecomparer\`, la parte del servidor o recurso compartido es server1\utilities. Esto es importante cuando se llama a un método como <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> con segmentos de directorio relativos, pues nunca se puede ir más allá del volumen.

Por definición, las rutas de acceso de dispositivo DOS son completas. No se permiten los segmentos de directorio relativos (`.` y `..`). Los directorios actuales nunca entran en uso.

## <a name="example-ways-to-refer-to-the-same-file"></a>Ejemplo: Formas de hacer referencia al mismo archivo

En el ejemplo siguiente se muestran algunas formas de hacer referencia a un archivo cuando se usan las API del espacio de nombres <xref:System.IO>. En el ejemplo se crea una instancia de un objeto <xref:System.IO.FileInfo> y se usan sus propiedades <xref:System.IO.FileInfo.Name> y <xref:System.IO.FileInfo.Length> para mostrar el nombre y la longitud del archivo.

[!code-csharp[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/cs/file-refs.cs)]
[!code-vb[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/vb/file-refs.vb)]

## <a name="path-normalization"></a>Normalización de la ruta de acceso

Casi todas las rutas de acceso que se pasan a las API de Windows se normalizan. Durante la normalización, Windows realiza los pasos siguientes:

- Identifica la ruta de acceso.
- Aplica el directorio actual a rutas de acceso parciales (relativas).
- Aplica formato canónico a los separadores de componentes y directorios.
- Evalúa los componentes de directorio relativos (`.` para el directorio actual y `..` para el directorio principal).
- Recorta determinados caracteres.

Esta normalización se produce de manera implícita, pero se puede realizar de forma explícita mediante una llamada al método <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType>, que encapsula una llamada a la [función GetFullPathName()](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea). También se puede llamar directamente a la [función GetFullPathName()](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) de Windows mediante P/Invoke.

### <a name="identifying-the-path"></a>Identificación de la ruta de acceso

El primer paso de la normalización de la ruta de acceso consiste en identificar el tipo de ruta de acceso. Las rutas de acceso se incluyen en una de estas categorías:

- Son rutas de acceso de dispositivo; es decir, comienzan con dos separadores y un signo de interrogación o un punto (`\\?` o `\\.`).
- Son rutas de acceso UNC, es decir, comienzan por dos separadores sin un signo de interrogación o un punto.
- Son rutas de acceso DOS completas, es decir, comienzan por una letra de unidad, un separador de volumen y un separador de componentes (`C:\`).
- Designan un dispositivo heredado (`CON`, `LPT1`).
- Son relativas a la raíz de la unidad actual; es decir, comienzan con un único separador de componente (`\`).
- Son relativas al directorio actual de una unidad especificada, es decir, comienzan por una letra de unidad, un separador de volumen y ningún separador de componente (`C:`).
- Son relativas al directorio actual, es decir, comienzan por cualquier otro elemento (`temp\testfile.txt`).

El tipo de la ruta de acceso determina si se aplica o no un directorio actual de alguna manera. También determina lo que es la "raíz" de la ruta de acceso.

### <a name="handling-legacy-devices"></a>Control de dispositivos heredados

Si la ruta de acceso es un dispositivo DOS heredado como `CON`, `COM1` o `LPT1`, se convierte en una ruta de acceso de dispositivo mediante la anteposición `\\.\` y se devuelve.

Una ruta de acceso que comienza por un nombre de dispositivo heredado se interpreta siempre como un dispositivo heredado por el método <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType>. Por ejemplo la ruta de acceso de dispositivo DOS para `CON.TXT` es `\\.\CON`, y la de `COM1.TXT\file1.txt` es `\\.\COM1`.

### <a name="applying-the-current-directory"></a>Aplicación del directorio actual

Si una ruta de acceso no es completa, Windows le aplica el directorio actual. El directorio actual no se aplica a las rutas de acceso de dispositivo y UNC. Ni tampoco una unidad completa con separador C:\\.

Si la ruta de acceso comienza por un único separador de componente, se aplica la unidad desde el directorio actual. Por ejemplo, si la ruta de acceso de archivo es `\utilities` y el directorio actual es `C:\temp\`, la normalización genera `C:\utilities`.

Si la ruta de acceso comienza por una letra de unidad, el separador de volumen y ningún separador de componente, se aplica el último directorio actual establecido desde el shell de comandos para la unidad especificada. Si no se estableció el último directorio actual, solo se aplica la unidad. Por ejemplo, si la ruta de acceso de archivo es `D:sources`, el directorio actual es `C:\Documents\` y el último directorio actual en la unidad D: era `D:\sources\`, el resultado es `D:\sources\sources`. Estas rutas de acceso "relativas a la unidad" son un origen común de errores lógicos de programas y scripts. Asumir que una ruta de acceso que comienza con una letra y dos puntos no es relativa evidentemente no es correcto.

Si la ruta de acceso comienza por un valor distinto de un separador, se aplican la unidad y el directorio actuales. Por ejemplo, si la ruta de acceso es `filecompare` y el directorio actual es `C:\utilities\`, el resultado es `C:\utilities\filecompare\`.

> [!IMPORTANT]
> El uso de rutas de acceso relativas en las aplicaciones multiproceso (es decir, en la mayoría de aplicaciones) es peligroso, porque el directorio actual es un valor de cada proceso. Cualquier subproceso puede cambiar el directorio actual en cualquier momento. A partir de .NET Core 2.1, se puede llamar al método <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> para obtener una ruta de acceso absoluta a partir de una ruta de acceso relativa y la ruta de acceso base (el directorio actual) sobre la que se quiere resolver.

### <a name="canonicalizing-separators"></a>Asignación canónica de separadores

Todas las barras diagonales (`/`) se convierten en el separador estándar de Windows, que es la barra diagonal inversa (`\`). Si están presentes, una serie de barras diagonales que siguen a las dos primeras barras diagonales se contraen en una sola barra diagonal.

### <a name="evaluating-relative-components"></a>Evaluación de componentes relativos

Cuando se procesa la ruta de acceso, se evalúan los componentes o segmentos que se componen de un punto o un punto doble (`.` o `..`):

- Para un punto, se quita el segmento actual, ya que hace referencia al directorio actual.

- Para un punto doble, se quitan el segmento actual y el principal, ya que el punto doble hace referencia al directorio principal.

   Los directorios principales solo se quitan si no están después de la raíz de la ruta de acceso. La raíz de la ruta de acceso depende del tipo de ruta de acceso. Es la unidad (`C:\`) para las rutas de acceso DOS, el servidor o recurso compartido para las UNC (`\\Server\Share`), y el prefijo de ruta de acceso de dispositivo para las rutas de acceso de dispositivo (`\\?\` o `\\.\`).

### <a name="trimming-characters"></a>Recorte de caracteres

Junto con las ejecuciones de los separadores y segmentos relativos que se han quitado anteriormente, durante la normalización se quitan algunos caracteres adicionales:

- Si un segmento termina en un punto, se quita ese punto. (Un segmento de un punto o un punto doble se normaliza en el paso anterior. Un segmento de tres o más puntos no se normaliza y, en realidad, es un nombre de archivo o directorio válido).

- Si la ruta de acceso no termina en un separador, se quitan todos los puntos y espacios finales (U+0020). Si el último segmento es simplemente un punto o un punto doble, se aplica la regla anterior de componentes relativos.

   Esta regla significa que se puede crear un nombre de directorio con un espacio final si se agrega un separador final después del espacio.

   > [!IMPORTANT]
   > **Nunca** se debe crear un nombre de archivo o directorio con un espacio final. Los espacios finales pueden dificultar o impedir el acceso a un directorio, y se suelen producir errores en las aplicaciones cuando se intenta controlar directorios o archivos con nombres que incluyen espacios.

## <a name="skipping-normalization"></a>Omisión de la normalización

Normalmente, todas las rutas de acceso que se pasan a una API de Windows se pasan (de forma efectiva) a la [función GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) y se normalizan. Hay una excepción importante: una ruta de acceso de dispositivo que comienza con un signo de interrogación en lugar de un punto. A menos que la ruta de acceso comience exactamente con `\\?\` (observe el uso de la barra diagonal inversa canónica), se normaliza.

¿Por qué querría omitir la normalización? Hay tres razones principales:

1. Para obtener acceso a las rutas de acceso que normalmente no están disponibles pero que son válidas. A un archivo o directorio denominado `hidden.`, por ejemplo, no se puede acceder de otra forma.

1. Para mejorar el rendimiento omitiendo la normalización, si ya se ha normalizado.

1. Solo en .NET Framework, para omitir la comprobación `MAX_PATH` de la longitud de ruta de acceso para permitir rutas de acceso que tienen más de 259 caracteres. En la mayoría de API se permite esto, con algunas excepciones.

> [!NOTE]
> En .NET Core las rutas de acceso largas se administran de forma implícita y no se realiza una comprobación `MAX_PATH`. La comprobación `MAX_PATH` solo se aplica a .NET Framework.

La omisión de la normalización y las comprobaciones de ruta de acceso máximas es la única diferencia entre las dos sintaxis de ruta de acceso de dispositivo. En los demás casos son idénticas. Tenga cuidado al omitir la normalización, dado que es muy fácil crear rutas de acceso difíciles de controlar para las aplicaciones "normales".

Las rutas de acceso que empiezan por `\\?\` se siguen normalizando si se pasan de forma explícita a la [función GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).

Puede pasar rutas de acceso de más de `MAX_PATH` caracteres a [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) sin `\\?\`. Admite rutas de acceso de longitud arbitraria hasta el tamaño de cadena máximo admitido por Windows.

## <a name="case-and-the-windows-file-system"></a>Las mayúsculas y minúsculas y el sistema de archivos de Windows

Una peculiaridad del sistema de archivos de Windows que resulta confuso para los usuarios y desarrolladores que no usan Windows es que los nombres de ruta de acceso y directorio no distinguen mayúsculas de minúsculas. Es decir, los nombres de archivos y directorios reflejan las mayúsculas y minúsculas de las cadenas que se usan cuando se crean. Por ejemplo, la llamada al método

```csharp
Directory.Create("TeStDiReCtOrY");
```

```vb
Directory.Create("TeStDiReCtOrY")
```

crea un directorio denominado TeStDiReCtOrY. Si modifica el nombre de un directorio o archivo para cambiar sus mayúsculas y minúsculas, el nombre del directorio o archivo refleja las mayúsculas y minúsculas de la cadena usada al cambiar el nombre. Por ejemplo, en el código siguiente se cambia el nombre de un archivo de test.txt a Test.txt:

[!code-csharp[case-and-renaming](~/samples/snippets/standard/io/file-names/cs/rename.cs)]
[!code-vb[case-and-renaming](~/samples/snippets/standard/io/file-names/vb/rename.vb)]

Pero las comparaciones de nombre de directorio y archivo no distinguen mayúsculas de minúsculas. Si busca un archivo denominado "test.txt", las API del sistema de archivos de .NET ignoran las mayúsculas y minúsculas en la comparación. Test.txt, TEST.TXT, test.TXT y cualquier otra combinación de letras mayúsculas y minúsculas coincidirán con "test.txt".
