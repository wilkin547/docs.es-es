---
title: Cómo el motor en tiempo de ejecución ubica ensamblados
description: Aprenda como Common Language Runtime (CLR) localiza los ensamblados que conforman la aplicación en .NET y se enlaza con ellos.
ms.date: 03/30/2017
helpviewer_keywords:
- app.config files, assembly locations
- deploying applications [.NET Framework], assembly locations
- application configuration files, locating assemblies
- .NET Framework application deployment, locating assemblies
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 772ac6f4-64d2-4cfb-92fd-58096dcd6c34
ms.openlocfilehash: 1b2ee58ccbd4bdfceb6300c20d5255718982f2e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272532"
---
# <a name="how-the-runtime-locates-assemblies"></a>Cómo el motor en tiempo de ejecución ubica ensamblados

Para implementar correctamente una aplicación de .NET Framework, debe entender la manera en que Common Language Runtime busca y enlaza los ensamblados que componen la aplicación. De forma predeterminada, runtime intenta enlazar con la versión exacta de un ensamblado con el que se creó la aplicación. Este comportamiento predeterminado puede reemplazarse con los valores del archivo de configuración.

Common Language Runtime realiza una serie de pasos cuando intenta buscar un ensamblado y resolver una referencia de ensamblado. Cada paso se explica en las secciones siguientes. El sondeo de términos suele usarse cuando se describe la manera en que el tiempo de ejecución busca ensamblados; hace referencia al conjunto de heurística que se usa para buscar el ensamblado en función de su nombre y referencia cultural.

