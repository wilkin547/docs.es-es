---
title: Metadatos y componentes autodescriptivos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- runtime, metadata
- languages, interoperability
- portable executable files, metadata
- self-describing files
- metadata, about metadata
- common language runtime, metadata
- PE files, metadata
- components [.NET Framework], metadata
ms.assetid: 3dd13c5d-a508-455b-8dce-0a852882a5a7
ms.openlocfilehash: 5327bd70b05bac8970fa9802fb15e94ba5f686c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290063"
---
# <a name="metadata-and-self-describing-components"></a>Metadatos y componentes autodescriptivos

Hasta ahora, un componente de software (.exe o .dll) escrito en un lenguaje no podía usar fácilmente un componente de software escrito en otro lenguaje. COM supuso un paso adelante en la resolución de este problema. .NET Framework hace la interoperación entre componentes todavía más fácil, permitiendo que los compiladores emitan información de declaración adicional en todos los módulos y ensamblados. Esta información, denominada metadatos, contribuye a que los componentes interactúen sin problemas.

 Los metadatos son información binaria que describe un programa, almacenada en un archivo ejecutable portable (PE) de Common Language Runtime o en memoria. Cuando se compila el código en un archivo PE, los metadatos se insertan en una parte del archivo, y el código se convierte al lenguaje intermedio de Microsoft (MSIL) y se inserta en otra parte del archivo. Cada tipo y miembro que se define y al que se hace referencia en un módulo o ensamblado se describe en los metadatos. Cuando se ejecuta código, el motor en tiempo de ejecución carga los metadatos en la memoria y hace referencia a ellos para detectar información acerca de las clases, miembros, herencia, etc., del código.

 Los metadatos describen todos los tipos y miembros definidos en el código mediante un lenguaje neutro. Los metadatos almacenan la siguiente información:

- Descripción del ensamblado

  - Identidad (nombre, versión, referencia cultural, clave pública).

  - Los tipos que se exportan.

  - Otros ensamblados de los que depende éste.

  - Permisos de seguridad que hay que ejecutar.

- Descripción de los tipos.

  - Nombre, visibilidad, clase base e interfaces implementadas.

  - Miembros (métodos, campos, propiedades, eventos, tipos anidados).

- Atributos.

  - Elementos descriptivos adicionales que modifiquen los tipos y los miembros.

## <a name="benefits-of-metadata"></a>Ventajas de los metadatos

Los metadatos son la clave para un modelo de programación más sencillo y eliminando la necesidad de tener archivos de Lenguaje de definición de interfaz (IDL), archivos de encabezado o cualquier método externo de referencia a componentes. Los metadatos permiten que los lenguajes de .NET Framework se describan a sí mismos automáticamente independientemente del lenguaje, que no ven ni el programador ni el usuario. Además, los metadatos se pueden extender mediante el uso de atributos. Los metadatos proporcionan las siguientes ventajas principales:

- Archivos autodescriptivos

  Los módulos y ensamblados de Common Language Runtime son autodescriptivos. Los metadatos de un módulo contienen todo lo necesario para interactuar con otro módulo. Los metadatos proporcionan automáticamente la funcionalidad del IDL en COM, por lo que puede usar un archivo tanto para la definición como para la implementación. Los módulos y ensamblados de Common Language Runtime no necesitan ni registrarse en el sistema operativo. En consecuencia, las descripciones que usa el motor en tiempo de ejecución reflejan siempre el código actual del archivo compilado, lo que aumenta la confiabilidad de la aplicación.

- Interoperabilidad de lenguajes y diseño más sencillo, basado en el componente.

  Los metadatos proporcionan toda la información necesaria sobre el código compilado para derivar clases de archivos PE escritos en otro lenguaje. Se puede crear una instancia de cualquier clase escrita en cualquier lenguaje administrado (cualquier lenguaje dirigido a Common Language Runtime) sin tener que preocuparse por la serialización explícita ni por usar código de interoperabilidad personalizado.

- Atributos.

  .NET Framework le permite declarar determinados tipos de metadatos, denominados atributos, en el archivo compilado. Los atributos se encuentran en todo .NET Framework y se usan para controlar más minuciosamente el comportamiento del programa en tiempo de ejecución. Además, se pueden emitir metadatos personalizados propios en los archivos .NET Framework mediante atributos personalizados definidos por el usuario. Para obtener más información, consulte [Attributes](attributes/index.md) (Atributos).

