---
title: Mpgo.exe (Herramienta de optimización guiada por perfiles administrados)
ms.date: 03/30/2017
helpviewer_keywords:
- Mpgo.exe
- training scenarios, generating profiles with
- Managed Profile Guided Optimization Tool
- Ngen.exe
- Ngen.exe, profilers and native images
ms.assetid: f6976502-a000-4fbe-aaf5-a7aab9ce4ec2
ms.openlocfilehash: 0052475697dae2c3ad891db18d300b5ec08a7e62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180345"
---
# <a name="mpgoexe-managed-profile-guided-optimization-tool"></a>Mpgo.exe (Herramienta de optimización guiada por perfiles administrados)

La herramienta de optimización guiada por perfiles administrados (Mpgo.exe) es una herramienta de línea de comandos que usa escenarios de usuario final comunes para optimizar los ensamblados de imagen nativa creados por el [Generador de imágenes nativas (Ngen.exe)](ngen-exe-native-image-generator.md). Esta herramienta permite ejecutar escenarios de aprendizaje que generan datos de perfil. El [Generador de imágenes nativas (Ngen.exe)](ngen-exe-native-image-generator.md) usa estos datos para optimizar los ensamblados de aplicación de imagen nativa generados. Un escenario de aprendizaje es una ejecución de prueba de un uso previsto de la aplicación. Mpgo.exe está disponible en Visual Studio Ultimate 2012 y versiones posteriores. A partir de Visual Studio 2013, también puede usar Mpgo.exe para optimizar las aplicaciones de la Tienda Windows 8.x.  
  
La optimización guiada por perfiles mejora el tiempo de inicio de la aplicación, el uso de la memoria (tamaño del espacio de trabajo) y el rendimiento mediante la recopilación de datos procedentes de escenarios de aprendizaje y el uso de dichos datos para optimizar el diseño de las imágenes nativas.  
  
Si encuentra problemas de rendimiento relacionados con el tiempo de inicio y el tamaño del espacio de trabajo de los ensamblados de Lenguaje intermedio (IL), le recomendamos que primero use Ngen.exe para eliminar los costos de compilación Just-In-Time (JIT) y facilitar el uso compartido de código. Si necesita mejoras adicionales, después puede usar Mpgo.exe para optimizar aún más la aplicación. Puede usar los datos de rendimiento de los ensamblados de imagen nativa no optimizados como línea base para evaluar las mejoras de rendimiento. Mpgo.exe puede agilizar los tiempos de inicio en frío y reducir el tamaño del espacio de trabajo. Mpgo.exe agrega información a los ensamblados de IL que Ngen.exe usa para crear ensamblados de imagen nativa optimizados. Para obtener más información, vea la entrada sobre cómo [mejorar el rendimiento de inicio de las aplicaciones de escritorio](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/) del blog de .NET.  
  
Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7) con credenciales de administrador y escriba lo siguiente en dicho símbolo. Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
Para aplicaciones de escritorio:  
  
```console  
mpgo –Scenario <command> [-Import <directory>] –AssemblyList <assembly1>  <assembly2> ... -OutDir <directory> [options]  
```  
  