> [!NOTE]
> Puede ver la información de enlace en el archivo de registro usando el [visor de registro de enlaces de ensamblados (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), que se incluye en Windows SDK.

## <a name="initiating-the-bind"></a>Iniciar el enlace

El proceso de buscar y enlazar a un ensamblado comienza cuando el tiempo de ejecución intenta resolver una referencia a otro ensamblado. Esta referencia puede ser estática o dinámica. El compilador registra las referencias estáticas en los metadatos del manifiesto del ensamblado en tiempo de compilación. Las referencias dinámicas se construyen sobre la marcha como resultado de llamar a varios métodos, como <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.

La mejor manera de hacer referencia a un ensamblado es usar una referencia completa, incluido el nombre del ensamblado, la versión, la referencia cultural y el token de clave pública (si existe). El tiempo de ejecución usa esta información para buscar el ensamblado, siguiendo los pasos descritos más adelante en esta sección. El tiempo de ejecución usa el mismo proceso de resolución, sin tener en cuenta si la referencia es para un ensamblado estático o dinámico.

También puede hacer una referencia dinámica a un ensamblado proporcionando el método de llamada únicamente con información parcial sobre el ensamblado, por ejemplo especificando solo el nombre de ensamblado. En este caso, el ensamblado solo se busca en el directorio de la aplicación y no se realiza ninguna otra comprobación. Se hace una referencia parcial mediante cualquiera de los diversos métodos para cargar ensamblados, como <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>.

Por último, puede hacer una referencia dinámica mediante un método como <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> y facilitar solo información parcial. Después, califique la referencia mediante el elemento [\<qualifyAssembly>](../configure-apps/file-schema/runtime/qualifyassembly-element.md) en el archivo de configuración de la aplicación. Este elemento permite proporcionar información de referencia completa (nombre, versión, referencia cultural y, si procede, el token de clave pública) en el archivo de configuración de la aplicación, en lugar de en el código. Use esta técnica si desea completar una referencia a un ensamblado fuera del directorio de la aplicación, o si desea hacer referencia a un ensamblado en la caché global de ensamblados pero prefiere la comodidad de especificar la referencia completa en el archivo de configuración en lugar de en el código.

> [!NOTE]
> Este tipo de referencia parcial no debe usarse con ensamblados que se comparten entre varias aplicaciones. Como los valores de configuración se aplican por aplicación y no por ensamblado, un ensamblado compartido que use este tipo de referencia parcial requerirá que cada aplicación que use el ensamblado compartido tenga la información calificadora en su archivo de configuración.

El tiempo de ejecución sigue estos pasos para resolver una referencia de ensamblado:

1. [Determina la versión correcta del ensamblado](#step1) examinando los archivos de configuración aplicables, incluido el archivo de configuración de la aplicación, el archivo de directiva de edición y el archivo de configuración del equipo. Si el archivo de configuración se encuentra en un equipo remoto, el tiempo de ejecución debe buscar y descargar el archivo de configuración de la aplicación en primer lugar.

2. [Comprueba si el nombre de ensamblado ya estuvo enlazado](#step2) y, si es así, usa el ensamblado cargado previamente. Si una solicitud anterior para cargar el ensamblado produjo un error, la solicitud produce un error inmediatamente sin intentar cargar el ensamblado.

    > [!NOTE]
    > El almacenamiento en caché de errores de enlace de ensamblados es nuevo en .NET Framework versión 2.0.

3. [Comprueba la caché global de ensamblados](#step3). Si el ensamblado se encuentra allí, el tiempo de ejecución usa este ensamblado.

4. [Sondea el ensamblado](#step4) siguiendo estos siguientes pasos:

    1. Si la directiva de configuración y edición no afecta a la referencia original y si la solicitud de enlace se creó usando el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> , el tiempo de ejecución comprueba las sugerencias de ubicación.

    2. Si se encuentra un código base en los archivos de configuración, el tiempo de ejecución solo comprueba esta ubicación. Si se produce un error en este sondeo, el tiempo de ejecución determina que la solicitud de enlace produjo un error y no se llevan a cabo más sondeos.

    3. Sondea el ensamblado mediante la heurística descrita en la [sección de sondeo](#step4). Si no se encuentra el ensamblado tras el sondeo, el tiempo de ejecución solicita a Windows Installer que proporcione un ensamblado. Esto actúa como una característica de instalación a petición.

        > [!NOTE]
        > No se produce ninguna comprobación de versión en busca de ensamblados sin nombres seguros, y el tiempo de ejecución no protege la caché global de ensamblados para los ensamblados sin nombres seguros.

<a name="step1"></a>

## <a name="step-1-examining-the-configuration-files"></a>Paso 1: Examen de los archivos de configuración

El comportamiento de enlace de ensamblados puede configurarse en niveles diferentes en función de tres archivos XML:

- Archivo de configuración de la aplicación.

- Archivo de directiva de edición.

- Archivo de configuración del equipo.

Estos archivos tienen la misma sintaxis y proporcionan información como las redirecciones de enlaces, la ubicación del código y los modos de enlace de ensamblados concretos. Cada archivo de configuración puede contener un elemento [\<assemblyBinding> ](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) que redirige el proceso de enlace. Los elementos secundarios del elemento [\<assemblyBinding> ](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) incluyen el elemento [\<dependentAssembly> ](../configure-apps/file-schema/runtime/dependentassembly-element.md). Los elementos secundarios del elemento [\<dependentAssembly> ](../configure-apps/file-schema/runtime/dependentassembly-element.md) incluyen el elemento [\<assemblyIdentity> ](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment), el elemento [\<bindingRedirect> ](../configure-apps/file-schema/runtime/bindingredirect-element.md) y el elemento [\<codeBase> ](../configure-apps/file-schema/runtime/codebase-element.md).

> [!NOTE]
> Puede encontrarse información de configuración en los tres archivos de configuración; no todos los elementos son válidos en todos los archivos de configuración. Por ejemplo, la información sobre el modo de enlace y la ruta de acceso privada solo puede estar en el archivo de configuración de la aplicación. Para obtener una lista completa de la información contenida en cada archivo, consulte [Configurar aplicaciones con archivos de configuración](../configure-apps/index.md).

### <a name="application-configuration-file"></a>Archivo de configuración de aplicación

En primer lugar, Common Language Runtime comprueba el archivo de configuración de la aplicación en busca de información que reemplace la información de versión almacenada en el manifiesto del ensamblado que realiza la llamada. El archivo de configuración de la aplicación puede implementarse con una aplicación, pero no es necesario para la ejecución de la aplicación. Normalmente, la recuperación de este archivo es casi instantánea, pero en los casos en que la base de la aplicación se encuentra en un equipo remoto, como en un escenario basado en web de Internet Explorer, el archivo de configuración debe estar descargado.

Para los ejecutables de cliente, el archivo de configuración de la aplicación reside en el mismo directorio que el ejecutable de la aplicación y tiene el mismo nombre base que el ejecutable con la extensión .config. Por ejemplo, el archivo de configuración de C:\Program Files\Myapp\Myapp.exe es C:\Program Files\Myapp\Myapp.exe.config. En un escenario basado en explorador, el archivo HTML debe usar el elemento **\<link>** para apuntar explícitamente al archivo de configuración.

El código siguiente proporciona un ejemplo sencillo de un archivo de configuración de la aplicación. Este ejemplo agrega un <xref:System.Diagnostics.TextWriterTraceListener> a la colección <xref:System.Diagnostics.Debug.Listeners%2A> para habilitar la grabación de la información de depuración en un archivo.

```xml
<configuration>
   <system.diagnostics>
      <trace useGlobalLock="false" autoflush="true" indentsize="0">
         <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />
         </listeners>
      </trace>
   </system.diagnostics>
</configuration>
```

### <a name="publisher-policy-file"></a>Archivo de directiva de edición

En segundo lugar, el tiempo de ejecución examina el archivo de directiva de edición, si existe. Los archivos de directiva de edición se distribuyen mediante un editor de componentes como una corrección o actualización de un componente compartido. Estos archivos contienen información de compatibilidad emitida por el editor del componente compartido, que dirige una referencia de ensamblado a una nueva versión. A diferencia de los archivos de configuración de la aplicación y del equipo, los archivos de directiva de edición están contenidos en su propio ensamblado, que debe instalarse en la caché global de ensamblados.

A continuación se muestra un ejemplo de un archivo de configuración de directiva de edición:

```xml
<configuration>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">

            <dependentAssembly>
                <assemblyIdentity name="asm6" publicKeyToken="c0305c36380ba429" />
                <bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0"/>
            </dependentAssembly>

        </assemblyBinding>
    </runtime>
</configuration>
```

Para crear un ensamblado, puede usar la herramienta [Al.exe (Assembly Linker)](../tools/al-exe-assembly-linker.md) con un comando como el siguiente:

```console
Al.exe /link:asm6.exe.config /out:policy.3.0.asm6.dll /keyfile: compatkey.dat /v:3.0.0.0
```

`compatkey.dat` es un archivo de clave de nombre seguro. Este comando crea un ensamblado con nombre seguro que se puede colocar en la caché global de ensamblados.

> [!NOTE]
> La directiva de edición afecta a todas las aplicaciones que usan un componente compartido.

El archivo de configuración de directiva de edición reemplaza la información de versión que procede de la aplicación (es decir, que procede del manifiesto del ensamblado o del archivo de configuración de la aplicación). Si no hay ninguna instrucción en el archivo de configuración de la aplicación para redirigir la versión especificada en el manifiesto del ensamblado, el archivo de directiva de edición reemplaza la versión especificada en el manifiesto del ensamblado. Sin embargo, si hay una instrucción de redirección en el archivo de configuración de la aplicación, la directiva de edición reemplaza esa versión, en lugar de la especificada en el manifiesto.

Cuando se actualiza un componente compartido y todas las aplicaciones que lo usan deben seleccionar la nueva versión de dicho componente, se usa un archivo de directiva de edición. La configuración del archivo de directiva de edición invalida la configuración del archivo de configuración de la aplicación, a menos que este último aplique el modo seguro.

#### <a name="safe-mode"></a>Modo seguro

Los archivos de directiva de edición por lo general se instalan explícitamente como parte de un Service Pack o de una actualización del programa. Si hay algún problema con el componente compartido actualizado, puede pasar por alto los reemplazos realizados en el archivo de directiva de edición usando el modo seguro. El modo seguro está determinado por el elemento **\<publisherPolicy apply="yes**&#124;**no"/>** , que se encuentra solo en el archivo de configuración de la aplicación. Especifica si la información de configuración de directiva de edición debe quitarse del proceso de enlace.

El modo seguro se puede establecer para toda la aplicación o para los ensamblados seleccionados. Es decir, puede desactivar la directiva para todos los ensamblados que componen la aplicación, o bien activarla para algunos ensamblados pero no para otros. Para aplicar de forma selectiva la directiva de publicador a los ensamblados que componen una aplicación, establezca **\<publisherPolicy apply\=no/>** y especifique los ensamblados que desee que se vean afectados mediante el elemento \<**dependentAssembly**>. Para aplicar la directiva de edición a todos los ensamblados que componen la aplicación, establezca **\<publisherPolicy apply\=no/>** sin elementos de ensamblado dependiente. Para obtener más información acerca de la configuración, consulte [Configurar aplicaciones con archivos de configuración](../configure-apps/index.md).

### <a name="machine-configuration-file"></a>Archivo de configuración del equipo

En tercer lugar, el tiempo de ejecución examina el archivo de configuración del equipo. Este archivo, denominado Machine.config, reside en el equipo local, el subdirectorio Config del directorio raíz donde está instalado el tiempo de ejecución. Los administradores pueden usar este archivo para especificar las restricciones de enlace de ensamblado locales de ese equipo. La configuración incluida en el archivo de configuración del equipo tiene prioridad sobre otras opciones de configuración; sin embargo, esto no significa que todos los valores de configuración deban colocarse en este archivo. La versión determinada por el archivo de directiva del administrador es final y no se puede invalidar. Los reemplazos especificados en el archivo Machine.config afectan a todas las aplicaciones. Para obtener más información acerca de los archivos de configuración, consulte [Configurar aplicaciones con archivos de configuración](../configure-apps/index.md).

<a name="step2"></a>

## <a name="step-2-checking-for-previously-referenced-assemblies"></a>Paso 2: Comprobación de los ensamblados a los que se ha hecho referencia previamente

Si el ensamblado solicitado también se solicitó en llamadas anteriores, Common Language Runtime usa el ensamblado que ya está cargado. Esto puede tener consecuencias cuando se asignan nombres a los ensamblados que componen una aplicación. Para obtener más información sobre los nombres de ensamblados, vea [Nombres de ensamblados](../../standard/assembly/names.md).

Si una solicitud anterior para el ensamblado produjo un error, las solicitudes posteriores para el ensamblado producen un error inmediatamente sin intentar cargar el ensamblado. A partir de .NET Framework versión 2.0, los errores de enlace de ensamblado se almacenan en caché y la información en caché se usa para determinar si se intenta cargar el ensamblado.

> [!NOTE]
> Para revertir al comportamiento de .NET Framework versiones 1.0 y 1.1, que no almacenaban en caché los errores de enlace, incluya el elemento [\<disableCachingBindingFailures> ](../configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md) en el archivo de configuración.

<a name="step3"></a>

## <a name="step-3-checking-the-global-assembly-cache"></a>Paso 3: Comprobación de la memoria caché global de ensamblados

Para los ensamblados con nombre seguro, el proceso de enlace continúa con la búsqueda en la caché global de ensamblados. La caché global de ensamblados almacena los ensamblados que varias aplicaciones pueden usar en un equipo. Todos los ensamblados de la caché global de ensamblados deben tener nombres seguros.

<a name="step4"></a>

## <a name="step-4-locating-the-assembly-through-codebases-or-probing"></a>Paso 4: Localización del ensamblado a través de códigos base o sondeos

Una vez determinada la versión correcta del ensamblado usando la información contenida en la referencia del ensamblado que realiza la llamada y en los archivos de configuración, y una vez protegida la caché global de ensamblados (solo para ensamblados con nombre seguro), Common Language Runtime intenta buscar el ensamblado. El proceso de buscar un ensamblado conlleva los pasos siguientes:

1. Si se encuentra un elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) en el archivo de configuración de la aplicación, el tiempo de ejecución comprueba la ubicación especificada. Si se encuentra una coincidencia, se usa ese ensamblado y no se realiza ningún sondeo. Si no se encuentra ahí el ensamblado, se produce un error en la solicitud de enlace.

2. Entonces, el tiempo de ejecución sondea el ensamblado al que se hace referencia usando las reglas que se especifican más adelante en esta sección.

> [!NOTE]
> Si tiene varias versiones de un ensamblado en un directorio y desea hacer referencia a una versión concreta de dicho ensamblado, debe usar el elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) en lugar del atributo `privatePath` del elemento [\<probing>](../configure-apps/file-schema/runtime/probing-element.md). Si usa el elemento [\<probing>](../configure-apps/file-schema/runtime/probing-element.md), el tiempo de ejecución detiene el sondeo la primera vez que encuentra un ensamblado que coincida con el nombre sencillo de ensamblado al que se hace referencia, tanto si es una coincidencia correcta como si no. Si es una coincidencia correcta, se usa dicho ensamblado. Si no es una coincidencia correcta, detiene el sondeo y el enlace produce un error.

### <a name="locating-the-assembly-through-codebases"></a>Ubicar el ensamblado a través de códigos base

Se puede proporcionar información de código base mediante un elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración. Este código base siempre se comprueba antes de que el tiempo de ejecución intente sondear el ensamblado al que se hace referencia. Si un archivo de directiva de edición que contiene la redirección de versión final también contiene un elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md), dicho elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) es el que se usa. Por ejemplo, si el archivo de configuración de la aplicación especifica un elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) y un archivo de directiva de edición que está reemplazando la información de la aplicación también especifica un elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md), se usa el elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) del archivo de directiva de edición.

