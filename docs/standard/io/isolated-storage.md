---
title: Almacenamiento aislado
description: Explore el almacenamiento aislado, que es un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de formas estándar de asociar código a los datos guardados.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data storage using isolated storage
- stores
- storing data using isolated storage
- isolated storage
- location of isolated storage in file system
- standardizing storage systems
- storing data using isolated storage, when not to use
- code, isolated storage
- isolated storage, options
- data storage using isolated storage, when not to use
- storing data using isolated storage, options
- isolated storage, when not to use
- data storage using isolated storage, options
- isolation
ms.assetid: aff939d7-9e49-46f2-a8cd-938d3020e94e
ms.openlocfilehash: 4ad7779b9810954d110af576dd834daf61888d59
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555925"
---
# <a name="isolated-storage"></a>Almacenamiento aislado

Para las aplicaciones de escritorio, el almacenamiento aislado es un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de modos estándar de asociar código a los datos guardados. La estandarización ofrece además otras ventajas. Los administradores pueden usar herramientas diseñadas para manipular el almacenamiento aislado para configurar el espacio de almacenamiento de archivos, establecer directivas de seguridad y eliminar los datos no utilizados. Con el almacenamiento aislado, el código ya no requiere rutas de acceso únicas para especificar ubicaciones seguras en el sistema de archivos y los datos están protegidos de otras aplicaciones que solo tienen acceso a un almacenamiento aislado. La información en código que indica la ubicación del área de almacenamiento de la aplicación no es necesaria.

> [!IMPORTANT]
> El almacenamiento aislado no está disponible para las aplicaciones de la Tienda Windows 8.x. En su lugar, use las clases de datos de la aplicación de los espacios de nombres `Windows.Storage` incluidas en la API de Windows Runtime para almacenar archivos y datos locales. Para más información, vea [Datos de aplicación](/previous-versions/windows/apps/hh464917(v=win.10)) en el Centro de desarrollo de Windows.

<a name="data_compartments_and_stores"></a>

## <a name="data-compartments-and-stores"></a>Compartimientos y almacenes de datos

Cuando una aplicación almacena datos en un archivo, el nombre de archivo y la ubicación de almacenamiento se deben elegir con cuidado para minimizar el riesgo de que otra aplicación llegue a conocer dicha ubicación, lo que la haría susceptible de recibir daños. Si no se dispone de un sistema estándar que controle estos problemas, el desarrollo de técnicas ad hoc para minimizar los conflictos de almacenamiento puede ser complicado, y los resultados poco confiables.

Con el almacenamiento aislado, los datos están siempre aislados por usuario y ensamblado. Las credenciales como el origen o el nombre seguro del ensamblado determinan la identidad del ensamblado. Los datos se pueden aislar también por el dominio de la aplicación, usando credenciales parecidas.

Al usar el almacenamiento aislado, las aplicaciones guardan los datos en un compartimiento de datos único asociado a algún aspecto de la identidad del código, como su publicador o signatura. El compartimiento de datos es abstracto, no una ubicación de almacenamiento concreta; está formado por uno o varios archivos de almacenamiento aislado, denominados almacenes, que contienen las ubicaciones reales del directorio donde están almacenados los datos. Por ejemplo, una aplicación puede tener un compartimiento de datos asociado, y un directorio del sistema de archivos implementaría el almacén que conserva de hecho los datos de esa aplicación. Los datos guardados en el almacén pueden ser de cualquier tipo, desde información de preferencia del usuario hasta el estado de la aplicación. Para el desarrollador, la ubicación del compartimiento de datos es transparente. Los almacenes residen normalmente en el cliente, pero una aplicación de servidor puede usar almacenes aislados para almacenar información suplantando al usuario en cuyo nombre está trabajando. El almacenamiento aislado también puede guardar información en un servidor con un perfil de usuario móvil para que éste pueda tener acceso a la información desde donde se encuentre.

<a name="quotas"></a>

