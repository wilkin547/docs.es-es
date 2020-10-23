---
title: proceso de ejecución administrada
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- source code language
- code, managed execution process
- runtime, managed execution process
- compiling source code, managed execution process
- managed execution process
- common language runtime, managed execution process
ms.assetid: 476b03dc-2b12-49a7-b067-41caeaa2f533
ms.openlocfilehash: bc455817d29d2427f3051e79145b535e3eeaccbb
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161106"
---
# <a name="managed-execution-process"></a>proceso de ejecución administrada
<a name="introduction"></a> El proceso de ejecución administrada incluye los pasos siguientes, que se describen en detalle más adelante en este tema:

1. [Elegir un compilador](#choosing_a_compiler).

     Para obtener los beneficios que proporciona Common Language Runtime, se deben utilizar uno o más compiladores de lenguaje orientados al tiempo de ejecución.

2. [Compilar código a MSIL](#compiling_to_msil).

     La compilación convierte el código fuente en lenguaje intermedio de Microsoft (MSIL) y genera los metadatos necesarios.

3. [Compilar MSIL a código nativo](#compiling_msil_to_native_code).

     En tiempo de ejecución, un compilador Just-In-Time (JIT) convierte MSIL en código nativo. Durante esta compilación, el código debe pasar un proceso de comprobación que examina el MSIL y los metadatos para averiguar si el código garantiza la seguridad de tipos.

4. [Ejecutar código](#running_code).

     Common Language Runtime proporciona la infraestructura que permite que la ejecución tenga lugar y los servicios que se pueden usar durante la ejecución.

<a name="choosing_a_compiler"></a>
## <a name="choosing-a-compiler"></a>Elegir un compilador
 Para aprovechar las ventajas que ofrece Common Language Runtime (CLR), deben emplearse uno o varios compiladores de lenguaje destinados al motor en tiempo de ejecución, como Visual Basic, C#, Visual C++, F# o uno de los muchos compiladores de otros fabricantes, como un compilador Eiffel, Perl o COBOL.

 Como se ejecuta en un entorno multilenguaje, el motor en tiempo de ejecución es compatible con una gran variedad de tipos de datos y características de lenguajes. El compilador de lenguaje utilizado determina las características en tiempo de ejecución que están disponibles, y el código se diseña con esas características. El compilador, y no el motor en tiempo de ejecución, es el que establece la sintaxis que se debe utilizar en el código. Si los componentes escritos en otros lenguajes deben poder usar plenamente el componente, los tipos exportados de ese componente solo deben exponer las características del lenguaje incluidas en [Independencia del lenguaje y componentes independientes del lenguaje](language-independence-and-language-independent-components.md) (CLS). Puede utilizar el atributo <xref:System.CLSCompliantAttribute> para garantizar que su código es conforme a CLS. Para más información, consulte [Independencia del lenguaje y componentes independientes del lenguaje](language-independence-and-language-independent-components.md).

 [Volver al principio](#introduction)

<a name="compiling_to_msil"></a>
## <a name="compiling-to-msil"></a>Compilar en lenguaje intermedio de Microsoft (MSIL)
 Cuando se compila a código administrado, el compilador convierte el código fuente en Lengua intermedio de Microsoft (MSIL), que es un conjunto de instrucciones independiente de la CPU que se pueden convertir de forma eficaz en código nativo. MSIL incluye instrucciones para cargar, almacenar, inicializar y llamar a métodos en los objetos, así como instrucciones para operaciones lógicas y aritméticas, flujo de control, acceso directo a la memoria, control de excepciones y otras operaciones. Antes de poder ejecutar código, se debe convertir MSIL al código específico de la CPU, normalmente mediante un [compilador Just-In-Time (JIT)](#compiling_msil_to_native_code). Common Language Runtime proporciona uno o varios compiladores JIT para cada arquitectura de equipo compatible, por lo que se puede compilar y ejecutar el mismo conjunto de MSIL en cualquier arquitectura compatible.

 Cuando el compilador produce MSIL, también genera metadatos. Los metadatos describen los tipos que aparecen en el código, incluidas las definiciones de los tipos, las firmas de los miembros de tipos, los miembros a los que se hace referencia en el código y otros datos que el motor en tiempo de ejecución utiliza en tiempo de ejecución. MSIL y los metadatos están contenidos en un archivo ejecutable portable (PE), que se basa y extiende el PE de Microsoft publicado y el formato de archivo de objeto común (COFF) usado tradicionalmente para contenido ejecutable. Este formato de archivo, que contiene código MSIL o código nativo así como metadatos, permite al sistema operativo reconocer imágenes de Common Language Runtime. La presencia de metadatos en el archivo junto con MSIL permite crear códigos autodescriptivos, con lo cual las bibliotecas de tipos y el Lenguaje de definición de interfaz (IDL) son innecesarios. El motor en tiempo de ejecución localiza y extrae los metadatos del archivo cuando son necesarios durante la ejecución.

 [Volver al principio](#introduction)

<a name="compiling_msil_to_native_code"></a>
## <a name="compiling-msil-to-native-code"></a>Compilar MSIL a código nativo
 Para poder ejecutar el lenguaje intermedio de Microsoft (MSIL), primero debe compilarse a código nativo con Common Language Runtime para la arquitectura del equipo de destino. .NET proporciona dos formas de realizar esta conversión:

- Un compilador Just-In-Time (JIT) de .NET.

- [Ngen.exe (Generador de imágenes nativas)](../framework/tools/ngen-exe-native-image-generator.md).

### <a name="compilation-by-the-jit-compiler"></a>Compilación mediante el compilador JIT
 La compilación JIT convierte MSIL en código nativo a petición en el tiempo de ejecución de la aplicación, cuando el contenido de un ensamblado se carga y ejecuta. Common Language Runtime proporciona un compilador JIT para cada arquitectura de CPU compatible, por lo que los programadores pueden crear un conjunto de ensamblados MSIL que se puede compilar con un compilador JIT y se puede ejecutar en equipos distintos con diferentes arquitecturas. No obstante, si el código administrado llama a las API nativas específicas de la plataforma o a una biblioteca de clases específica de la plataforma, solo se ejecutará en ese sistema operativo.

 La compilación JIT tiene en cuenta la posibilidad de que durante la ejecución nunca se llame a parte del código. En vez de emplear tiempo y memoria para convertir todo el MSIL de un archivo PE a código nativo, convierte el MSIL necesario durante la ejecución y almacena el código nativo resultante en memoria para que sea accesible en las llamadas posteriores que se produzcan en el contexto de ese proceso. El cargador crea y asocia un código auxiliar a cada método de un tipo cuando este tipo se carga y se inicializa. Cuando se llama a un método por primera vez, el código auxiliar pasa el control al compilador JIT, el cual convierte el MSIL del método en código nativo y modifica el código auxiliar para señalar directamente al código nativo generado. Por tanto, las siguientes llamadas al método compilado mediante un compilador JIT pasan directamente al código nativo.

### <a name="install-time-code-generation-using-ngenexe"></a>Generación de código en tiempo de instalación mediante NGen.exe
 Puesto que el compilador JIT convierte el MSIL de un ensamblado en código nativo cuando se llama a cada uno de los métodos definidos en ese ensamblado, esto afecta negativamente al rendimiento en tiempo de ejecución. En la mayoría de los casos, esa disminución del rendimiento es aceptable. Y lo que es más importante, el código generado por el compilador JIT se enlaza al proceso que activó la compilación. Este código no se puede compartir en varios procesos. Para permitir que el código generado se comparta en varias invocaciones de una aplicación o en varios procesos que compartan un conjunto de ensamblados, Common Language Runtime admite un modo de compilación anticipado. Este modo de compilación Ahead Of Time usa [Ngen.exe (Generador de imágenes nativas)](../framework/tools/ngen-exe-native-image-generator.md) para convertir los ensamblados MSIL en código nativo de forma muy similar a como lo hace el compilador JIT. Sin embargo, la operación de Ngen.exe se diferencia de la del compilador JIT en tres aspectos:

- Realiza la conversión de MSIL a código nativo antes de ejecutar la aplicación en lugar de realizarla durante su ejecución.

- Compila a la vez un ensamblado completo, en lugar de compilar un método cada vez.

- Conserva el código generado en la memoria caché de imágenes nativas como un archivo en disco.

### <a name="code-verification"></a>Comprobación del código
 Como parte de su compilación en código nativo, el código de MILS debe pasar un proceso de comprobación, a menos que un administrador haya establecido una directiva de seguridad que permita al código omitir esta comprobación. En esta comprobación se examina el MSIL y los metadatos para determinar si el código garantiza la seguridad de tipos, lo que significa que el código solo tiene acceso a aquellas ubicaciones de la memoria para las que está autorizado. La seguridad de tipos ayuda a aislar los objetos entre sí y ayuda a protegerlos frente a daños involuntarios o malintencionados. Además, garantiza que las restricciones de seguridad sobre el código se aplican con toda certeza.

 El motor en tiempo de ejecución se basa en el hecho de que se cumplan las siguientes condiciones para el código seguro comprobable:

- La referencia a un tipo es estrictamente compatible con el tipo al que hace referencia.

- En un objeto sólo se invocan las operaciones definidas adecuadamente.

- Una identidad es precisamente lo que dice ser.

 Durante el proceso de comprobación, se examina el código MSIL para intentar confirmar que el código tiene acceso a las ubicaciones de memoria y puede llamar a los métodos sólo a través de los tipos definidos correctamente. Por ejemplo, un código no permite el acceso a los campos de un objeto si esta acción sobrecarga las ubicaciones de memoria. Además, el proceso de comprobación examina el código para determinar si el MSIL se ha generado correctamente, ya que un MSIL incorrecto puede llevar a la infracción de las reglas en materia de seguridad de tipos. El proceso de comprobación pasa un conjunto de código seguro bien definido, y pasa exclusivamente código seguro. No obstante, algunos códigos con seguridad de tipos no pasan la comprobación debido a algunas limitaciones de este proceso, y algunos lenguajes no producen código seguro comprobable debido a su diseño. Si la directiva de seguridad requiere código seguro de tipos y el código no pasa la comprobación, se produce una excepción al ejecutar el código.

 [Volver al principio](#introduction)

<a name="running_code"></a>
## <a name="running-code"></a>Ejecutar código
 Common Language Runtime proporciona la infraestructura que permite que la ejecución administrada tenga lugar y los servicios que se pueden usar durante la ejecución. Para poder ejecutar un método, primero se debe compilar a código específico del procesador. Cada método para el que se ha generado código de MSIL se compila mediante un compilador JIT la primera vez que se le llama y, después, se ejecuta. La próxima vez que se ejecuta el método, se ejecuta el código nativo existente resultante de la compilación JIT. El proceso de compilación JIT y la posterior ejecución de código se repite hasta completar la ejecución.

 Durante la ejecución, el código administrado recibe servicios como la recolección de elementos no utilizados, seguridad, interoperabilidad con código no administrado, compatibilidad de depuración entre lenguajes diferentes y compatibilidad mejorada con el control de versiones y la implementación.

 En Microsoft Windows Vista, el cargador del sistema operativo comprueba los módulos administrados mediante el examen de un bit del encabezado de COFF. El bit que se establece indica un módulo administrado. Si el cargador detecta módulos administrados, carga mscoree.dll, y `_CorValidateImage` y `_CorImageUnloading` notifican al cargador cuándo se cargan y descargan imágenes del módulo administrado. `_CorValidateImage` lleva a cabo las acciones siguientes:

1. Garantiza que el código es código administrado válido.

2. Cambia el punto de entrada en la imagen a un punto de entrada en el motor en tiempo de ejecución.

 En las versiones de 64 bits de Windows, `_CorValidateImage` modifica la imagen que está en la memoria transformando el formato PE32 en PE32+.

 [Volver al principio](#introduction)

## <a name="see-also"></a>Vea también

- [Información general](../framework/get-started/overview.md)
- [Independencia del lenguaje y componentes independientes del lenguaje](language-independence-and-language-independent-components.md)
- [Metadatos y componentes autodescriptivos](metadata-and-self-describing-components.md)
- [Ilasm.exe (Ensamblador de IL)](../framework/tools/ilasm-exe-il-assembler.md)
- [Seguridad](security/index.md)
- [Interoperating with Unmanaged Code](../framework/interop/index.md) (Interoperar con código no administrado)
- [Implementación](../framework/deployment/net-framework-applications.md)
- [Ensamblados de .NET](assembly/index.md)
- [Dominios de aplicación](../framework/app-domains/application-domains.md)