Si no se encuentra ninguna coincidencia en la ubicación especificada por el elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md), se produce un error en la solicitud de enlace y no se realizan más acciones. Si el tiempo de ejecución determina que un ensamblado coincide con los criterios del ensamblado que realiza la llamada, usa dicho ensamblado. Cuando se carga el archivo especificado por el elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) determinado, el tiempo de ejecución realiza una comprobación para asegurarse de que el nombre, la versión, la referencia cultural y la clave pública coinciden con la referencia del ensamblado de llamada.

> [!NOTE]
> Los ensamblados a los que se hace referencia fuera del directorio raíz de la aplicación deben tener nombres seguros y deben estar instalados en la caché global de ensamblados o especificarse usando el elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md).

### <a name="locating-the-assembly-through-probing"></a>Ubicar el ensamblado a través del sondeo

Si no hay ningún elemento [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) en el archivo de configuración de la aplicación, el tiempo de ejecución sondea el ensamblado usando cuatro criterios:

- Base de la aplicación, que es la ubicación raíz donde se ejecuta la aplicación.

- Referencia cultural, que es el atributo de referencia cultural del ensamblado al que se hace referencia.

- Nombre, que es el nombre del ensamblado al que se hace referencia.

- El atributo `privatePath` del elemento [\<probing>](../configure-apps/file-schema/runtime/probing-element.md), que es la lista definida por el usuario de subdirectorios bajo la ubicación raíz. Esta ubicación puede especificarse en el archivo de configuración de la aplicación y en el código administrado mediante la propiedad <xref:System.AppDomainSetup.PrivateBinPath?displayProperty=nameWithType> para un dominio de aplicación. Cuando se especifica en código administrado, se sondea primero el código administrado `privatePath` , seguido de la ruta de acceso especificada en el archivo de configuración de la aplicación.