## <a name="quotas-for-isolated-storage"></a>Cuotas para el almacenamiento aislado

Una cuota es un límite de la cantidad de almacenamiento aislado que se puede usar. La cuota contiene bytes de espacio de archivo además de la sobrecarga asociada al directorio y otra información del almacén. El almacenamiento aislado usa cuotas de permisos, que son límites de almacenamiento que se establecen mediante objetos <xref:System.Security.Permissions.IsolatedStoragePermission> . Si se intenta escribir datos que superan la cuota, se produce una excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException> .  La Directiva de seguridad, que se puede modificar con la herramienta Configuración de .NET Framework (Mscorcfg.msc), determina los permisos que se conceden al código. El código al que se le ha concedido el permiso <xref:System.Security.Permissions.IsolatedStoragePermission> está restringido para que no utilice más almacenamiento que el que permite la propiedad <xref:System.Security.Permissions.IsolatedStoragePermission.UserQuota%2A> . Sin embargo, como el código puede omitir las cuotas de permisos presentando distintas identidades de usuario, dichas cuotas sirven como directrices sobre cómo debe comportarse el código y no como un límite estricto del comportamiento del código.

Las cuotas no se aplican a los almacenes móviles. Por ello, para que el código los use es necesario un nivel de permiso algo más alto. Los valores de enumeración <xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByRoamingUser> y <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByRoamingUser> especifican un permiso para usar el almacenamiento aislado para un usuario móvil.

<a name="secure_access"></a>

## <a name="secure-access"></a>Acceso seguro

La utilización de un almacenamiento aislado permite que las aplicaciones que no son de plena confianza almacenen datos de una forma controlada por la directiva de seguridad del equipo. Esto resulta especialmente útil para componentes descargados que quizás el usuario desee usar con cautela. La directiva de seguridad raramente concede este tipo de permiso de código cuando se tiene acceso al sistema de archivos mediante los mecanismos de E/S estándar. Sin embargo, de forma predeterminada, el código que se ejecuta desde el equipo local, una red local o Internet tiene derecho a utilizar almacenamiento aislado.

Los administradores pueden limitar la cantidad de almacenamiento aislado de que disponen un usuario o una aplicación, basándose en un nivel de confianza adecuado. Además, los administradores pueden quitar los datos que se conservan de un usuario por completo. Para crear o tener acceso al almacenamiento aislado, el código debe disponer del permiso <xref:System.Security.Permissions.IsolatedStorageFilePermission> correspondiente.

El código debe tener todos los derechos del sistema operativo de plataforma nativa necesarios para tener acceso al almacenamiento aislado. Se deben cumplir las listas de control de acceso (ACL) que controlan qué usuarios tienen derechos para usar el sistema de archivos. Las aplicaciones de .NET Framework ya tienen los derechos de sistema operativo para tener acceso al almacenamiento aislado a menos que lleven a cabo una suplantación (específica de plataforma). En ese caso, la aplicación tiene la responsabilidad de garantizar que la identidad del usuario suplantado disponga de los derechos de sistema operativo adecuados para tener acceso al almacenamiento aislado. Este acceso proporciona una forma cómoda para que el código que se ejecuta o se descarga desde Web lea y escriba en un área de almacenamiento relacionada con un usuario concreto.

Para controlar el acceso al almacenamiento aislado, Common Language Runtime usa objetos <xref:System.Security.Permissions.IsolatedStorageFilePermission> . Cada objeto tiene propiedades que especifican los valores siguientes:

- Uso permitido, que indica el tipo de acceso permitido. Los valores son miembros de la enumeración <xref:System.Security.Permissions.IsolatedStorageContainment> . Para obtener más información sobre estos valores, vea la tabla de la sección siguiente.

- Cuota de almacenamiento, como se describe en la sección anterior.

