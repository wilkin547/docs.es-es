---
title: Globalización e ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: ca579e837b801de237859963ede0e5a9a4bfbcbf
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439474"
---
# <a name="net-globalization-and-icu"></a>Globalización de .NET e ICU

Antes, las API de globalización de .NET usaban diferentes bibliotecas subyacentes en distintas plataformas. En UNIX, las API usaban [Componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home) y, en Windows, usaban [Compatibilidad con el idioma nacional (NLS)](/windows/win32/intl/national-language-support). Esto producía algunas diferencias de comportamiento en varias API de globalización al ejecutar aplicaciones en distintas plataformas. Las diferencias de comportamiento eran evidentes en estas áreas:

- Referencias culturales y datos culturales
- Uso de mayúsculas y minúsculas en cadenas
- Ordenación y búsqueda de cadenas
- Criterios de ordenación
- Normalización de cadenas
- Compatibilidad con nombres de dominio internacionalizados (IDN)
- Nombre para mostrar de la zona horaria en Linux

A partir de .NET 5.0, los desarrolladores tienen más control sobre la biblioteca subyacente que se usa, lo que permite a las aplicaciones evitar diferencias entre plataformas.

## <a name="icu-on-windows"></a>ICU en Windows

La actualización de mayo de 2019 de Windows 10 y las versiones posteriores incluyen [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) como parte del sistema operativo, y .NET 5.0 y las versiones posteriores usan ICU de forma predeterminada. Cuando se ejecuta en Windows, .NET 5.0 y las versiones posteriores intentan cargar `icu.dll` y, si está disponible, se usa para la implementación de globalización. Si no se puede encontrar o cargar la biblioteca de ICU, como cuando se ejecuta en versiones anteriores de Windows, .NET 5.0 y las versiones posteriores se revierten a la implementación basada en NLS.

> [!NOTE]
> Incluso cuando se usa ICU, los miembros de `CurrentCulture`, `CurrentUICulture` y `CurrentRegion` siguen usando las API del sistema operativo Windows para respetar la configuración de usuario.

### <a name="behavioral-differences"></a>Diferencias de comportamiento

Si actualiza la aplicación para que tenga como destino .NET 5, es posible que vea cambios en ella aunque no sea consciente de usar las instalaciones de globalización. En esta sección se enumera uno de los cambios de comportamiento que podría ver, pero también hay otros.

##### <a name="stringindexof"></a>String.IndexOf

Considere el código siguiente que llama a <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> para buscar el índice del carácter de nueva línea en una cadena.

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- En versiones anteriores de .NET en Windows, el fragmento de código imprime `6`.
- En .NET 5.0 y versiones posteriores en la actualización del 10 de mayo de 2019 de Windows, el fragmento de código imprime `-1`.

Para corregir este código mediante la realización de una búsqueda ordinal en lugar de una búsqueda según la referencia cultural, llame a la sobrecarga <xref:System.String.IndexOf(System.String,System.StringComparison)> y pase <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> como argumento.

Puede ejecutar las reglas de análisis de código [CA1307: Especificar StringComparison para mayor claridad](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309: Usar StringComparison ordinal](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) para buscar estos sitios de llamada en el código.

Para más información, consulte [Cambios de comportamiento al comparar cadenas en .NET 5 +](../base-types/string-comparison-net-5-plus.md).

### <a name="use-nls-instead-of-icu"></a>Uso de NLS en lugar de ICU

Si se usa ICU en lugar de NLS, se pueden producir diferencias de comportamiento con algunas operaciones relacionadas con la globalización. Para revertir al uso de NLS, los desarrolladores pueden rechazar la implementación de ICU. Las aplicaciones pueden habilitar el modo NLS de cualquiera de estas maneras:

- El archivo del proyecto:

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- En el archivo `runtimeconfig.json`:

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- Al establecer la variable de entorno `DOTNET_SYSTEM_GLOBALIZATION_USENLS` en el valor `true` o `1`.

> [!NOTE]
> Un valor establecido en el proyecto o en el archivo `runtimeconfig.json` tiene prioridad sobre la variable de entorno.