#### <a name="probing-the-application-base-and-culture-directories"></a>Sondear los directorios de base de la aplicación y de referencia cultural

El tiempo de ejecución siempre empieza a sondear en la base de la aplicación, que puede ser una dirección URL o el directorio raíz de la aplicación en un equipo. Si el ensamblado al que se hace referencia no se encuentra en la base de la aplicación y si no se proporciona ninguna información de referencia cultural, el tiempo de ejecución busca cualquier subdirectorio con el nombre del ensamblado. Los directorios sondeados incluyen:

- [base de la aplicación] / [nombre de ensamblado].dll

- [base de la aplicación] / [nombre de ensamblado] / [nombre de ensamblado].dll

Si se especifica información de referencia cultural para el ensamblado al que se hace referencia, solo se busca en los directorios siguientes:

- [base de la aplicación] / [referencia cultural] / [nombre de ensamblado].dll

- [base de la aplicación] / [referencia cultural] / [nombre de ensamblado] / [nombre de ensamblado].dll

#### <a name="probing-with-the-privatepath-attribute"></a>Sondear con el atributo privatePath

Además de los subdirectorios de referencia cultural y los subdirectorios con el nombre del ensamblado al que se hace referencia, el tiempo de ejecución también sondea los directorios especificados mediante el atributo `privatePath` del elemento [\<probing>](../configure-apps/file-schema/runtime/probing-element.md). Los directorios especificados mediante el atributo `privatePath` debe ser subdirectorios del directorio raíz de la aplicación. Los directorios sondeados varían en función de si se incluye información de referencia cultural en la solicitud del ensamblado al que se hace referencia.

