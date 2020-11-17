---
title: Ildasm.exe (Desensamblador de IL)
description: Use Ildasm.exe (Desensamblador de IL), que toma un archivo portable ejecutable (PE) que contiene código de lenguaje intermedio (IL) y crea un archivo de texto para Ilasm.exe.
ms.date: 03/30/2017
helpviewer_keywords:
- PE files, MSIL Disassembler
- portable executable files, MSIL Disassembler
- Ildasm.exe
- MSIL Disassembler
- text files produced by MSIL Disassembler
- disassembling file for MSIL Assembler input
ms.assetid: db27f6b2-f1ec-499e-be3a-7eecf95ca42b
ms.openlocfilehash: e94e80d0342f68098a08e184b6bf3f48c14e817b
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440886"
---
# <a name="ildasmexe-il-disassembler"></a>Ildasm.exe (Desensamblador de IL)

El Desensamblador de IL es una herramienta complementaria del Ensamblador de IL (*Ilasm.exe*). A partir de un archivo portable ejecutable (PE) que contiene código de lenguaje intermedio (IL), *Ildasm.exe* crea un archivo de texto que se puede usar como entrada para *Ilasm.exe*.

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

En el símbolo del sistema, escriba lo siguiente:

## <a name="syntax"></a>Sintaxis

```console
ildasm [options] [PEfilename] [options]
```

## <a name="parameters"></a>Parámetros

Las siguientes opciones se pueden usar con archivos *.exe*, *.dll*, *.obj*, *.lib* y *.winmd*.

| Opción | Descripción |
| ------ | ----------- |
|**/out=** `filename`|Crea un archivo de salida con el `filename` especificado, en lugar de mostrar los resultados en una interfaz gráfica de usuario.|
|**/rtf**|Genera la salida en formato de texto enriquecido. Esta opción no es válida si se usa junto con la opción **/text**.|
|**/text**|Muestra los resultados en la ventana de la consola, en lugar de presentarlos en una interfaz gráfica de usuario o en un archivo de salida.|
|**/html**|Genera la salida en formato HTML. Esta opción solo es válida si se usa con la opción **/output**.|
|**/?**|Muestra la sintaxis de comandos y las opciones de la herramienta.|

Las siguientes opciones adicionales se pueden usar con archivos *.exe*, *.dll* y *.winmd*.

| Opción | Descripción |
| ------ | ----------- |
|**/bytes**|Muestra bytes reales, en formato hexadecimal, como comentarios de instrucciones.|
|**/caverbal**|Genera objetos binarios de atributos personalizados en formato verbal. El valor predeterminado es el formato binario.|
|**/linenum**|Incluye referencias a líneas de código fuente originales.|
|**/nobar**|Suprime la ventana emergente del indicador de progreso del desensamblado.|
|**/noca**|Suprime la salida de atributos personalizados.|
|**/project**|Muestra los metadatos en la forma en que aparecen en el código administrado, no de la forma en que aparecen en el entorno de Windows Runtime nativo. Si `PEfilename` no es un archivo de metadatos de Windows ( *.winmd*), esta opción no tiene ningún efecto. Consulte [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](../cross-platform/support-for-windows-store-apps-and-windows-runtime.md).|
|**/pubonly**|Desensambla únicamente tipos y miembros públicos. Equivale a **/visibility:PUB**.|
|**/quoteallnames**|Incluye todos los nombres entre comillas simples.|
|**/raweh**|Muestra sin formato las cláusulas de control de excepciones.|
|**/source**|Muestra líneas de código fuente originales como comentarios.|
|**/tokens**|Muestra tokens de metadatos de clases y miembros.|
|**/visibility:** `vis`[+`vis`...]|Desensambla únicamente tipos o miembros con la visibilidad especificada. Los valores válidos para `vis` son los siguientes:<br /><br /> **PUB**: público<br /><br /> **PRI**: privado<br /><br /> **FAM**: familia<br /><br /> **ASM**: ensamblado<br /><br /> **FAA**: familia y ensamblado<br /><br /> **FOA**: familia o ensamblado<br /><br /> **PSC**: ámbito privado<br /><br /> Para obtener definiciones de estos modificadores de visibilidad, vea <xref:System.Reflection.MethodAttributes> y <xref:System.Reflection.TypeAttributes>.|

Las opciones siguientes se pueden usar con archivos *.exe*, *.dll* y *.winmd* para mostrar la salida únicamente en la consola o en un archivo.