Para aplicaciones de la Tienda Windows 8.x:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
mpgo –Scenario <packageName> -AppID <appId> -Timeout <seconds>  
```  
  
## <a name="parameters"></a>Parámetros  
 Ninguno de los argumentos de Mpgo.exe distingue entre mayúsculas y minúsculas. Los comandos llevan como prefijo un guion.  
  
> [!NOTE]
> Puede usar `–Scenario` o `–Import` como comando requerido, pero no ambos. Si especifica la opción `–Reset`, no se usa ninguno de los parámetros requeridos.

|Parámetro requerido|Descripción|
|------------------------|-----------------|
|`-Scenario` \<*comando*><br /><br /> -O bien-<br /><br /> `-Scenario` \<*nombreDePaquete*><br /><br /> o bien<br /><br /> `-Import` \<*directorio*>|Para las aplicaciones de escritorio, use `–Scenario` para especificar el comando que ejecutará la aplicación que desea optimizar, incluidos los argumentos de la línea de comandos. Ponga tres conjuntos de comillas dobles alrededor de *command* si especifica una ruta de acceso que contiene espacios, por ejemplo: `mpgo.exe -scenario """C:\My App\myapp.exe""" -assemblylist """C:\My App\myapp.exe""" -outdir "C:\optimized files"`. No use un único juego de comillas dobles; no funcionará correctamente si *command* contiene espacios.<br /><br /> o bien<br /><br /> Para las aplicaciones de la Tienda Windows 8.x, use `–Scenario` para especificar el paquete para el que desea generar información de perfil. Si especifica el nombre para mostrar del paquete o su nombre de familia en lugar del nombre completo, Mpgo.exe seleccionará el paquete cuyo nombre coincide con el nombre proporcionado, si solo hay uno. Si hay varios paquetes que tienen el nombre especificado, Mpgo.exe le pedirá que elija uno.<br /><br /> -O bien-<br /><br /> Use `-Import` para especificar que desea usar los datos de optimización de ensamblados optimizados previamente para optimizar los ensamblados de `-AssemblyList`. *directory* especifica el directorio que contiene los archivos optimizados previamente. Los ensamblados especificados en `–AssemblyList` o `–AssemblyListFile` son las nuevas versiones de los ensamblados que se optimizarán usando los datos de los archivos importados. Usar los datos de optimización de una versión anterior de los ensamblados permite optimizar las versiones más recientes sin necesidad de volver a ejecutar el escenario.  Sin embargo, si los ensamblados importados y de destino incluyen código significativamente diferente, los datos de optimización resultarán ineficaces. Los nombres de ensamblados especificados en `–AssemblyList` o en `–AssemblyListFile` deben existir en el directorio especificado en `–Import`*directory*. Ponga tres conjuntos de comillas dobles alrededor de *directory* si especifica una ruta de acceso que contiene espacios.<br /><br /> Debe especificar `–Scenario` o `–Import`, pero no ambos parámetros.|
|`-OutDir` \<*directorio*>|El directorio en el que se colocarán los ensamblados optimizados. Si un ensamblado ya existe en la carpeta del directorio de salida, se crea una nueva copia y se anexa un número de índice al nombre del ensamblado; por ejemplo: *assemblyname*-1.exe. Ponga comillas dobles alrededor de *directory* si especifica una ruta que contiene espacios.|
|`-AssemblyList` \<*ensamblado1 ensamblado2 ...* ><br /><br /> -O bien-<br /><br /> `-AssemblyListFile` \<*archivo*>|Lista de ensamblados (incluidos los archivos .exe y .dll), separados por espacios, sobre los que desea recopilar información de perfil. Puede especificar `C:\Dir\*.dll` o `*.dll` para seleccionar todos los ensamblados existentes en el directorio de trabajo especificado o en el actual. Vea la sección Comentarios para obtener más información.<br /><br /> -O bien-<br /><br /> Archivo de texto que contiene la lista de ensamblados sobre la que desea recopilar información de perfil y en el que cada ensamblado aparece en una línea. Si un nombre de ensamblado comienza con un guion (-), use una lista de archivos de ensamblado o cambie el nombre del ensamblado.|
|`-AppID` \<*idApl*>|El identificador de la aplicación del paquete especificado. Si usa el carácter comodín (\*), Mpgo.exe intentará enumerar los AppID del paquete y recurrirá a \<*package_family_name*>!App si se produce un error. Si especifica una cadena que lleva como prefijo un signo de exclamación (!), Mpgo.exe concatenará el nombre de familia del paquete con el argumento proporcionado.|
|`-Timeout` \<*segundos*>|La cantidad de tiempo del que dispone la aplicación de la Tienda Windows 8.x para ejecutarse antes de que se cierre.|

|Parámetro opcional|Descripción|
|------------------------|-----------------|
|`-64bit`|Instrumenta los ensamblados para los sistemas de 64 bits.  Debe especificar este parámetro para los ensamblados de 64 bits, incluso si el ensamblado se declara como de 64 bits.|
|`-ExeConfig` \<*nombre de archivo*>|Especifica el archivo de configuración que el escenario usa para proporcionar la información de versión y del cargador.|
|`-f`|Fuerza la inclusión de datos de perfil en un ensamblado binario, incluso si está firmado.  Si el ensamblado está firmado, deberá firmarse de nuevo; de lo contrario, no podrá cargarse ni ejecutarse.|
|`-Reset`|Restablece el entorno para asegurarse de que una sesión de generación de perfiles anulada no afecta a los ensamblados; a continuación, la herramienta se cierra. El entorno se restablece de forma predeterminada antes y después de una sesión de generación de perfiles.|
|`-Timeout` \<*tiempo en segundos*>|Especifica la duración del proceso de generación de perfiles en segundos. Use un valor algo mayor que los tiempos de inicio observados para las aplicaciones GUI. Al final del período de tiempo de espera, los datos de perfil se graban aunque la aplicación continúe ejecutándose. Si no establece esta opción, la generación de perfiles continuará hasta el cierre de la aplicación, momento en el que se grabarán los datos.|
|`-LeaveNativeImages`|Especifica que las imágenes nativas instrumentadas no deben quitarse después de ejecutar el escenario. Esta opción se usa principalmente cuando se obtiene la aplicación que se especificó para la ejecución del escenario. Evitará que se vuelvan a crear las imágenes nativas en las ejecuciones posteriores de Mpgo.exe. Si especifica esta opción, cuando haya terminado de ejecutar la aplicación puede haber imágenes nativas huérfanas en la caché. En este caso, ejecute Mpgo.exe con el mismo escenario y la misma lista de ensamblados y use el parámetro `–RemoveNativeImages` para quitar estas imágenes nativas.|
|`-RemoveNativeImages`|Realiza la limpieza tras una ejecución en la que se especificó `–LeaveNativeImages`. Si especifica `-RemoveNativeImages`, Mpgo.exe omite cualquier argumento excepto `-64bit` y `–AssemblyList`, y se cierra después de quitar todas las imágenes nativas instrumentadas.|

## <a name="remarks"></a>Comentarios
 Puede usar `–AssemblyList` y `- AssemblyListFile` varias veces en la línea de comandos.

 Si no especifica nombres de rutas de acceso completas al especificar los ensamblados, Mpgo.exe busca en el directorio actual. Si especifica una ruta de acceso incorrecta, Mpgo.exe muestra un mensaje de error, pero continúa generando datos para otros ensamblados. Si especifica un ensamblado que no se carga durante el escenario de aprendizaje, no se genera ningún dato de aprendizaje para ese ensamblado.

 Si un ensamblado de la lista se encuentra en la caché global de ensamblados, no se actualizará con la información de perfil.  Quítelo de la caché global de ensamblados para que obtenga la información de perfil.

 Solo se recomienda usar Ngen.exe y Mpgo.exe en aplicaciones administradas grandes, ya que normalmente solo se aprecia la ventaja que conllevan las imágenes nativas precompiladas cuando se elimina de forma significativa la compilación JIT en tiempo de ejecución. Ejecutar Mpgo.exe en aplicaciones del estilo de "Hello World", que no usan el espacio de trabajo de manera intensiva, no solo no proporciona ninguna ventaja, sino que podría impedir que Mpgo.exe recopilara los datos de perfil.

> [!NOTE]
> No se recomienda usar Ngen.exe y Mpgo.exe en aplicaciones ASP.NET y servicios de Windows Communication Foundation (WCF).  
  
## <a name="to-use-mpgoexe"></a>Para usar Mpgo.exe  
  
1. Use un equipo que tenga instalados Visual Studio Ultimate 2012 y la aplicación.  
  
2. Ejecute Mpgo.exe como administrador con los parámetros necesarios.  En la sección siguiente hallará comandos de ejemplo.  
  
     Se crean los ensamblados optimizados de lenguaje intermedio (IL) en la carpeta especificada en el parámetro `–OutDir` (en los ejemplos, esta es la carpeta `C:\Optimized`).  
  
3. Reemplace los ensamblados de IL que usó para Ngen.exe por los nuevos ensamblados de IL que contienen información de perfil procedente del directorio especificado en `–OutDir`.  
  
4. Al instalar la aplicación (con las imágenes proporcionadas por Mpgo.exe) se instalan las imágenes nativas optimizadas.  
  
## <a name="suggested-workflow"></a>Flujo de trabajo sugerido  
  
1. Cree un conjunto de ensamblados optimizados de IL usando Mpgo.exe con el parámetro `–Scenario`.  
  
2. Proteja los ensamblados optimizados de IL en el control de código fuente.  
  
3. Durante el proceso de compilación, llame a Mpgo.exe con el parámetro `–Import` como paso posterior a la compilación para generar las imágenes de IL optimizadas que se pasarán a Ngen.exe.  
  
 Este proceso garantiza que todos los ensamblados dispongan de datos de optimización. Si protege los ensamblados optimizados actualizados (pasos 1 y 2) con más frecuencia, las cifras de rendimiento serán más coherentes durante el desarrollo del producto.  
  
## <a name="using-mpgoexe-from-visual-studio"></a>Uso de Mpgo.exe desde Visual Studio  
 Puede ejecutar Mpgo.exe desde Visual Studio (vea el artículo [Cómo: Especificación de eventos de compilación (C#)](/visualstudio/ide/how-to-specify-build-events-csharp)) con las siguientes restricciones:  
  
- No puede usar rutas de acceso entre comillas con barras diagonales finales, ya que las macros de Visual Studio también usan barras diagonales finales de forma predeterminada (por ejemplo, `–OutDir "C:\Output Folder\"` no es válido). Para evitar esta restricción, puede omitir la barra diagonal final (por ejemplo, en su lugar, use `-OutDir "$(OutDir)\"`).  
  
