---
title: Ngen.exe (Generador de imágenes nativas)
description: Revise Ngen.exe, el Generador de imágenes nativas. Mejore el rendimiento de las aplicaciones administradas creando imágenes nativas e instalándolas en la caché local de imágenes nativas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
ms.openlocfilehash: 12ef6724a76ec59bd412427a0a353565b1be2c8e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558422"
---
# <a name="ngenexe-native-image-generator"></a>Ngen.exe (Generador de imágenes nativas)

El Generador de imágenes nativas (Ngen.exe) es una herramienta que mejora el rendimiento de las aplicaciones administradas. Ngen.exe crea imágenes nativas, que son archivos que contienen código máquina compilado específicamente para un procesador, e instala estas imágenes en la memoria caché de imágenes nativas del equipo local. El runtime puede usar imágenes nativas de la memoria caché en lugar de usar el compilador Just-In-Time (JIT) para compilar el ensamblado original.

> [!NOTE]
> Ngen.exe compila las imágenes nativas de los ensamblados que tienen como destino solo .NET Framework. El generador de imágenes nativas equivalente para .NET Core es [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).

Cambios en Ngen.exe en .NET Framework 4:

- Ahora, Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).

- Las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial.

Cambios en Ngen.exe en la versión 2.0 de .NET Framework:

- Al instalar un ensamblado, también se instalan sus dependencias, lo que simplifica la sintaxis de Ngen.exe.

- Ahora, las imágenes nativas se pueden compartir en los dominios de aplicación.

- Una nueva acción, `update`, vuelve a crear las imágenes invalidadas.

- Se pueden aplazar las acciones para que las ejecute un servicio que use el tiempo de inactividad del equipo para generar e instalar las imágenes.

- Se han eliminado algunas de las causas que provocan la invalidación de imágenes.

En Windows 8, consulte [Tarea de imagen nativa](#native-image-task).

Para información adicional sobre el uso de Ngen.exe y el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).

