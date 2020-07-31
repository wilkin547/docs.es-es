---
title: Gacutil.exe (Herramienta Caché global de ensamblados)
description: Obtenga detalles sobre Gacutil.exe, la herramienta Caché global de ensamblados. Esta herramienta le permite ver y manipular la caché global de ensamblados y la caché de descarga.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- global assembly cache, manipulating contents
- GAC (global assembly cache), Gacutil.exe
- Gacutil.exe
- GAC (global assembly cache), viewing contents
- installing assemblies into global assembly cache
- removing assemblies from global assembly cache
- list of assemblies in global assembly cache
- cache [.NET Framework], global assembly cache
- GAC (global assembly cache), manipulating contents
- global assembly cache, Gacutil.exe
- Global Assembly Cache tool
ms.assetid: 4c7be9c8-72ae-481f-a01c-1a4716806e99
ms.openlocfilehash: 1fe79a09aa99c9d91d8223e7642408a56da20dfe
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166936"
---
# <a name="gacutilexe-global-assembly-cache-tool"></a>Gacutil.exe (Herramienta Caché global de ensamblados)

La herramienta Caché global de ensamblados permite ver y manipular el contenido de la caché global de ensamblados y la memoria caché de descarga.

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

En el símbolo del sistema, escriba lo siguiente:

## <a name="syntax"></a>Sintaxis

```console
gacutil [options] [assemblyName | assemblyPath | assemblyListFile]
```

## <a name="parameters"></a>Parámetros

|Argumento|Descripción|
|--------------|-----------------|
|*assemblyName*|El nombre de un ensamblado. Puede especificar parte del nombre del ensamblado, como `myAssembly`, o puede especificar un nombre de ensamblado completo, como `myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5`.|
|*assemblyPath*|El nombre de un archivo que contiene un manifiesto del ensamblado.|
|*assemblyListFile*|La ruta de acceso a un archivo de texto ANSI donde se enumeran los ensamblados que se van a instalar o desinstalar. Si desea usar un archivo de texto para instalar ensamblados, especifique la ruta de acceso de cada ensamblado en una línea independiente del archivo. La herramienta interpreta las rutas de acceso relativas en relación con la ubicación de *assemblyListFile*. Si desea usar un archivo de texto para desinstalar ensamblados, especifique el nombre completo de cada ensamblado en una línea independiente del archivo. Puede ver algunos ejemplos del contenido de *assemblyListFile* más adelante en este tema.|