- De forma predeterminada, Mpgo.exe no está en la ruta de acceso de compilación de Visual Studio. Debe agregar la ruta de acceso a Visual Studio o especificar la ruta de acceso completa en la línea de comandos de Mpgo. Puede usar `–Scenario` o el parámetro `–Import` en el evento posterior a la compilación en Visual Studio. Pero el proceso típico es usar `–Scenario` una vez desde Símbolo del sistema para desarrolladores de Visual Studio y, luego, usar `–Import` para actualizar los ensamblados optimizados después de cada compilación; por ejemplo: `"C:\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\mpgo.exe" -import "$(OutDir)tmp" -assemblylist "$(TargetPath)" -outdir "$(OutDir)\"`.  
  
<a name="samples"></a>
## <a name="examples"></a>Ejemplos  
 El siguiente comando de Mpgo.exe usado desde Símbolo del sistema para desarrolladores de Visual Studio optimiza una aplicación fiscal:  
  
```console  
mpgo –scenario "C:\MyApp\MyTax.exe /params par" –AssemblyList Mytax.dll MyTaxUtil2011.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 El siguiente comando de Mpgo.exe optimiza una aplicación de sonido:  
  
```console  
mpgo –scenario "C:\MyApp\wav2wma.exe –input song1.wav –output song1.wma" –AssemblyList transcode.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 El siguiente comando de Mpgo.exe usa datos de ensamblados optimizados previamente para optimizar las versiones más recientes de los ensamblados:  
  
```console  
mpgo.exe -import "C:\Optimized" -assemblylist "C:\MyApp\MyTax.dll" "C:\MyApp\MyTaxUtil2011.dll" -outdir C:\ReOptimized  
```  
  
## <a name="see-also"></a>Vea también

- [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
- [Improving Launch Performance for your Desktop Applications (Mejorar el rendimiento de inicio de las aplicaciones de escritorio)](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/)
- [Información general de las mejoras de rendimiento en .NET 4.5](https://docs.microsoft.com/archive/msdn-magazine/2012/april/clr-an-overview-of-performance-improvements-in-net-4-5)