## <a name="metadata-and-the-pe-file-structure"></a>Metadatos y la estructura del archivo PE

Los metadatos se almacenan en una sección de un archivo ejecutable portable (PE) de .NET Framework, mientras que el lenguaje intermedio de Microsoft (MSIL) se guarda en otra sección del mismo archivo. La parte de los metadatos del archivo contiene una serie de estructuras de datos de tablas y montones. La parte del MSIL contiene símbolos (token) de MSIL y de metadatos que hacen referencia a la parte de metadatos del archivo PE. Puede encontrarse con tokens de metadatos al usar herramientas como el [Desensamblador de MSIL (Ildasm.exe)](../framework/tools/ildasm-exe-il-disassembler.md) para ver el MSIL del código, por ejemplo.

### <a name="metadata-tables-and-heaps"></a>Tablas y montones de metadatos

Cada tabla de metadatos tiene información sobre los elementos del programa. Por ejemplo, una tabla de metadatos describe las clases del código, otra los campos, etc. Si hay diez clases en el código, la tabla de clases tendrá diez filas, una por clase. Las tablas de metadatos hacen referencia a otras tablas y montones. Por ejemplo, la tabla de metadatos de clases hace referencia a la tabla de métodos.

Los metadatos también almacenan información en cuatro estructuras de montón: cadena, objeto binario, cadena de usuario y GUID. Todas las cadenas usadas en los nombres de los tipos y los miembros se almacenan en el montón de cadenas. Por ejemplo, una tabla de métodos no almacena directamente el nombre de un método concreto, sino que señala al nombre del método almacenado en el montón de cadenas.

### <a name="metadata-tokens"></a>Símbolos (token) de metadatos

Cada fila de cada tabla de metadatos se identifica de forma exclusiva en la parte de MSIL del archivo PE mediante un token de metadatos. Los tokens de metadatos responden a un concepto similar a los punteros, que persisten en MSIL, que hacen referencia a una tabla de metadatos concreta.

Un token de metadatos es un número de cuatro bytes. El byte superior indica la tabla de metadatos a la que se refiere un token concreto (método, tipo, etc.). Los tres bytes restantes especifican la fila de la tabla de metadatos que corresponde al elemento de programación que se describe. Si se define un método en C# y se compila en un archivo PE, en la porción de MSIL del archivo PE podrían aparecer los tokens de metadatos siguientes:

`0x06000004`

El byte superior (`0x06`) indica que este es un token de **MethodDef**. Los tres bytes inferiores (`000004`) indican a Common Language Runtime que busque en la cuarta fila de la tabla **MethodDef** la información que describe la definición de este método.

### <a name="metadata-within-a-pe-file"></a>Metadatos en un archivo PE

Cuando se compila un programa para Common Language Runtime, se convierte en un archivo PE formado por tres partes. La tabla siguiente describe el contenido de cada una de estas partes.

|Sección del archivo PE|Contenido de la sección del archivo PE|
|----------------|----------------------------|
|Encabezado PE|El índice de las secciones principales del archivo PE y la dirección del punto de entrada.<br /><br /> El motor en tiempo de ejecución usa esta información para identificar el archivo como archivo PE y para determinar dónde comienza la ejecución al cargar el programa en la memoria.|
|Instrucciones MSIL|Instrucciones del Lenguaje intermedio de Microsoft (MSIL) que contiene el código. Muchas de las instrucciones MSIL van acompañadas por tokens de metadatos.|
|Metadatos|Tablas y montones de metadatos. El motor en tiempo de ejecución usa esta sección para registrar información sobre todos los tipos y miembros del código. Esta sección incluye también atributos personalizados e información de seguridad.|

## <a name="run-time-use-of-metadata"></a>Uso de metadatos en tiempo de ejecución

Para comprender mejor los metadatos y su uso en Common Language Runtime, puede resultar útil construir un programa sencillo y mostrar cómo afectan los metadatos a su comportamiento durante su ejecución. El siguiente ejemplo de código muestra dos métodos dentro de una clase llamada `MyApp`. El método `Main` es el punto de entrada del programa, mientras que el método `Add` simplemente devuelve la suma de dos argumentos de enteros.

```vb
Public Class MyApp
   Public Shared Sub Main()
      Dim ValueOne As Integer = 10
      Dim ValueTwo As Integer = 20
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo))
   End Sub

   Public Shared Function Add(One As Integer, Two As Integer) As Integer
      Return (One + Two)
   End Function
End Class
```