Para más información, vea [Valores de configuración de tiempo de ejecución](../../core/run-time-config/globalization.md#nls).

## <a name="app-local-icu"></a>ICU local de la aplicación

Cada versión de ICU puede tener incorporadas correcciones de errores, así como datos del Repositorio de datos comunes de configuración regional (CLDR) que describen los idiomas del mundo. El cambio entre las versiones de ICU puede afectar sutilmente al comportamiento de la aplicación cuando se trata de operaciones relacionadas con la globalización. Para que los desarrolladores de aplicaciones puedan garantizar la coherencia entre todas las implementaciones, .NET 5.0 y las versiones posteriores permiten que las aplicaciones de Windows y UNIX transporten y usen su propia copia de ICU.

Las aplicaciones pueden participar en un modo de implementación de ICU local de la aplicación de cualquiera de estas maneras:

- En el archivo del proyecto:

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- En el archivo `runtimeconfig.json`:

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- Al establecer la variable de entorno `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` en el valor `<suffix>:<version>` o `<version>`.

  `<suffix>`: sufijo opcional de menos de 36 caracteres de longitud, según las convenciones de empaquetado públicas de ICU. Al compilar un ICU personalizado, puede personalizarlo para generar los nombres de lib y los nombres de símbolos exportados para que contengan un sufijo, por ejemplo, `libicuucmyapp`, donde `myapp` es el sufijo.

  `<version>`: versión de ICU válida, por ejemplo, 67.1. Esta versión se usa para cargar los archivos binarios y obtener los símbolos exportados.

Para cargar el ICU cuando se establece el modificador local de la aplicación, .NET usa el método <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>, que sondea varias rutas de acceso. El método intenta buscar primero la biblioteca en la propiedad `NATIVE_DLL_SEARCH_DIRECTORIES`, que la crea el host dotnet basándose en el archivo `deps.json` de la aplicación. Para más información, vea [Sondeo predeterminado](../../core/dependency-loading/default-probing.md).

En el caso de las aplicaciones independientes, el usuario no tiene que hacer ninguna acción especial, aparte de asegurarse de que ICU está en el directorio de la aplicación (para las aplicaciones independientes, el directorio de trabajo tiene como valor predeterminado `NATIVE_DLL_SEARCH_DIRECTORIES`).

Si está usando ICU a través de un paquete NuGet, esto funciona en aplicaciones dependientes del marco. NuGet resuelve los recursos nativos y los incluye en el archivo `deps.json` y en el directorio de salida de la aplicación en el directorio `runtimes`. .NET lo carga desde allí.

En el caso de las aplicaciones dependientes del marco (no independientes) en las que se usa ICU desde una compilación local, debe realizar unos cuantos pasos más. El SDK de .NET todavía no tiene una característica para que los binarios nativos "sueltos" se incorporen en `deps.json` (vea [este problema del SDK](https://github.com/dotnet/sdk/issues/11373)). En su lugar, puede habilitarlo si agrega información adicional en el archivo de proyecto de la aplicación. Por ejemplo:

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

Debe realizar esto en todos los archivos binarios de ICU de los entornos de ejecución admitidos. Además, los metadatos de `NuGetPackageId` del grupo de elementos `RuntimeTargetsCopyLocalItems` deben coincidir con un paquete NuGet al que realmente hace referencia el proyecto.

### <a name="macos-behavior"></a>Comportamiento de macOS

El comportamiento que tiene `macOS` para resolver bibliotecas dinámicas dependientes a partir de los comandos de carga especificados en el archivo `match-o` es diferente al del cargador de Linux. En el cargador de Linux, .NET puede intentar `libicudata`, `libicuuc` y `libicui18n` (en ese orden) para satisfacer el gráfico de dependencias de ICU. Pero esto no funciona en macOS. Al crear ICU en macOS, se obtiene de forma predeterminada una biblioteca dinámica con estos comandos de carga en `libicuuc`. En el fragmento de código siguiente se muestra un ejemplo.

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

Estos comandos simplemente hacen referencia al nombre de las bibliotecas dependientes para los demás componentes de ICU. El cargador realiza la búsqueda según las convenciones de `dlopen`, lo que implica tener estas bibliotecas en los directorios del sistema o configurar env vars de `LD_LIBRARY_PATH` o tener ICU en el directorio de nivel de aplicación. Si no puede establecer `LD_LIBRARY_PATH` o asegurarse de que los binarios de ICU se encuentran en el directorio de nivel de aplicación, deberá realizar algún trabajo adicional.

Hay algunas directivas para el cargador, como `@loader_path`, que indican al cargador que busque esa dependencia en el mismo directorio que el binario con ese comando de carga. Hay dos formas de lograrlo:

- `install_name_tool -change`

  Ejecute los comandos siguientes:

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- Revisión de ICU para generar los nombres de instalación con `@loader_path`

  Antes de ejecutar autoconf (`./runConfigureICU`), cambie [estas líneas](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) a:

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a>ICU en WebAssembly

Hay disponible una versión de ICU que es específicamente para cargas de trabajo de WebAssembly. Esta versión proporciona compatibilidad de globalización con los perfiles de escritorio. Para reducir el tamaño del archivo de datos de ICU de 24 MB a 1,4 MB (o ~ 0,3 MB si está comprimido con Brotli), esta carga de trabajo tiene una serie de limitaciones.

No se admiten las siguientes API:

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

Las siguientes API se admiten con limitaciones:

- <xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> y <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> no admiten los formularios <xref:System.Text.NormalizationForm.FormKC> y <xref:System.Text.NormalizationForm.FormKD> poco usados.
- <xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> devuelve el mismo valor que <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.

Además, puede encontrar una lista de configuraciones regionales admitidas en el repositorio [dotnet/ICU](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).