El runtime exige el permiso <xref:System.Security.Permissions.IsolatedStorageFilePermission> la primera vez que el código intenta abrir un almacén. Decide si debe conceder este permiso basándose en el nivel de confianza del código. Si se concede el permiso, los valores de uso permitido y cuota de almacenamiento se determinan mediante la directiva de seguridad y la solicitud del código de <xref:System.Security.Permissions.IsolatedStorageFilePermission>. La directiva de seguridad se configura mediante la herramienta Configuración de .NET Framework (Mscorcfg.msc). Se comprueban todos los llamadores de la pila de llamadas, para garantizar que cada llamador tiene al menos el uso permitido adecuado. El motor en tiempo de ejecución comprueba también la cuota impuesta en el código que abrió o creó el almacén en que se va a guardar el archivo. Si se cumplen estas condiciones, se concede el permiso. La cuota se vuelve a comprobar cada vez que se escribe un archivo en el almacén.

El código de la aplicación no necesita solicitar permiso porque Common Language Runtime concederá el <xref:System.Security.Permissions.IsolatedStorageFilePermission> adecuado basándose en la directiva de seguridad. Sin embargo, existen buenas razones para solicitar permisos concretos que necesita la aplicación, como <xref:System.Security.Permissions.IsolatedStorageFilePermission>.

<a name="allowed_usage"></a>

## <a name="allowed-usage-and-security-risks"></a>Uso permitido y riesgos de seguridad

El uso permitido que especifica <xref:System.Security.Permissions.IsolatedStorageFilePermission> determina hasta qué punto el código podrá crear y usar el almacenamiento aislado. En la siguiente tabla se muestra la correspondencia entre el uso permitido especificado en el permiso y los tipos de aislamiento, y se resumen los riesgos de seguridad asociados a cada uso permitido.

|Uso permitido|Tipos de aislamiento|Riesgos de seguridad|
|-------------------|---------------------|---------------------|
|<xref:System.Security.Permissions.IsolatedStorageContainment.None>|No se permite el uso de almacenamiento aislado.|No hay ningún riesgo de seguridad.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>|Aislamiento por usuario, dominio y ensamblado Cada ensamblado tiene un subalmacén separado dentro del dominio. Los almacenes que usan este permiso también están aislados de forma implícita por equipo.|Este nivel de permiso deja los recursos abiertos a un sobreuso no autorizado, aunque las cuotas impuestas lo hacen más difícil. Se denomina ataque de denegación de servicio.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByRoamingUser>|Igual que `DomainIsolationByUser`, pero el almacén se guarda en una ubicación que se trasladará si están habilitados los perfiles de usuario móvil y no se imponen cuotas.|Como las cuotas deben estar deshabilitadas, los recursos de almacenamiento son más vulnerables a los ataques de denegación de servicio.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByUser>|Aislamiento por usuario y ensamblado. Los almacenes que usan este permiso también están aislados de forma implícita por equipo.|En este nivel se imponen cuotas para tratar de impedir los ataques de denegación de servicio. El mismo ensamblado de otro dominio puede tener acceso a este almacén, por lo que existe la posibilidad de que se filtre información de una aplicación a otra.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AssemblyIsolationByRoamingUser>|Igual que `AssemblyIsolationByUser`, pero el almacén se guarda en una ubicación que se trasladará si están habilitados los perfiles de usuario móvil y no se imponen cuotas.|Igual que en `AssemblyIsolationByUser`, pero sin cuotas; el riesgo de un ataque de denegación de servicio aumenta.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser>|Aislamiento por usuario. Normalmente, sólo usan este nivel de permiso las herramientas administrativas o de depuración.|El acceso con este permiso permite al código ver o eliminar cualquiera de los archivos o directorios de almacenamiento aislado de un usuario (independientemente del aislamiento de ensamblado). Existen, entre otros, riesgos de filtrado de información y de pérdida de datos.|
|<xref:System.Security.Permissions.IsolatedStorageContainment.UnrestrictedIsolatedStorage>|Aislamiento por todos los usuarios, dominios y ensamblados. Normalmente, sólo usan este nivel de permiso las herramientas administrativas o de depuración.|Este permiso crea una situación de riesgo total en todos los almacenes aislados de todos los usuarios.|