El tiempo de ejecución detiene el sondeo la primera vez que encuentra un ensamblado que coincida con el nombre sencillo de ensamblado al que se hace referencia, tanto si es una coincidencia correcta como si no. Si es una coincidencia correcta, se usa dicho ensamblado. Si no es una coincidencia correcta, detiene el sondeo y el enlace produce un error.

Si se incluye la referencia cultural, se busca en los directorios siguientes:

- [base de la aplicación] / [binpath] / [referencia cultural] / [nombre de ensamblado].dll

- [base de la aplicación] / [binpath] / [referencia cultural] / [nombre de ensamblado] / [nombre de ensamblado].dll

Si no se incluye información de referencia cultural, se busca en los directorios siguientes:

- [base de la aplicación] / [binpath] / [nombre de ensamblado].dll

- [base de la aplicación] / [binpath] / [nombre de ensamblado] / [nombre de ensamblado].dll

#### <a name="probing-examples"></a>Ejemplos de sondeo

Dada la siguiente información:

- Nombre del ensamblado al que se hace referencia: myAssembly

- Directorio raíz de la aplicación: `http://www.code.microsoft.com`

- El elemento [\<probing>](../configure-apps/file-schema/runtime/probing-element.md) del archivo de configuración especifica: bin

- Referencia cultural: de