|Opción|Descripción|
|------------|-----------------|
|**/cdl**|Elimina el contenido de la memoria caché de descarga.|
|**/f**|Especifique esta opción con las opciones **/i** o **/il** para forzar la reinstalación de un ensamblado. Si ya existe un ensamblado con el mismo nombre en la caché global de ensamblados, la herramienta sobrescribe dicho ensamblado.|
|**/h**[**elp**]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|**/i** *assemblyPath*|Instala un ensamblado en la caché global de ensamblados.|
|**/if**  *assemblyPath*|Instala un ensamblado en la caché global de ensamblados. Si ya existe un ensamblado con el mismo nombre en la caché global de ensamblados, la herramienta sobrescribe dicho ensamblado.<br /><br /> Especificar esta opción equivale a especificar las opciones **/i** y **/f** juntas.|
|**/il** *assemblyListFile*|Instala uno o varios ensamblados especificados en *assemblyListFile* en la caché global de ensamblados.|
|**/ir**  *assemblyPath*<br /><br /> *scheme*<br /><br /> *identificador*<br /><br /> *description*|Instala un ensamblado en la caché global de ensamblados y agrega una referencia para contar el ensamblado. Con esta opción, debe especificar los parámetros *assemblyPath*, *scheme*, *id* y *description*. Para obtener una descripción de los valores válidos que puede especificar para estos parámetros, vea la opción **/r**.<br /><br /> Especificar esta opción equivale a especificar las opciones **/i** y **/r** juntas.|
|**/l** [*assemblyName*]|Enumera el contenido de la caché global de ensamblados. Si especifica el parámetro *assemblyName*, la herramienta solo enumera los ensamblados que coinciden con el nombre.|
|**/ldl**|Enumera el contenido de la memoria caché de archivos descargados.|
|**/lr** [*assemblyName*]|Enumera todos los ensamblados y sus recuentos de referencias correspondientes. Si especifica el parámetro *assemblyName*, la herramienta solo enumera los ensamblados que coinciden con el nombre y sus recuentos de referencias correspondientes.|
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|
|**/r** [*assemblyName &#124; assemblyPath*]<br /><br /> *scheme*<br /><br /> *identificador*<br /><br /> *description*|Especifica una referencia de la que se mantiene un seguimiento a uno o varios ensamblados que se van a instalar o desinstalar. Especifique esta opción con las opciones **/i**, **/il**, **/u** o **/ul**.<br /><br /> Para instalar un ensamblado, especifique los parámetros *assemblyPath*, *scheme*, *id* y *description* con esta opción. Para desinstalar un ensamblado, especifique los parámetros *assemblyName*, *scheme*, *id* y *description*.<br /><br /> Para quitar una referencia a un ensamblado, debe especificar los mismos parámetros *scheme*, *id* y *description* que especificó con las opciones **/i** y **/r** (o **/ir**) al instalar el ensamblado. A la hora de desinstalar un ensamblado, tenga en cuenta que la herramienta también quita el ensamblado de la caché global de ensamblados si se trata de la última referencia que se va a quitar y si Windows Installer no tiene referencias pendientes al ensamblado.<br /><br /> El parámetro *scheme* especifica el tipo de esquema de instalación. Puede especificar uno de los siguientes valores:<br /><br /> - UNINSTALL_KEY: Especifique este valor si el instalador agrega la aplicación a Agregar o quitar programas en Microsoft Windows. Las aplicaciones se agregan por sí mismas a Agregar o quitar programas, ya que agregan una clave del Registro a HKLM\Software\Microsoft\Windows\CurrentVersion.<br />- FILEPATH: Especifique este valor si el instalador no agrega la aplicación a Agregar o quitar programas.<br />- OPAQUE: Especifique este valor si el escenario de instalación no requiere que se proporcione una clave del Registro o una ruta de acceso de archivo. Este valor permite especificar información personalizada para el parámetro *id*.<br /><br /> El valor que hay que especificar para el parámetro *id* depende del valor especificado para el parámetro *scheme*:<br /><br /> - Si especifica UNINSTALL_KEY para el parámetro *scheme*, especifique el nombre de la aplicación establecida en la clave del Registro HKLM\Software\Microsoft\Windows\CurrentVersion. Por ejemplo, si la clave del Registro es HKLM\Software\Microsoft\Windows\CurrentVersion\MyApp, especifique MyApp para el parámetro *id*.<br />- Si especifica FILEPATH para el parámetro *scheme*, especifique la ruta de acceso completa al archivo ejecutable que instala el ensamblado como parámetro *id*.<br />- Si especifica OPAQUE para el parámetro *scheme*, puede proporcionar cualquier dato como parámetro *id*. Los datos que especifique deben ir entre comillas ("").<br /><br /> El parámetro *description* permite especificar texto descriptivo sobre la aplicación que se va a instalar. Esta información se muestra cuando se enumeran las referencias.|
|**/silent**|Suprime la presentación de toda la salida del comando.|
|**/u**  *assemblyName*|Desinstala un ensamblado de la caché global de ensamblados.|
|**/uf**  *assemblyName*|Fuerza la desinstalación de un ensamblado específico mediante la eliminación de todas las referencias a este.<br /><br /> Especificar esta opción equivale a especificar las opciones **/u** y **/f** juntas. **Nota:**  No puede usar esta opción para quitar un ensamblado instalado con Microsoft Windows Installer. Si intenta realizar esta operación, la herramienta muestra un mensaje de error.|
|**/ul** *assemblyListFile*|Desinstala uno o varios ensamblados especificados en *assemblyListFile* de la caché global de ensamblados.|
|**/u**[**ngen**] *assemblyName*|Desinstala el ensamblado especificado de la caché global de ensamblados. Si el ensamblado especificado tiene recuentos de referencias, la herramienta muestra dichos recuentos y no quita el ensamblado de la caché global de ensamblados. **Nota:**  En la versión 2.0 de .NET Framework, no se admite `/ungen`. En su lugar, use el comando `uninstall` de [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md). <br /><br /> En las versiones 1.0 y 1.1 de .NET Framework, si se especifica **/ungen**, Gacutil.exe quita el ensamblado de la memoria caché de imágenes nativas. Esta caché almacena las imágenes nativas de los ensamblados creados mediante [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md).|
|**/ur**  *assemblyName*<br /><br /> *scheme*<br /><br /> *identificador*<br /><br /> *description*|Desinstala una referencia a un ensamblado especificado de la caché global de ensamblados. Para quitar una referencia a un ensamblado, debe especificar los mismos parámetros *scheme*, *id* y *description* que especificó con las opciones **/i** y **/r** (o **/ir)** al instalar el ensamblado. Para obtener una descripción de los valores válidos que puede especificar para estos parámetros, vea la opción **/r**.<br /><br /> Especificar esta opción equivale a especificar las opciones **/u** y **/r** juntas.|
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|

## <a name="remarks"></a>Comentarios

> [!NOTE]
> Debe tener privilegios de administrador para poder usar Gacutil.exe.

En concreto, Gacutil.exe permite instalar y quitar ensamblados de la memoria caché, así como enumerar el contenido de la misma.

Gacutil.exe proporciona opciones compatibles con el recuento de referencias, algo parecido al esquema de recuento de referencias de Windows Installer. Puede usar Gacutil.exe para instalar dos aplicaciones que instalen el mismo ensamblado; la herramienta realiza un seguimiento del número de referencias al ensamblado. Como consecuencia, el ensamblado permanecerá en el equipo hasta que se desinstalen ambas aplicaciones. Si usa Gacutil.exe para realizar instalaciones de productos, use las opciones compatibles con el recuento de referencias. Use las opciones **/i** y **/r** de forma conjunta para instalar un ensamblado y agregar una referencia para contarlo. Use las opciones **/u** y **/r** de forma conjunta para quitar un recuento de referencias de un ensamblado. Tenga en cuenta que el uso de las opciones **/i** y **/u** por separado no es compatible con el recuento de referencias. Es adecuado usar estas opciones durante el desarrollo del producto, pero no para realizar instalaciones de productos propiamente dichas.

Use las opciones **/il** o **/ul** para instalar o desinstalar una lista de ensamblados almacenados en un archivo de texto ANSI. El contenido del archivo de texto debe tener el formato correcto. Si desea usar un archivo de texto para instalar ensamblados, especifique la ruta de acceso de cada ensamblado en una línea independiente del archivo. En el siguiente ejemplo se muestra el contenido de un archivo que contiene ensamblados que se van a instalar.

```text
myAssembly1.dll
myAssembly2.dll
myAssembly3.dll
```

Si desea usar un archivo de texto para desinstalar ensamblados, especifique el nombre completo de cada ensamblado en una línea independiente del archivo. En el siguiente ejemplo se muestra el contenido de un archivo que contiene ensamblados que se van a desinstalar.

```text
myAssembly1,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
myAssembly2,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
myAssembly3,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
```

> [!NOTE]
> Al intentar instalar a un ensamblado con un nombre de archivo que tenga entre 79 y 91 caracteres (sin incluir la extensión de archivo) se puede producir el error siguiente:
>
> ```output
> Failure adding assembly to the cache:   The file name is too long.
> ```
>
> Esto es porque Gacutil.exe crea internamente una ruta de acceso de hasta MAX_PATH caracteres que consta de los siguientes elementos:
>
> - Raíz de GAC: 34 caracteres (es decir, `C:\Windows\Microsoft.NET\assembly\`)
> - Arquitectura: 7 o 9 caracteres (es decir, `GAC_32\`, `GAC_64\` y `GAC_MSIL`)
> - AssemblyName: hasta 91 caracteres, según el tamaño de los demás elementos (por ejemplo, `System.Xml.Linq\`)
> - AssemblyInfo: de 31 a 48 caracteres o más que constan de:
>   - Framework: 5 caracteres (por ejemplo, `v4.0_`)
>   - AssemblyVersion: de 8 a 24 caracteres (por ejemplo, `9.0.1000.0_`)
>   - AssemblyLanguage: de 1 a 8 caracteres (por ejemplo, `de_`, `sr-Cyrl_`)
>   - PublicKey: 17 caracteres (por ejemplo, `31bf3856ad364e35\`)
> - DllFileName: hasta 91 + 4 caracteres (es decir, `<AssemblyName>.dll`)

## <a name="examples"></a>Ejemplos

El comando siguiente instala el ensamblado `mydll.dll` en la caché global de ensamblados.

```console
gacutil /i mydll.dll
```

El comando siguiente quita el ensamblado `hello` de la caché global de ensamblados, ya que no existen recuentos de referencias para el ensamblado.

```console
gacutil /u hello
```

Observe que el comando anterior puede quitar más de un ensamblado de la memoria caché de ensamblados porque no se ha especificado el nombre completo del ensamblado. Por ejemplo, si se han instalado en la memoria caché las versiones 1.0.0.0 y 3.2.2.1 de `hello`, el comando `gacutil /u hello` quita los dos ensamblados.

Use el ejemplo siguiente si solo desea quitar un ensamblado. Este comando solo quita el ensamblado `hello` cuyo número de versión, referencia cultural y clave pública coincide con los especificados.

```console
gacutil /u hello, Version=1.0.0.1, Culture="de",PublicKeyToken=45e343aae32233ca
```

El comando siguiente instala los ensamblados especificados en el archivo `assemblyList.txt` en la caché global de ensamblados.

```console
gacutil /il assemblyList.txt
```

El comando siguiente quita los ensamblados especificados en el archivo `assemblyList.txt` de la caché global de ensamblados.

```console
gacutil /ul assemblyList.txt
```

El comando siguiente instala `myDll.dll` en la caché global de ensamblados y agrega una referencia para contarlo. La aplicación `myDll.dll` usa el ensamblado `MyApp`. El parámetro `UNINSTALL_KEY MyApp` especifica la clave del Registro que agrega `MyApp` a Agregar o quitar programas en Windows. El parámetro de descripción se especifica como `My Application Description`.

```console
gacutil /i /r myDll.dll UNINSTALL_KEY MyApp "My Application Description"
```

El comando siguiente instala `myDll.dll` en la caché global de ensamblados y agrega una referencia para contarlo. El parámetro de esquema, `FILEPATH`, y el parámetro de identificador, `c:\applications\myApp\myApp.exe`, especifican la ruta de acceso a la aplicación que va a instalar `myDll.dll.` El parámetro de descripción se especifica como `MyApp`.

```console
gacutil /i /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp
```

El comando siguiente instala `myDll.dll` en la caché global de ensamblados y agrega una referencia para contarlo. El parámetro de esquema, `OPAQUE`, permite personalizar los parámetros de identificador y descripción.

```console
gacutil /i /r mydll.dll OPAQUE "Insert custom application details here" "Insert Custom description information here"
```

El comando siguiente quita la referencia a `myDll.dll` procedente de la aplicación `myApp`. Si se trata de la última referencia al ensamblado, también quitará el ensamblado de la caché global de ensamblados.

```console
gacutil /u /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp
```

El comando siguiente enumera el contenido de la caché global de ensamblados.

```console
gacutil /l
```

## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Caché global de ensamblados](../app-domains/gac.md)
- [Regasm.exe (Herramienta de registro de ensamblados)](regasm-exe-assembly-registration-tool.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