## <a name="safety-of-isolated-storage-components-with-regard-to-untrusted-data"></a>Seguridad de los componentes de almacenamiento aislado con respecto a los datos que no son de confianza

__Esta sección es aplicable a los siguientes marcos:__

- .NET Framework (todas las versiones)
- .NET Core 2.1+
- .NET 5.0+

Las plataformas .NET Framework y .NET Core ofrecen almacenamiento aislado como mecanismo para conservar los datos de un usuario, una aplicación o un componente. Se trata de un componente heredado especialmente diseñado para escenarios de seguridad de acceso del código en desuso.

Se pueden usar diversas API y herramientas de almacenamiento aislado para leer datos a través de límites de confianza. Por ejemplo, la lectura de datos desde un ámbito de nivel de máquina puede agregar datos de otras cuentas de usuario, posiblemente de menos confianza, a la máquina. Los componentes o las aplicaciones que leen desde ámbitos de almacenamiento aislado de nivel de máquina deben tener en cuenta las consecuencias de leer estos datos.

### <a name="security-sensitive-apis-that-can-read-from-the-machine-wide-scope"></a>API relativas a la seguridad que pueden leer el ámbito de nivel de máquina

Los componentes o las aplicaciones que llaman a cualquiera de las siguientes API se leen desde el ámbito de nivel de máquina:

* [IsolatedStorageFile.GetEnumerator](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.getenumerator) (pasa un ámbito que incluye la marca IsolatedStorageScope.Machine)
* [IsolatedStorageFile.GetMachineStoreForApplication](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.getmachinestoreforapplication)
* [IsolatedStorageFile.GetMachineStoreForAssembly](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.getmachinestoreforassembly)
* [IsolatedStorageFile.GetMachineStoreForDomain](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.getmachinestorefordomain)
* [IsolatedStorageFile.GetStore](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.getstore) (pasa un ámbito que incluye la marca IsolatedStorageScope.Machine)
* [IsolatedStorageFile.Remove](/dotnet/api/system.io.isolatedstorage.isolatedstoragefile.remove) (pasa un ámbito que incluye la marca `IsolatedStorageScope.Machine`)

La [herramienta de almacenamiento aislado](../../framework/tools/storeadm-exe-isolated-storage-tool.md) `storeadm.exe` se ve afectada si se llama con el modificador `/machine`, tal y como se muestra en el código siguiente:

```txt
storeadm.exe /machine [any-other-switches]
```

La herramienta de almacenamiento aislado se proporciona como parte de Visual Studio y el SDK de .NET Framework.

Si la aplicación no implica llamadas a las API anteriores, o si el flujo de trabajo no implica la llamada a `storeadm.exe` de esta manera, no se aplica este documento.

### <a name="impact-in-multi-user-environments"></a>Efecto en entornos multiusuario

Como se mencionó anteriormente, el efecto en la seguridad de estas API se deriva de que los datos escritos en un entorno de confianza se leen en otro entorno de confianza. En general, el almacenamiento aislado usa una de estas tres ubicaciones para leer y escribir datos:

1. `%LOCALAPPDATA%\IsolatedStorage\`: Por ejemplo, `C:\Users\<username>\AppData\Local\IsolatedStorage\` para el ámbito `User`.
2. `%APPDATA%\IsolatedStorage\`: Por ejemplo, `C:\Users\<username>\AppData\Roaming\IsolatedStorage\` para el ámbito `User|Roaming`.
3. `%PROGRAMDATA%\IsolatedStorage\`: Por ejemplo, `C:\ProgramData\IsolatedStorage\` para el ámbito `Machine`.

Las dos primeras ubicaciones están aisladas por usuario. Windows garantiza que las distintas cuentas de usuario de una misma máquina no puedan acceder a las carpetas de perfil de usuario de las demás. Dos cuentas de usuario diferentes que utilizan los almacenes `User` o `User|Roaming` no verán los datos de la otra ni pueden interferir con los datos de la otra.

La tercera ubicación se comparte entre todas las cuentas de usuario de la máquina. Distintas cuentas pueden leer y escribir en esta ubicación y pueden ver los datos de las demás.

Las rutas de acceso anteriores pueden diferir en función de la versión de Windows en uso.

Ahora plantéese usar un sistema multiusuario con dos usuarios registrados _Mallory_ y _Bob_. Mallory tiene la capacidad de acceder a su directorio de perfil de usuario `C:\Users\Mallory\`, así como a la ubicación de almacenamiento compartida de nivel de máquina `C:\ProgramData\IsolatedStorage\`. No puede acceder al directorio de perfil de usuario de Bob `C:\Users\Bob\`.

Si Mallory quiere atacar a Bob, puede escribir datos en la ubicación de almacenamiento de nivel de máquina y luego intentar influir en Bob para que lea desde el almacén de nivel de máquina. Cuando Bob ejecute una aplicación que lea en este almacén, la aplicación operará en los datos que Mallory colocó en él, pero desde el contexto de una cuenta de usuario de Bob. En el resto de este documento se contemplan varios vectores de ataque y los pasos que pueden seguir las aplicaciones para minimizar el riesgo de estos ataques.

__Nota:__ Para que se produzca este tipo de ataque, Mallory necesita lo siguiente:

* Una cuenta de usuario en la máquina.
* La capacidad de colocar un archivo en una ubicación conocida en el sistema de archivos.
* Saber que, en algún momento, Bob ejecutará una aplicación que intente leer estos datos.

No se trata de vectores de amenazas que se aplican a entornos de escritorio de un solo usuario estándar, como equipos domésticos o estaciones de trabajo empresariales de un solo empleado.

#### <a name="elevation-of-privilege"></a>Elevación de privilegios

Un ataque de __elevación de privilegios__ se produce cuando la aplicación de Bob lee el archivo de Mallory y automáticamente intenta realizar alguna acción en función del contenido de esa carga. Plantéese usar una aplicación que lea el contenido de un script de inicio del almacén de nivel de máquina y pase ese contenido a `Process.Start`. Si Mallory puede colocar un script malintencionado dentro del almacén de nivel de máquina, cuando Bob inicia su aplicación:

* La aplicación analiza el script malintencionado de Mallory y lo ejecuta _en el contexto del perfil de usuario de Bob_.
* Mallory obtiene acceso a la cuenta de Bob en la máquina local.

#### <a name="denial-of-service"></a>Denegación de servicio

Un ataque por __denegación de servicio__ se produce cuando la aplicación de Bob lee el archivo de Mallory y se bloquea o deja de funcionar correctamente. Plantéese de nuevo usar la aplicación mencionada anteriormente, que intenta analizar un script de inicio desde el almacén de nivel de máquina. Si Mallory puede colocar un archivo con un contenido incorrecto dentro del almacén de nivel de máquina, podría:

* Hacer que la aplicación de Bob inicie una excepción al principio de la ruta de acceso de inicio.
* Evitar que la aplicación se inicie correctamente debido a la excepción.

Después, ha denegado a Bob la posibilidad de iniciar la aplicación en su propia cuenta de usuario.

#### <a name="information-disclosure"></a>Divulgación de información

Un ataque de __divulgación de información__ se produce cuando Mallory puede engañar a Bob para que revele el contenido de un archivo al que Mallory no tiene acceso normalmente. Tenga en cuenta que Bob tiene un archivo de secreto *C:\Users\Bob\secret.txt* que Mallory quiere leer. Mallory conoce la ruta de acceso a este archivo, pero no puede leerlo porque Windows le prohíbe obtener acceso al directorio del perfil de usuario de Bob.

En su lugar, Mallory coloca un vínculo físico en el almacén de nivel de máquina. Se trata de un tipo especial de archivo que no contiene ningún contenido, sino que apunta a otro archivo en el disco. Al intentar leer el archivo de vínculo físico, se leerá en su lugar el contenido del archivo de destino del vínculo. Después de crear el vínculo físico, Mallory todavía no puede leer el contenido del archivo porque no tiene acceso al destino (`C:\Users\Bob\secret.txt`) del vínculo. Sin embargo, Bob _sí_ tiene acceso a este archivo.

Cuando la aplicación de Bob lee desde el almacén de nivel de máquina, ahora lee involuntariamente el contenido de su archivo `secret.txt`, como si el propio archivo hubiera estado presente en el almacén de nivel de máquina. Cuando se cierra la aplicación de Bob, si intenta volver a guardar el archivo en el almacén de nivel de máquina, terminará colocando una copia real del archivo en el directorio *C:\ProgramData\IsolatedStorage\*. Dado que este directorio es legible para cualquier usuario de la máquina, Mallory ahora puede leer el contenido del archivo.

### <a name="best-practices-to-defend-against-these-attacks"></a>Procedimientos recomendados para defenderse frente a estos ataques

__Importante:__ Si su entorno tiene varios usuarios que no son de confianza mutua, __no__ llame a la API `IsolatedStorageFile.GetEnumerator(IsolatedStorageScope.Machine)` ni invoque la herramienta `storeadm.exe /machine /list`. Ambas acciones presuponen que trabajan en datos de confianza. Si un atacante puede inicializar una carga malintencionada en el almacén de nivel de máquina, esa carga puede conducir a un ataque de elevación de privilegios en el contexto del usuario que ejecuta estos comandos.

Si trabaja en un entorno multiusuario, reconsidere el uso de características de almacenamiento aislado que tengan como destino el ámbito de _máquina_. Si una aplicación debe leer datos de una ubicación de nivel de máquina, es preferible leer los datos de una ubicación en la que solo puedan escribir las cuentas de administrador. El directorio `%PROGRAMFILES%` y el subárbol del Registro `HKLM` son ejemplos de ubicaciones en las que solo pueden escribir los administradores y que pueden leer todos los usuarios. Por lo tanto, los datos leídos de esas ubicaciones se consideran de confianza.

Si una aplicación debe usar el ámbito _Machine_ en un entorno multiusuario, se valida el contenido de cualquier archivo que se lea desde el almacén de toda la máquina. Si la aplicación deserializa los gráficos de objetos de estos archivos, plantéese la posibilidad de usar serializadores más seguros como `XmlSerializer`, en lugar de serializadores peligrosos como `BinaryFormatter` o `NetDataContractSerializer`. Sea cauto con los gráficos de objetos profundamente anidados o los gráficos de objetos que realizan la asignación de recursos en función del contenido del archivo.

<a name="isolated_storage_locations"></a>

## <a name="isolated-storage-locations"></a>Ubicaciones del almacenamiento aislado

En ocasiones resulta útil comprobar un cambio en el almacenamiento aislado usando el sistema de archivos del sistema operativo. También puede que se desee conocer la ubicación de los archivos de almacenamiento aislado. La ubicación cambia dependiendo del sistema operativo. En la tabla siguiente se muestran las ubicaciones raíz en que se crea el almacenamiento aislado en algunos de los sistemas operativos más frecuentes. Busque el directorio Microsoft\IsolatedStorage bajo esta ubicación raíz. Para que se muestren los archivos y carpetas ocultos y ver el almacenamiento aislado en el sistema de archivos debe cambiar la configuración de carpetas.

|Sistema operativo|Ubicación en el sistema de archivos|
|----------------------|-----------------------------|
|Windows 2000, Windows XP, Windows Server 2003 (actualización desde Windows NT 4.0)|Almacenes con movilidad =<br /><br /> \<SYSTEMROOT>\Profiles\\<usuario\>\Application Data<br /><br /> Almacenes sin movilidad =<br /><br /> \<SYSTEMROOT>\Profiles\\<usuario\>\Local Settings\Application Data|
|Windows 2000 - instalación nueva (y actualizaciones desde Windows 98 y Windows NT 3.51)|Almacenes con movilidad =<br /><br /> \<SYSTEMDRIVE>\Documents and Settings\\<usuario\>\Application Data<br /><br /> Almacenes sin movilidad =<br /><br /> \<SYSTEMDRIVE>\Documents and Settings\\<usuario\>\Local Settings\Application Data|
|Windows XP, Windows Server 2003 - instalación nueva (y actualizaciones desde Windows 2000 y Windows 98)|Almacenes con movilidad =<br /><br /> \<SYSTEMDRIVE>\Documents and Settings\\<usuario\>\Application Data<br /><br /> Almacenes sin movilidad =<br /><br /> \<SYSTEMDRIVE>\Documents and Settings\\<usuario\>\Local Settings\Application Data|
|Windows 8, Windows 7, Windows Server 2008, Windows Vista|Almacenes con movilidad =<br /><br /> \<SYSTEMDRIVE>\Users\\< usuario\>\AppData\Roaming<br /><br /> Almacenes sin movilidad =<br /><br /> \<SYSTEMDRIVE>\Users\\<usuario\>\AppData\Local|

<a name="isolated_storage_tasks"></a>

## <a name="creating-enumerating-and-deleting-isolated-storage"></a>Crear, enumerar y eliminar almacenamiento aislado

.NET Framework proporciona tres clases en el espacio de nombres <xref:System.IO.IsolatedStorage> para ayudar a realizar tareas relacionadas con el almacenamiento aislado:

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>deriva de <xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType> y proporciona administración básica de archivos de aplicación y ensamblado almacenados. Una instancia de la clase <xref:System.IO.IsolatedStorage.IsolatedStorageFile> representa un único almacén ubicado en el sistema de archivos.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> que deriva de <xref:System.IO.FileStream?displayProperty=nameWithType> y proporciona acceso a los archivos de un almacén.

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope> es una enumeración que permite crear y seleccionar un almacén con el tipo de aislamiento adecuado.

Las clases de almacenamiento aislado permiten crear, enumerar y eliminar almacenamiento aislado. Los métodos para realizar estas tareas están disponibles mediante el objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFile> . Algunas operaciones requieren disponer del permiso <xref:System.Security.Permissions.IsolatedStorageFilePermission> que representa el derecho a administrar el almacenamiento aislado. También podría ser necesario disponer de derechos de sistema operativo para tener acceso a un archivo o directorio.

Para ver una serie de ejemplos que muestran tareas de almacenamiento aislado habituales, vea los temas que aparecen en enumerados en [Temas relacionados](#related_topics).

<a name="scenarios_for_isolated_storage"></a>

## <a name="scenarios-for-isolated-storage"></a>Escenarios del almacenamiento aislado

El almacenamiento aislado resulta útil en muchas situaciones, incluidos estos cuatro escenarios:

- Controles descargados. Los controles de código administrado descargados de Internet no tienen permiso para escribir en el disco duro mediante clases de E/S normales, pero puede usar el almacenamiento aislado para almacenar la configuración del usuario y los estados de la aplicación.

- Almacenamiento de componentes compartidos. Los componentes compartidos entre aplicaciones pueden usar el almacenamiento aislado para proporcionar acceso controlado a los almacenes de datos.

- Almacenamiento en servidor. Las aplicaciones de servidor pueden usar el almacenamiento aislado para proporcionar almacenes individuales a un gran número de usuarios que hacen solicitudes a la aplicación. Puesto que el almacenamiento aislado siempre se aísla por usuario, el servidor debe suplantar al usuario que hace la solicitud. En este caso, los datos se aíslan basándose en la identidad de la entidad de seguridad, que es la identidad que usa la aplicación para diferenciar a los usuarios.

- Movilidad. Las aplicaciones pueden usar también el almacenamiento aislado con perfiles de usuario móvil. De esta manera los almacenes aislados de un usuario se pueden trasladar con el perfil.

No debe usar el almacenamiento aislado en las situaciones siguientes:

- Para guardar información confidencial, como claves o contraseñas sin cifrar, ya que el almacenamiento aislado no está protegido contra código de plena confianza, contra código no administrado ni contra usuarios de confianza del equipo.

- Para almacenar el código.

- Para almacenar los valores de configuración e implementación, que controlan los administradores. (Las preferencias de usuario no se consideran valores de configuración porque los administradores no las controlan.)

Muchas aplicaciones usan bases de datos para almacenar y aislar los datos y, en ese caso, una o varias filas de la base de datos pueden representar el almacenamiento de un usuario concreto. Se puede elegir usar el almacenamiento aislado en lugar de una base de datos si el número de usuarios es reducido, si la sobrecarga resultante de usar una base de datos es alta o si no existe una utilidad de bases de datos. Además, si la aplicación requiere un tipo de almacenamiento más flexible y complejo que el que ofrece una fila de una base de datos, el almacenamiento aislado puede ser una alternativa viable.

<a name="related_topics"></a>

## <a name="related-articles"></a>Artículos relacionados

|Title|Descripción|
|-----------|-----------------|
|[Tipos de aislamiento](types-of-isolation.md)|Describe los distintos tipos de aislamiento.|
|[Cómo: Obtener los almacenes de almacenamiento aislado](how-to-obtain-stores-for-isolated-storage.md)|Proporciona un ejemplo de uso de la clase <xref:System.IO.IsolatedStorage.IsolatedStorageFile> para obtener un almacén aislado por usuario y ensamblado.|
|[Cómo: Enumerar los almacenes de almacenamiento aislado](how-to-enumerate-stores-for-isolated-storage.md)|Muestra cómo utilizar el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> para calcular el tamaño de todo el almacenamiento aislado para el usuario.|
|[Cómo: Eliminar almacenes de almacenamiento aislado](how-to-delete-stores-in-isolated-storage.md)|Muestra cómo usar el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A?displayProperty=nameWithType> , de dos maneras diferentes, para eliminar almacenes aislados.|
|[Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado](how-to-anticipate-out-of-space-conditions-with-isolated-storage.md)|Muestra cómo medir el espacio que queda en un almacén aislado.|
|[Cómo: Crear archivos y directorios en almacenamiento aislado](how-to-create-files-and-directories-in-isolated-storage.md)|Proporciona ejemplos de creación de archivos y directorios en un almacén aislado.|
|[Cómo: Buscar archivos y directorios existentes en almacenamiento aislado](how-to-find-existing-files-and-directories-in-isolated-storage.md)|Muestra cómo leer la estructura y los archivos del directorio de almacenamiento aislado.|
|[Cómo: Leer y escribir en archivos en almacenamiento aislado](how-to-read-and-write-to-files-in-isolated-storage.md)|Proporciona un ejemplo de cómo escribir una cadena en un archivo de almacenamiento aislado y, a continuación, leerla.|
|[Cómo: Eliminar archivos y directorios en almacenamiento aislado](how-to-delete-files-and-directories-in-isolated-storage.md)|Muestra cómo eliminar archivos y directorios de almacenamiento aislado.|
|[E/S de archivos y secuencias](index.md)|Explica cómo puede realizar el acceso sincrónico y asincrónico a archivos y flujos de datos.|

<a name="reference"></a>

## <a name="reference"></a>Referencia

- <xref:System.IO.IsolatedStorage.IsolatedStorage?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream?displayProperty=nameWithType>

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=nameWithType>