El tiempo de ejecución sondea las direcciones URL siguientes:

- `http://www.code.microsoft.com/de/myAssembly.dll`

- `http://www.code.microsoft.com/de/myAssembly/myAssembly.dll`

- `http://www.code.microsoft.com/bin/de/myAssembly.dll`

- `http://www.code.microsoft.com/bin/de/myAssembly/myAssembly.dll`

##### <a name="multiple-assemblies-with-the-same-name"></a>Varios ensamblados con el mismo nombre

En el ejemplo siguiente se muestra cómo configurar varios ensamblados con el mismo nombre.

```xml
<dependentAssembly>
   <assemblyIdentity name="Server" publicKeyToken="c0305c36380ba429" />
   <codeBase version="1.0.0.0" href="v1/Server.dll" />
   <codeBase version="2.0.0.0" href="v2/Server.dll" />
</dependentAssembly>
```

#### <a name="other-locations-probed"></a>Otras ubicaciones sondeadas

La ubicación del ensamblado también puede determinarse mediante el contexto de enlace actual. Esto suele ocurrir cuando se usa el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> y en escenarios de interoperabilidad COM. Si un ensamblado usa el método <xref:System.Reflection.Assembly.LoadFrom%2A> para hacer referencia a otro ensamblado, la ubicación del ensamblado que realiza la llamada se considera una pista sobre dónde se encontrará el ensamblado al que se hace referencia. Si se encuentra una coincidencia, se carga dicho ensamblado. Si no se encuentra ninguna coincidencia, el tiempo de ejecución prosigue con la semántica de búsqueda y, a continuación, consulta a Windows Installer para proporcionar el ensamblado. Si no se proporciona ningún ensamblado que coincida con la solicitud de enlace, se produce una excepción. Esta excepción es una <xref:System.TypeLoadException> en código administrado si se hacía referencia a un tipo, o una <xref:System.IO.FileNotFoundException> si no se encontró un ensamblado que se estuviera cargando.

Por ejemplo, si Assembly1 hace referencia a Assembly2 y Assembly1 se descargó desde `http://www.code.microsoft.com/utils`, dicha ubicación se considera una pista sobre dónde buscar Assembly2.dll. Después, el runtime busca el ensamblado en `http://www.code.microsoft.com/utils/Assembly2.dll` y `http://www.code.microsoft.com/utils/Assembly2/Assembly2.dll`. Si no se encuentra Assembly2 en ninguna de estas ubicaciones, el tiempo de ejecución consulta a Windows Installer.

## <a name="see-also"></a>Vea también

- [Procedimientos recomendados para cargar ensamblados](best-practices-for-assembly-loading.md)
- [Implementación](index.md)