| Opción | Descripción |
| ------ | ----------- |
|**/all**|Especifica una combinación de las opciones **/header**, **/bytes**, **/stats**, **/classlist** y **/tokens**.|
|**/classlist**|Incluye una lista de las clases definidas en el módulo.|
|**/forward**|Usa la declaración de clase de envío.|
|**/headers**|Incluye información de encabezados de archivos en la salida.|
|**/item:** `class`[ **::** `member`[`(sig`]]|Desensambla los elementos siguientes dependiendo del argumento proporcionado:<br /><br /> -   Desensambla el elemento `class` especificado.<br />-   Desensambla el elemento `member` de `class`.<br />-   Desensambla el elemento `member` de `class` con la firma especificada `sig`. El formato de `sig` es:<br />     [`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)<br />     **Nota** En las versiones 1.0 y 1.1 de .NET Framework, `sig` debe ir seguido de un paréntesis de cierre: `(sig)`. A partir de .NET Framework 2.0, el paréntesis de cierre se debe omitir: `(sig`.|
|**/noil**|Suprime la salida de código del ensamblado de IL.|
|**/stats**|Incluye estadísticas en la imagen.|
|**/typelist**|Genera la lista completa de tipos para mantener el orden de tipos en una acción de ida y vuelta.|
|**/unicode**|Usa codificación Unicode para la salida.|
|**/utf8**|Usa codificación UTF-8 para la salida. ANSI es el valor predeterminado.|

Las opciones siguientes se pueden usar con archivos *.exe*, *.dll*, *.obj*, *.lib* y *.winmd* para mostrar la salida únicamente en la consola o en un archivo.

| Opción | Descripción |
| ------ | ----------- |
|**/metadata**[=`specifier`]|Muestra metadatos, donde `specifier` es:<br /><br /> **MDHEADER**: muestra la información y los tamaños del encabezado de metadatos.<br /><br /> **HEX**: muestra información tanto en hexadecimal como en palabras.<br /><br /> **CSV**: muestra el número de registros y los tamaños de los montones.<br /><br /> **UNREX**: muestra externos sin resolver.<br /><br /> **SCHEMA**: muestra información del esquema y del encabezado de metadatos.<br /><br /> **RAW**: muestra las tablas de metadatos sin formato.<br /><br /> **HEAPS**: muestra los montones sin formato.<br /><br /> **VALIDATE**: valida la coherencia de los metadatos.<br /><br /> Puede especificar **/metadata** varias veces con valores diferentes para `specifier`.|

Las siguientes opciones se pueden usar con archivos *.lib* para mostrar la salida únicamente en la consola o en un archivo.

| Opción | Descripción |
| ------ | ----------- |
|**/objectfile**=`filename`|Muestra los metadatos de un único archivo objeto en la biblioteca especificada.|

> [!NOTE]
> Ninguna de las opciones de *Ildasm.exe* distingue entre mayúsculas y minúsculas, y se reconocen mediante las tres primeras letras. Por ejemplo, **/quo** equivale a **/quoteallnames**. Las opciones que especifican argumentos aceptan un signo de dos puntos (:) o un signo igual (=) como separador entre la opción y el argumento. Por ejemplo, **/output:** *filename* equivale a **/output=** *filename*.

## <a name="remarks"></a>Comentarios

*Ildasm.exe* solo funciona en archivos portables ejecutables (PE) del disco. No funciona en archivos instalados en la caché global de ensamblados.

El archivo de texto creado por *Ildasm.exe* se puede usar como entrada para el Ensamblador de IL (*Ilasm.exe*). Esta técnica es muy útil cuando, por ejemplo, se compila código en un lenguaje de programación que no admite todos los atributos de metadatos en tiempo de ejecución. Una vez compilado el código y ejecutada su salida mediante *Ildasm.exe*, el archivo de texto de IL resultante se puede editar manualmente para agregar los atributos que faltan. A continuación, puede ejecutar este archivo de texto mediante el Ensamblador de IL para generar un archivo ejecutable final.

> [!NOTE]
> Actualmente no se puede usar esta técnica con archivos PE que contienen código nativo incrustado (por ejemplo, archivos PE generados por Visual C++).  

Puede usar la interfaz gráfica de usuario predeterminada en el Desensamblador de IL para ver los metadatos y el código desensamblado de los archivos PE existentes en una vista jerárquica de árbol. Para usar dicha interfaz, escriba **ildasm** en la línea de comandos sin proporcionar el argumento *PEfilename* ni ninguna de las opciones. Desde el menú **Archivo** puede navegar hasta el archivo PE que quiera cargar en *Ildasm.exe*. Para guardar los metadatos y el código desensamblado mostrados para el PE seleccionado, seleccione el comando **Volcar** en el menú **Archivo**. Para guardar únicamente la vista de árbol jerárquica, seleccione el comando **Volcar vista de árbol** en el menú **Archivo**. Para obtener detalles sobre el modo de cargar un archivo en *Ildasm.exe* e interpretar la salida, vea el tutorial de *Ildasm.exe*, ubicado en la carpeta de ejemplos que se incluye con Windows SDK.

Si ejecuta *Ildasm.exe* con un argumento *PEfilename* que contiene recursos incrustados, la herramienta creará varios archivos de salida: un archivo de texto que contiene código IL y, para cada recurso administrado incrustado, un nuevo archivo .resources al que asignará el nombre usado para el recurso en los metadatos. Si un recurso no administrado se inserta en el argumento *PEfilename*, se creará un archivo .res con el nombre de archivo especificado por la opción **/output** para la salida de IL.

> [!NOTE]
> *Ildasm.exe* solo muestra descripciones de metadatos para archivos de entrada *.obj* y *.lib*. El código IL de estos tipos de archivos no se desensambla.

Puede ejecutar *Ildasm.exe* en un archivo .exe o *.dll* para determinar si está administrado. Si el archivo no está administrado, la herramienta muestra un mensaje que indica que el archivo no tiene un encabezado válido de Common Language Runtime y no se puede desensamblar. Si el archivo está administrado, la herramienta se ejecuta correctamente.

## <a name="version-information"></a>Información de versión

A partir de .NET Framework 4.5, *Ildasm.exe* controla un objeto binario grande (BLOB) de serialización desconocido mediante la presentación del contenido binario sin formato. Por ejemplo, el código siguiente muestra cómo se muestra un BLOB de cálculo de referencias generado por un programa de C#:

```csharp
public void Test([MarshalAs((short)70)] int test) { }
```

```il
// IL from Ildasm.exe output
.method public hidebysig instance void Test(int32  marshal({ 46 }) test) cil managed
```

A partir de .NET Framework 4.5, *Ildasm.exe* muestra atributos que se aplican a las implementaciones de interfaz, tal como se muestra en el siguiente fragmento de salida de *Ildasm.exe*:

```il
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

## <a name="examples"></a>Ejemplos

El comando siguiente hace que los metadatos y el código desensamblado del archivo PE `MyHello.exe` se muestren en la interfaz gráfica de usuario predeterminada de *Ildasm.exe*.

```console
ildasm myHello.exe
```

El comando siguiente desensambla el archivo `MyFile.exe` y almacena el texto del Ensamblador de IL resultante en el archivo *MyFile.il*.

```console
ildasm MyFile.exe /output:MyFile.il
```

El comando siguiente desensambla el archivo `MyFile.exe` y muestra el texto del Ensamblador de IL resultante en la ventana de consola.

```console
ildasm MyFile.exe /text
```

Si el archivo `MyApp.exe` contiene recursos insertados administrados y no administrados, el comando siguiente genera cuatro archivos: *MyApp.il*, *MyApp.res*, *Icons.resources* y *Message.resources*:

```console
ildasm MyApp.exe /output:MyApp.il
```

El comando siguiente desensambla el método `MyMethod` de la clase `MyClass` en `MyFile.exe` y muestra la salida en la ventana de consola.

```console
ildasm /item:MyClass::MyMethod MyFile.exe /text
```

En el ejemplo anterior podría haber varios métodos denominados `MyMethod` con firmas diferentes. El siguiente comando desensambla el método de instancia `MyMethod` con el tipo de valor devuelto **void** y los tipos de parámetros **int32** y **string**.

```console
ildasm /item:"MyClass::MyMethod(instance void(int32,string)" MyFile.exe /text
```

> [!NOTE]
> En las versiones 1.0 y 1.1 de .NET Framework, el paréntesis izquierdo que sigue al nombre del método debe equilibrarse con un paréntesis derecho después de la firma: `MyMethod(instance void(int32))`. A partir de .NET Framework 2.0, el paréntesis de cierre se debe omitir: `MyMethod(instance void(int32)`.

Para recuperar un método `static` (método`Shared` en Visual Basic), omita la palabra clave `instance`. Los tipos de clase no primitivos como `int32` y `string` deben incluir el espacio de nombres y deben ir precedidos de la palabra clave `class`. Los tipos externos deben ir precedidos del nombre de la biblioteca entre corchetes. El comando siguiente desensambla un método estático denominado `MyMethod` que tiene un parámetro de tipo <xref:System.AppDomain> y un tipo de valor devuelto de <xref:System.AppDomain>.

```console
ildasm /item:"MyClass::MyMethod(class [mscorlib]System.AppDomain(class [mscorlib]System.AppDomain)" MyFile.exe /text
```

Un tipo anidado debe ir precedido de su clase contenedora delimitada por una barra diagonal. Por ejemplo, si la clase `MyNamespace.MyClass` contiene una clase anidada denominada `NestedClass`, la clase anidada se identifica de la siguiente manera: `class MyNamespace.MyClass/NestedClass`.

## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Ilasm.exe (Ensamblador de IL)](ilasm-exe-il-assembler.md)
- [Proceso de ejecución administrada](../../standard/managed-execution-process.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