> [!NOTE]
> Puede encontrar información sobre la sintaxis de Ngen.exe para las versiones 1.0 y 1.1 de .NET Framework en [Sintaxis heredada del generador de imágenes nativas (Ngen.exe)](/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

En el símbolo del sistema, escriba lo siguiente:

## <a name="syntax"></a>Sintaxis

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a>Acciones

En la tabla siguiente se muestra la sintaxis de cada acción (`action`). Para ver descripciones de los distintos elementos de una `action`, consulte las tablas [Argumentos](#ArgumentTable), [Niveles de prioridad](#PriorityTable), [Escenarios](#ScenarioTable) y [Configuración](#ConfigTable). En la tabla [Opciones](#OptionTable) se describe el parámetro `options` y los modificadores de ayuda.

|Acción|Descripción|
|------------|-----------------|
|`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]|Genera imágenes nativas para un ensamblado y sus dependencias e instala las imágenes en la memoria caché de imágenes nativas.<br /><br /> Si se especifica `/queue`, la acción se pone en la cola del servicio de imágenes nativas. La prioridad predeterminada es 3. Consulte la tabla [Niveles de prioridad](#PriorityTable).|
|`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]|Elimina las imágenes nativas de un ensamblado y sus dependencias de la memoria caché de imágenes nativas.<br /><br /> Para desinstalar una imagen y sus dependencias, use los mismos argumentos de la línea de comandos que usó para instalar la imagen. **Nota:**  A partir de .NET Framework 4:, ya no se admite la acción `uninstall` *.|
|`update` [`/queue`]|Actualiza las imágenes nativas que han dejado de ser válidas.<br /><br /> Si se especifica `/queue`, las actualizaciones se ponen en la cola del servicio de imágenes nativas. Las actualizaciones siempre se programan con una prioridad de 3, por lo que se ejecutan cuando el equipo se encuentra inactivo.|
|`display` [`assemblyName` &#124; `assemblyPath`]|Muestra el estado de las imágenes nativas para un ensamblado y sus dependencias.<br /><br /> Si no se proporciona ningún argumento, se muestra todo el contenido de la memoria caché de imágenes nativas.|
|`executeQueuedItems` [<code>1&#124;2&#124;3</code>]<br /><br /> o bien<br /><br /> `eqi` [1&#124;2&#124;3]|Ejecuta los trabajos de compilación en cola.<br /><br /> Si se especifica una prioridad, se ejecutan los trabajos de compilación con una prioridad mayor o igual a la especificada. Si no se especifica ninguna prioridad, se ejecutan todos los trabajos de compilación en cola.|
|`queue` {`pause` &#124; `continue` &#124; `status`}|Pausa el servicio de imágenes nativas, permite la reanudación del servicio en pausa o consulta el estado del servicio.|

<a name="ArgumentTable"></a>

## <a name="arguments"></a>Argumentos

|Argumento|Descripción|
|--------------|-----------------|
|`assemblyName`|El nombre para mostrar completo del ensamblado. Por ejemplo: `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`. **Nota:**  Puede proporcionar un nombre de ensamblado parcial, como `myAssembly`, para las acciones `display` y `uninstall`. <br /><br /> Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.|
|`assemblyPath`|La ruta de acceso explícita del ensamblado. Se puede especificar una ruta de acceso completa o relativa.<br /><br /> Si se especifica un nombre de archivo sin una ruta de acceso, el ensamblado deberá estar ubicado en el directorio actual.<br /><br /> Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a>Niveles de prioridad

|Prioridad|Descripción|
|--------------|-----------------|
|`1`|Las imágenes nativas se generan e instalan de forma inmediata, sin esperar al tiempo de inactividad.|
|`2`|Las imágenes nativas se generan e instalan sin esperar al tiempo de inactividad, pero después de que se hayan completado todas las acciones de prioridad 1 (y sus dependencias).|
|`3`|Las imágenes nativas se instalan cuando el servicio de imágenes nativas detecta que el equipo se encuentra inactivo. Consulte [Servicio de imágenes nativas](#native-image-service).|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a>Escenarios

|Escenario|Descripción|
|--------------|-----------------|
|`/Debug`|Genera imágenes nativas que pueden usarse con un depurador.|
|`/Profile`|Genera imágenes nativas que pueden usarse con un generador de perfiles.|
|`/NoDependencies`|Genera el número mínimo de imágenes nativas requerido por las opciones de escenario especificadas.|

<a name="ConfigTable"></a>

## <a name="config"></a>Configuración

|Configuración|Descripción|
|-------------------|-----------------|
|`/ExeConfig:` `exePath`|Usa la configuración del ensamblado ejecutable especificado.<br /><br /> Ngen.exe tiene que tomar las mismas decisiones que el cargador al enlazarse a las dependencias. Cuando se carga un componente compartido en tiempo de ejecución usando el método <xref:System.Reflection.Assembly.Load%2A>, el archivo de configuración de la aplicación determina las dependencias que se cargan para el componente compartido como, por ejemplo, la versión que se carga de una dependencia. El modificador `/ExeConfig` proporciona a Ngen.exe orientación sobre las dependencias que se cargarán en tiempo de ejecución.|
|`/AppBase:` `directoryPath`|Al buscar dependencias, usa el directorio especificado como base de la aplicación.|

<a name="OptionTable"></a>

## <a name="options"></a>Opciones

|Opción|Descripción|
|------------|-----------------|
|`/nologo`|Suprime la presentación de la pancarta de inicio de Microsoft.|
|`/silent`|Suprime la presentación de mensajes de operaciones correctas.|
|`/verbose`|Muestra información detallada para la depuración. **Nota:**  Debido a las limitaciones de los sistemas operativos, esta opción no muestra tanta información adicional en Windows 98 y Windows Millennium Edition.|
|`/help`, `/?`|Muestra las opciones y la sintaxis de los comandos de la versión actual.|

## <a name="remarks"></a>Comentarios

Para ejecutar Ngen.exe, es necesario disponer de privilegios administrativos.

> [!CAUTION]
> No ejecute Ngen.exe en ensamblados que no son de plena confianza. A partir de .NET Framework 4, Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).

A partir de .NET Framework 4, las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial. En su lugar, se invoca el compilador Just-In-Time (JIT).

Ngen.exe genera imágenes nativas para el ensamblado que el argumento `assemblyname` especifica para la acción `install` y todas sus dependencias. Las dependencias se determinan a partir de las referencias del manifiesto del ensamblado. El único escenario en el que es necesario instalar una dependencia por separado es aquel donde la aplicación carga la dependencia usando la reflexión, por ejemplo, llamando al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.

> [!IMPORTANT]
> No use el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> con imágenes nativas. Una imagen cargada con este método no la podrán usar otros ensamblados en el contexto de ejecución.

Ngen.exe mantiene un recuento de las dependencias. Por ejemplo, suponga que `MyAssembly.exe` y `YourAssembly.exe` están instalados en la memoria caché de imágenes nativas y que ambos tienen referencias a `OurDependency.dll`. Si se desinstala `MyAssembly.exe`, no se desinstala `OurDependency.dll`. Solo se quita cuando también se desinstala `YourAssembly.exe`.

Si va a generar una imagen nativa para un ensamblado en la caché global de ensamblados, especifique su nombre para mostrar. Vea <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.

Las imágenes nativas generadas por Ngen.exe se pueden compartir en los dominios de aplicación. Esto significa que Ngen.exe puede usarse en escenarios de aplicación que requieren el uso compartido de los ensamblados entre los dominios de aplicación. Para especificar una neutralidad de dominios:

- Aplique el atributo <xref:System.LoaderOptimizationAttribute> a la aplicación.

- Establezca la propiedad <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> al crear la información de instalación de un nuevo dominio de aplicación.

Use siempre código con dominio neutro al cargar el mismo ensamblado en varios dominios de aplicación. Si una imagen nativa se carga en un dominio de aplicación no compartido después de haberse cargado en un dominio compartido, no se podrá usar.

> [!NOTE]
> No se puede descargar código con dominio neutro y el rendimiento puede resultar algo más lento, especialmente al obtener acceso a miembros estáticos.

En esta sección Comentarios:

- [Generación de imágenes para distintos escenarios](#Scenarios)

- [Determinación de cuándo se deben usar imágenes nativas](#WhenToUse)

  - [Uso de memoria mejorado](#Memory)

  - [Inicio de aplicación más rápido](#Startup)

  - [Resumen de las consideraciones de uso](#UsageSummary)

- [Importancia de las direcciones base de los ensamblados](#BaseAddresses)

- [Enlace fuerte](#HardBinding)

  - [Especificación de una sugerencia de enlace para una dependencia](#DependencyHint)

  - [Especificación de una sugerencia de enlace predeterminado para un ensamblado](#AssemblyHint)

- [Procesamiento diferido](#Deferred)

- [Imágenes nativas y compilación JIT](#JITCompilation)

  - [Imágenes no válidas](#InvalidImages)

- [Solución de problemas](#Troubleshooting)

  - [Visor de registro de enlaces de ensamblados](#Fusion)

  - [Asistente para la depuración administrada JITCompilationStart](#MDA)

  - [Exclusión de la generación de imágenes nativas](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a>Generación de imágenes para distintos escenarios

Una vez generada la imagen nativa de un ensamblado, el runtime intenta localizar y usar automáticamente la imagen nativa cada vez que se ejecuta el ensamblado. Se pueden generar varias imágenes, en función de los escenarios de uso.

Por ejemplo, si ejecuta un ensamblado en un escenario de depuración o de generación de perfiles, el runtime buscará una imagen nativa generada con las opciones `/Debug` o `/Profile`. Si no encuentra una imagen nativa coincidente, el runtime usa la compilación JIT estándar. La única forma de depurar imágenes nativas es mediante la creación de una imagen nativa con la opción `/Debug`.

La acción `uninstall` también reconoce los escenarios, por lo que se pueden desinstalar todos los escenarios o solo los escenarios seleccionados.

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a>Determinación de cuándo se deben usar imágenes nativas

Las imágenes nativas pueden ofrecer mejoras de rendimiento en dos áreas: uso de memoria mejorado y tiempo de inicio reducido.

> [!NOTE]
> El rendimiento de las imágenes nativas depende de una serie de factores que dificultan el análisis, como los patrones de acceso a código y a datos, el número de llamadas realizadas a través de los límites de los módulos y el número de dependencias que ya se han cargado en otras aplicaciones. La única forma de determinar si las imágenes nativas benefician a la aplicación es mediante la realización de mediciones del rendimiento meticulosas en los escenarios de implementación clave.

<a name="Memory"></a>

### <a name="improved-memory-use"></a>Uso de memoria mejorado

Las imágenes nativas pueden mejorar significativamente el uso de memoria cuando el código se comparte entre los procesos. Las imágenes nativas son archivos PE de Windows, de modo que una única copia de un archivo .dll pueden compartirla varios procesos; en cambio, el código nativo generado por el compilador JIT se almacena en la memoria privada y no se puede compartir.

Las aplicaciones que se ejecutan en Terminal Services también pueden beneficiarse de las páginas de código compartido.

Además, al no cargar el compilador JIT, se reserva una cantidad de memoria fija para cada instancia de la aplicación.

<a name="Startup"></a>

### <a name="faster-application-startup"></a>Inicio de aplicación más rápido

Precompilar los ensamblados con Ngen.exe puede reducir el tiempo de inicio de algunas aplicaciones. En general, pueden obtenerse mejoras cuando las aplicaciones comparten ensamblados de componentes porque, una vez iniciada la primera aplicación, los componentes compartidos ya estarán cargados para las siguientes aplicaciones. Un inicio en frío, en el que todos los ensamblados de una aplicación deben cargarse desde el disco duro, no se beneficia tanto de las imágenes nativas porque predomina el tiempo de acceso al disco duro.

El enlace fuerte puede afectar al tiempo de inicio, ya que todas las imágenes con enlaces fuertes al ensamblado de aplicación principal deben cargarse al mismo tiempo.

> [!NOTE]
> Antes de .NET Framework 3.5 Service Pack 1, debía poner componentes con nombre seguro en la caché global de ensamblados porque el cargador efectúa una validación adicional de los ensamblados con nombre seguro que no se encuentran en la caché global de ensamblados, lo que anula cualquier mejora del tiempo de inicio obtenida gracias al uso de imágenes nativas. Las optimizaciones introducidas en .NET Framework 3.5 SP1 quitaron la validación adicional.

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a>Resumen de las consideraciones de uso

Las siguientes consideraciones generales y consideraciones sobre la aplicación pueden ayudarle a decidir si merece la pena asumir el esfuerzo de evaluar las imágenes nativas de la aplicación:

- Las imágenes nativas se cargan más rápido que MSIL, ya que eliminan la necesidad de ejecutar muchas actividades en el inicio, como la compilación JIT y la comprobación de la seguridad de tipos.

- Las imágenes nativas requieren un espacio de trabajo inicial más pequeño, ya que el compilador JIT no es necesario.

- Las imágenes nativas permiten un uso compartido del código entre los procesos.

- Las imágenes nativas requieren más espacio en el disco duro que los ensamblados MSIL y pueden tardar bastante tiempo en generarse.

- Las imágenes nativas necesitan mantenimiento.

  - Cuando se realiza el mantenimiento del ensamblado original o de una de sus dependencias, es necesario volver a generar las imágenes.

  - Un solo ensamblado puede necesitar varias imágenes nativas para su uso en aplicaciones o escenarios diferentes. Por ejemplo, la información de configuración de dos aplicaciones podría producir distintas decisiones de enlace para el mismo ensamblado dependiente.

  - La generación de imágenes nativas solo la puede llevar a cabo un administrador; es decir, deberá realizarse desde una cuenta de Windows del grupo de administradores.

Además de estas consideraciones generales, hay que tener en cuenta la naturaleza de la aplicación a la hora de determinar si las imágenes nativas pueden suponer una mejora en el rendimiento:

- Si la aplicación se ejecuta en un entorno que usa muchos componentes compartidos, las imágenes nativas permiten un uso compartido de los componentes por parte de varios procesos.

- Si la aplicación usa varios dominios de aplicación, las imágenes nativas permiten un uso compartido de las páginas de códigos entre los distintos dominios.

    > [!NOTE]
    > En las versiones 1.0 y 1.1 de .NET Framework, los dominios de aplicación no pueden compartir las imágenes nativas. Este no es el caso en la versión 2.0 o posterior.

- Si la aplicación va a ejecutarse en Terminal Server, las imágenes nativas permiten un uso compartido de las páginas de código.

- En general, las aplicaciones de gran tamaño se benefician de la compilación de imágenes nativas. En cambio, las aplicaciones pequeñas no suelen beneficiarse.

- En las aplicaciones de ejecución prolongada, la compilación JIT en tiempo de ejecución ofrece un rendimiento ligeramente superior al de las imágenes nativas. (El enlace fuerte puede mitigar hasta cierto punto esta diferencia de rendimiento).

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a>Importancia de las direcciones base de los ensamblados

Dado que las imágenes nativas son archivos PE de Windows, están sujetas a las mismas cuestiones de cambio de ubicación que otros archivos ejecutables. La repercusión que las reubicaciones tienen en el rendimiento es aún mayor si se usan enlaces fuertes.

Para establecer la dirección base de una imagen nativa, use la opción adecuada del compilador para establecer la dirección base del ensamblado. Ngen.exe usa esta dirección base para la imagen nativa.

> [!NOTE]
> Las imágenes nativas son de mayor tamaño que los ensamblados administrados a partir de los que se crean. Las direcciones base deben calcularse para permitir estos tamaños mayores.

Para ver la dirección base preferida de una imagen nativa, puede usar una herramienta como dumpbin.exe.

<a name="HardBinding"></a>

## <a name="hard-binding"></a>Enlace fuerte

El enlace fuerte aumenta el rendimiento y reduce el tamaño del espacio de trabajo de las imágenes nativas. El inconveniente del enlace fuerte es que todas las imágenes con enlaces fuertes a un ensamblado deben cargarse al cargar el ensamblado. Esto puede aumentar significativamente el tiempo de inicio de una aplicación de gran tamaño.

El enlace fuerte es adecuado para las dependencias que se cargan en todos los escenarios de la aplicación en los que el rendimiento es un factor crítico. Al igual que con cualquier otro aspecto del uso de imágenes nativas, la realización de mediciones del rendimiento meticulosas constituye la única forma de determinar si el enlace fuerte mejora el rendimiento de la aplicación.

Los atributos <xref:System.Runtime.CompilerServices.DependencyAttribute> y <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> permiten suministrar sugerencias de enlace fuerte a Ngen.exe.

> [!NOTE]
> Estos atributos son sugerencias para Ngen.exe, no comandos. El uso de estos atributos no garantiza el enlace fuerte. El significado de estos atributos puede cambiar en futuras versiones.

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a>Especificación de una sugerencia de enlace para una dependencia

Aplique <xref:System.Runtime.CompilerServices.DependencyAttribute> a un ensamblado para indicar la probabilidad de que se cargue una dependencia especificada. <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indica que el enlace fuerte es adecuado, <xref:System.Runtime.CompilerServices.LoadHint.Default> indica que debe usarse el valor predeterminado de la dependencia y <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indica que el enlace fuerte no es adecuado.

En el siguiente código se muestran los atributos de un ensamblado que tiene dos dependencias. La primera dependencia (Assembly1) es una candidata adecuada para el enlace fuerte, pero la segunda (Assembly2) no lo es.

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

El nombre de ensamblado no incluye la extensión de nombre de archivo. Pueden usarse nombres para mostrar.

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a>Especificación de una sugerencia de enlace predeterminado para un ensamblado

Las sugerencias de enlace predeterminado solo son necesarias para los ensamblados que cualquier aplicación con una dependencia sobre los mismos vaya a usar inmediatamente y con frecuencia. Aplique el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> con <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> a dichos ensamblados para especificar que debe usarse un enlace fuerte.

> [!NOTE]
> No hay ningún motivo para aplicar el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> a los ensamblados .dll que no pertenezcan a esta categoría, porque el hecho de aplicar el atributo con cualquier valor distinto de <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> produce el mismo efecto que no aplicar el atributo.

Microsoft usa el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> para especificar que el enlace fuerte es el valor predeterminado para un pequeño número de ensamblados de .NET Framework, como mscorlib.dll.

<a name="Deferred"></a>

## <a name="deferred-processing"></a>Procesamiento diferido

La generación de imágenes nativas para una aplicación de gran tamaño puede llevar bastante tiempo. Del mismo modo, los cambios realizados en un componente compartido o en la configuración del equipo pueden requerir la actualización de muchas imágenes nativas. Las acciones `install` y `update` disponen de una opción `/queue` que pone en cola la operación para su ejecución diferida por parte del servicio de imágenes nativas. Además, Ngen.exe dispone de las acciones `queue` y `executeQueuedItems`, que proporcionan algo de control sobre el servicio. Para más información, consulte [Servicio de imágenes nativas](#native-image-service).

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a>Imágenes nativas y compilación JIT

Si Ngen.exe encuentra en un ensamblado métodos que no puede generar, los excluye de la imagen nativa. Cuando el runtime ejecuta el ensamblado, usa la compilación JIT para los métodos que no se han incluido en la imagen nativa.

Además, si se ha actualizado el ensamblado o la imagen se ha invalidado por cualquier motivo, no se usan imágenes nativas.

<a name="InvalidImages"></a>

### <a name="invalid-images"></a>Imágenes no válidas

Cuando se usa Ngen.exe para crear una imagen nativa de un ensamblado, el resultado depende de las opciones especificadas en la línea de comandos y de determinadas opciones de configuración del equipo. Entre estas opciones de configuración, se incluyen las siguientes:

- La versión de .NET Framework.

- La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.

- La identidad exacta del ensamblado (la recompilación cambia la identidad).

- La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado (la recompilación cambia la identidad).

- Factores de seguridad.

Ngen.exe registra esta información cuando genera una imagen nativa. Al ejecutar un ensamblado, el runtime busca la imagen nativa generada con las opciones y los valores de configuración que coinciden con el entorno actual del equipo. El runtime usa la compilación JIT del ensamblado si no encuentra una imagen nativa coincidente. Si se realizan los siguientes cambios en la configuración y el entorno de un equipo, las imágenes nativas dejarán de ser válidas:

- La versión de .NET Framework.

     Si se aplica una actualización a .NET Framework, todas las imágenes nativas que se hayan creado mediante Ngen.exe dejarán de ser válidas. Por esta razón, todas las actualizaciones de .NET Framework ejecutan el comando `Ngen Update`, para garantizar que se vuelven a generar todas las imágenes nativas. .NET Framework crea nuevas imágenes nativas de forma automática para las bibliotecas de .NET Framework que instala.

- La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.

     Por ejemplo, si la versión del sistema operativo que se ejecuta en un equipo cambia de Windows 98 a Windows XP, todas las imágenes nativas almacenadas en la memoria caché de imágenes nativas dejan de ser válidas. Sin embargo, si el sistema operativo cambia de Windows 2000 a Windows XP, las imágenes siguen siendo válidas.

- La identidad exacta del ensamblado.

     Si vuelve a compilar un ensamblado, su imagen nativa correspondiente deja de ser válida.

- La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado.

     Si actualiza un ensamblado administrado, todas las imágenes nativas que, directa o indirectamente, dependen de ese ensamblado dejan de ser válidas y deben volver a generarse. Esto se aplica tanto a las referencias ordinarias como a las dependencias con enlaces fuertes. Cuando se aplica una actualización de software, el programa de instalación debe ejecutar un comando `Ngen Update` para garantizar que se vuelven a generar todas las imágenes nativas dependientes.

- Factores de seguridad.

     Si se modifica la directiva de seguridad del equipo para restringir los permisos previamente concedidos a un ensamblado, la imagen nativa compilada con anterioridad para dicho ensamblado puede dejar de ser válida.

     Para información detallada sobre cómo Common Language Runtime administra la seguridad de acceso del código y sobre cómo usar los permisos, consulte [Seguridad de acceso del código](../misc/code-access-security.md).

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a>Solución de problemas

Los temas de solución de problemas siguientes permiten ver cuáles son las imágenes nativas que la aplicación usa y cuáles no puede usar, determinar cuándo el compilador JIT comienza a compilar un método y muestra cómo excluir la compilación de imágenes nativas de métodos específicos.

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a>Visor de registro de enlaces de ensamblados

Para confirmar que la aplicación está usando imágenes nativas, puede usar [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](fuslogvw-exe-assembly-binding-log-viewer.md). Seleccione **Imágenes nativas** en el cuadro **Categorías de registro** de la ventana del visor de registro de enlaces. Fuslogvw.exe proporciona información sobre el motivo por el que se ha rechazado una imagen nativa.

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a>Asistente para la depuración administrada JITCompilationStart

Puede usar el Asistente para la depuración administrada (MDA) [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) para determinar el momento en el que el compilador JIT empieza a compilar una función.

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a>Exclusión de la generación de imágenes nativas

En algunos casos, NGen.exe puede tener problemas para generar una imagen nativa para un método específico, o bien es posible que prefiera que el método se compile en JIT en lugar de compilarlo en una imagen nativa. En este caso, puede usar el atributo `System.Runtime.BypassNGenAttribute` para evitar que NGen.exe genere una imagen nativa para un método concreto. El atributo se debe aplicar individualmente a cada método cuyo código no desea que se incluya en la imagen nativa. NGen.exe reconoce el atributo y no genera código en la imagen nativa para el método correspondiente.

Pero tenga en cuenta que `BypassNGenAttribute` no está definido como tipo en la biblioteca de clases .NET Framework. Para usar el atributo en el código, primero debe definirlo de la manera siguiente:

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

Luego puede aplicar el atributo a cada método. En el ejemplo siguiente se indica al Generador de imágenes nativas que no debe generar una imagen nativa para el método `ExampleClass.ToJITCompile`.

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a>Ejemplos

El siguiente comando genera una imagen nativa para `ClientApp.exe`, que se encuentra en el directorio actual, e instala la imagen en la memoria caché de imágenes nativas. Si existe un archivo de configuración para el ensamblado, Ngen.exe usará dicho archivo. Además, se generarán imágenes nativas para cualquier archivo .dll al que haga referencia `ClientApp.exe`.

```console
ngen install ClientApp.exe
```

Una imagen instalada con Ngen.exe también recibe el nombre de raíz. Una raíz puede ser una aplicación o un componente compartido.

El siguiente comando genera una imagen nativa para `MyAssembly.exe` con la ruta de acceso especificada.

```console
ngen install c:\myfiles\MyAssembly.exe
```

A la hora de buscar los ensamblados y sus dependencias, Ngen.exe usa la misma lógica de búsqueda que Common Language Runtime. De forma predeterminada, el directorio que contiene `ClientApp.exe` se usa como directorio base de la aplicación y todas las búsquedas de ensamblados comienzan en este directorio. Se puede reemplazar este comportamiento mediante la opción `/AppBase`.

> [!NOTE]
> Se trata de un cambio de comportamiento de Ngen.exe en las versiones 1.0 y 1.1 de .NET Framework, donde la base de la aplicación está establecida en el directorio actual.

Un ensamblado puede disponer de una dependencia sin referencia alguna; por ejemplo, si carga un archivo .dll mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>. Se puede crear una imagen nativa de este archivo .dll usando la información de configuración del ensamblado de aplicación, con la opción `/ExeConfig`. El siguiente comando genera una imagen nativa de `MyLib.dll,` usando la información de configuración de `MyApp.exe`.

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

Los ensamblados instalados de esta manera no se quitan cuando se quita la aplicación.

Para desinstalar una dependencia, use las mismas opciones de línea de comandos que se usaron para su instalación. El siguiente comando desinstala el archivo `MyLib.dll` del ejemplo anterior.

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

Para crear una imagen nativa de un ensamblado en la caché global de ensamblados, use el nombre para mostrar del ensamblado. Por ejemplo:

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

NGen.exe generará un conjunto independiente de imágenes para cada escenario que se instale. Por ejemplo, el siguiente comando instala un conjunto completo de imágenes nativas para el funcionamiento normal, otro conjunto completo para la depuración, y un tercer conjunto para la creación de perfiles:

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a>Mostrar la memoria caché de imágenes nativas

Una vez instaladas en la memoria caché las imágenes nativas, se pueden mostrar mediante Ngen.exe. El siguiente comando muestra todas las imágenes nativas que contiene la memoria caché de imágenes nativas.

```console
ngen display
```

La acción `display` muestra primero todos los ensamblados raíz, seguidos de una lista de todas las imágenes nativas del equipo.

Use el nombre simple de un ensamblado para mostrar únicamente información de dicho ensamblado. El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas que coinciden con el nombre parcial `MyAssembly`, sus dependencias y todas las raíces que tienen una dependencia en `MyAssembly`:

```console
ngen display MyAssembly
```

Conocer las raíces que dependen de un ensamblado de componente compartido resulta de gran utilidad para valorar el impacto de una acción `update` una vez actualizado el componente compartido.

Si especifica la extensión de archivo de un ensamblado, deberá especificar la ruta de acceso o ejecutar Ngen.exe desde el directorio que contiene el ensamblado:

```console
ngen display c:\myApps\MyAssembly.exe
```

El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas con el nombre `MyAssembly` y la versión 1.0.0.0.

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a>Actualizar imágenes

Normalmente, las imágenes se actualizan tras la actualización de un componente compartido. Para actualizar todas las imágenes nativas que hayan cambiado o cuyas dependencias hayan cambiado, use la acción `update` sin ningún argumento.

```console
ngen update
```

Actualizar todas las imágenes puede ser un proceso largo. La opción `/queue` pone en cola las actualizaciones para que las ejecute el servicio de imágenes nativas. Para más información sobre la opción `/queue` y las prioridades de instalación, consulte [Servicio de imágenes nativas](#native-image-service).

```console
ngen update /queue
```

### <a name="uninstalling-images"></a>Desinstalar imágenes

Ngen.exe mantiene una lista de dependencias; de este modo, los componentes compartidos se quitan únicamente cuando se han quitado todos los ensamblados que dependen de ellos. Además, si un componente compartido se ha instalado como raíz, no se quita.

El siguiente comando desinstala todos los escenarios de la raíz `ClientApp.exe`:

```console
ngen uninstall ClientApp
```

Se puede usar la acción `uninstall` para quitar escenarios concretos. El siguiente comando desinstala todos los escenarios de depuración de `ClientApp.exe`:

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> Cuando se desinstalan escenarios `/debug` no se desinstalan los escenarios que incluyen tanto `/profile` como `/debug.`

El siguiente comando desinstala todos los escenarios de una versión concreta de `ClientApp.exe`:

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

Los siguientes comandos desinstalan todos los escenarios de `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` o simplemente el escenario de depuración de dicho ensamblado:

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

Al igual que ocurre con la acción `install`, cuando se suministra una extensión, es necesario ejecutar Ngen.exe desde el directorio que contiene el ensamblado o especificar una ruta de acceso completa.

Para ver ejemplos relacionados con el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).

## <a name="native-image-task"></a>Tarea de imagen nativa

La tarea de imagen nativa es una tarea de Windows que genera y mantiene imágenes nativas. La tarea de imagen nativa genera y recupera automáticamente imágenes nativas para los escenarios admitidos. También permite que los instaladores usen [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md) para aplazar la creación y la actualización de las imágenes nativas.

La tarea de imagen nativa se registra una vez por cada arquitectura de CPU admitida en un equipo, para permitir la compilación de las aplicaciones que tienen como destino cada arquitectura:

|Nombre de la tarea|Equipo de 32 bits|Equipo de 64 bits|
|---------------|----------------------|----------------------|
|NET Framework NGEN v4.0.30319|Sí|Sí|
|NET Framework NGEN v4.0.30319 64|No|Sí|

La tarea de imagen nativa está disponible en .NET Framework 4.5 y las versiones posteriores, con Windows 8 o posterior. En las versiones anteriores de Windows, .NET Framework usa el [Servicio de imágenes nativas](#native-image-service).

### <a name="task-lifetime"></a>Duración de la tarea

En general, el Programador de tareas de Windows inicia la tarea de imagen nativa cada noche, cuando el equipo está inactivo. La tarea busca los trabajos aplazados puestos en cola por los instaladores de aplicaciones, las solicitudes aplazadas de actualización de imágenes nativas y las creaciones automáticas de imágenes. La tarea completa los elementos de trabajo pendientes y, después, se apaga. Si el equipo deja de estar inactivo mientras se ejecuta la tarea, esta se detendrá.

También puede iniciar la tarea de imagen nativa manualmente con la interfaz de usuario del Programador de tareas o con llamadas manuales a NGen.exe. Si la tarea se inicia con alguno de estos métodos, seguirá ejecutándose cuando el equipo ya no esté inactivo. Las imágenes creadas manualmente con NGen.exe tienen mayor prioridad, para que el comportamiento de los instaladores de aplicaciones sea predecible.

## <a name="native-image-service"></a>Servicio de imágenes nativas

El servicio de imágenes nativas es un servicio de Windows que genera y mantiene imágenes nativas. El servicio de imágenes nativas permite al desarrollador aplazar la instalación y la actualización de imágenes nativas hasta los períodos en los que el equipo está inactivo.

Normalmente, quien inicia el servicio de imágenes nativas es el programa de instalación (el instalador) de una aplicación o una actualización. En el caso de las acciones de prioridad 3, el servicio se ejecuta durante el tiempo de inactividad del equipo. El servicio guarda su estado y es capaz de continuar a lo largo de varios reinicios si es necesario. Se pueden poner en cola varias compilaciones de imágenes.

El servicio también interactúa con el comando Ngen.exe manual. Los comandos manuales tienen prioridad sobre la actividad en segundo plano.

> [!NOTE]
> En Windows Vista, el nombre del servicio de imágenes nativas que se muestra es "Microsoft.NET Framework NGEN v2.0.50727_X86" o "Microsoft.NET Framework NGEN v2.0.50727_X64". En todas las versiones anteriores de Microsoft Windows, el nombre es "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X86" o "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X64".

### <a name="launching-deferred-operations"></a>Iniciar operaciones aplazadas

Antes de comenzar una instalación o una actualización, se recomienda pausar el servicio. Así, el servicio no se ejecutará mientras el instalador copia archivos o coloca ensamblados en la caché global de ensamblados. La siguiente línea de comandos de Ngen.exe pausa el servicio:

```console
ngen queue pause
```

Después de poner en cola todas las operaciones aplazadas, el siguiente comando permite reanudar el servicio:

```console
ngen queue continue
```

Para aplazar la generación de imágenes nativas al instalar una nueva aplicación o al actualizar un componente compartido, utilice la opción `/queue` con las acciones `install` o `update`. Las siguientes líneas de comandos de Ngen.exe instalan una imagen nativa de un componente compartido y realizan una actualización de todas las raíces a las que puede que afectaran:

```console
ngen install MyComponent /queue
ngen update /queue
```

La acción `update` vuelve a generar todas las imágenes nativas invalidadas, no solo las que utilizan `MyComponent`.

Si la aplicación está formada por muchas raíces, puede controlar la prioridad de las acciones aplazadas. Los siguientes comandos ponen en cola la instalación de tres raíces. `Assembly1` se instala en primer lugar, sin esperar al tiempo de inactividad. `Assembly2` también se instala sin esperar al tiempo de inactividad, pero una vez que finalizan todas las acciones de prioridad 1. `Assembly3` se instala cuando el servicio detecta que el equipo se encuentra inactivo.

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

Puede forzar la ejecución sincrónica de las acciones en cola con la acción `executeQueuedItems`. Si especifica la prioridad (opcional), esta acción afecta solo a las acciones en cola que tienen una prioridad igual o menor. La prioridad predeterminada es 3, por lo que el siguiente comando de Ngen.exe procesa todas las acciones en cola inmediatamente y no vuelve hasta que finalizan:

```console
ngen executeQueuedItems
```

Los comandos sincrónicos son ejecutados por Ngen.exe y no utilizan el servicio de imágenes nativas. Puede ejecutar acciones con Ngen.exe mientras se está ejecutando el servicio de imágenes nativas.

### <a name="service-shutdown"></a>Apagado del servicio

El servicio, después de iniciarse con la ejecución de un comando de Ngen.exe que incluye la opción `/queue`, se ejecuta en segundo plano hasta que se completan todas las acciones. El servicio guarda su estado para poder continuar a lo largo de varios reinicios si es necesario. Cuando el servicio detecta que no hay más acciones en cola, restablece su estado para no reiniciarse la próxima vez que se arranque el equipo y, luego, se apaga.

### <a name="service-interaction-with-clients"></a>Interacción del servicio con los clientes

En la versión 2.0 de .NET Framework, la única interacción con el servicio de imágenes nativas es a través de la herramienta de línea de comandos Ngen.exe. Utilice la herramienta de línea de comandos en los scripts de instalación para poner en cola las acciones del servicio de imágenes nativas e interactuar con el servicio.

## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Proceso de ejecución administrada](../../standard/managed-execution-process.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