```csharp
using System;
public class MyApp
{
   public static int Main()
   {
      int ValueOne = 10;
      int ValueTwo = 20;
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo));
      return 0;
   }
   public static int Add(int One, int Two)
   {
      return (One + Two);
   }
}
```

Cuando se ejecuta el código, el motor en tiempo de ejecución carga el módulo en la memoria y consulta los metadatos de esta clase. Una vez cargado, el motor en tiempo de ejecución realiza una análisis exhaustivo de la secuencia de lenguaje intermedio de Microsoft (MSIL) del método para convertirla en rápidas instrucciones máquina nativas. El motor en tiempo de ejecución usa un compilador Just-In-Time (JIT) para convertir las instrucciones MSIL en código máquina nativo, método a método, según sea necesario.

En el siguiente ejemplo de código se muestra parte del MSIL producido a partir de la función `Main` del código anterior. El MSIL y los metadatos se pueden ver desde cualquier aplicación de .NET Framework usando el [Desensamblador de MSIL (Ildasm.exe)](../framework/tools/ildasm-exe-il-disassembler.md).

```console
.entrypoint
.maxstack  3
.locals ([0] int32 ValueOne,
         [1] int32 ValueTwo,
         [2] int32 V_2,
         [3] int32 V_3)
IL_0000:  ldc.i4.s   10
IL_0002:  stloc.0
IL_0003:  ldc.i4.s   20
IL_0005:  stloc.1
IL_0006:  ldstr      "The Value is: {0}"
IL_000b:  ldloc.0
IL_000c:  ldloc.1
IL_000d:  call int32 ConsoleApplication.MyApp::Add(int32,int32) /* 06000003 */
```

El compilador JIT lee el MSIL de todo el método, lo analiza exhaustivamente y genera instrucciones nativas efectivas para ese método. En `IL_000d` se encuentra un token de metadatos del método `Add` (`/*` `06000003 */`), y el motor en tiempo de ejecución usa ese token para consultar la tercera fila de la tabla **MethodDef**.

En la siguiente tabla, se muestra parte de la tabla **MethodDef** a la que hace referencia el token de los metadatos que describe el método `Add`. Aunque existen otras tablas de metadatos en el ensamblado y tienen sus propios valores únicos, sólo se trata esta tabla.

|Fila|Dirección relativa virtual (RVA)|ImplFlags|Marcas|NOMBRE<br /><br /> (señala el montón de cadenas).|Firma (señala el montón de objetos binarios)|
|---------|--------------------------------------|---------------|-----------|-----------------------------------------|----------------------------------------|
|1|0x00002050|IL<br /><br /> Administrado|Public<br /><br /> ReuseSlot<br /><br /> SpecialName<br /><br /> RTSpecialName<br /><br /> .ctor|.ctor (constructor)||
|2|0x00002058|IL<br /><br /> Administrado|Public<br /><br /> Estático<br /><br /> ReuseSlot|Método Main|String|
|3|0x0000208c|IL<br /><br /> Administrado|Public<br /><br /> Estático<br /><br /> ReuseSlot|Agregar|int, int, int|

Cada columna de la tabla contiene información importante sobre el código. La columna **RVA** permite que el motor en tiempo de ejecución calcule la dirección de memoria de inicio del MSIL que define este método. Las columnas **ImplFlags** y **Flags** contienen máscaras de bits que describen el método (por ejemplo, si el método es público o privado). La columna **Nombre** indexa el nombre del método del montón de cadenas. La columna **Firma** indexa la definición de la firma del método del montón de blobs.

El motor en tiempo de ejecución calcula la dirección de desplazamiento deseada desde la columna **RVA** de la tercera fila y la devuelve al compilador JIT, que, después, se dirige a la nueva dirección. El compilador JIT continúa procesando el MSIL en la nueva dirección hasta que encuentra otro token de metadatos y se repite el proceso.

Usando metadatos, el motor en tiempo de ejecución tiene acceso a toda la información que necesita para cargar el código y procesarlo en instrucciones máquina nativas. De este modo, los metadatos hacen posible los archivos autodescriptivos y, junto con el sistema de tipos comunes, la herencia de un lenguaje a otro.

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Atributos](attributes/index.md)|Describe cómo aplicar atributos, escribir atributos personalizados y recuperar información almacenada en atributos.|
