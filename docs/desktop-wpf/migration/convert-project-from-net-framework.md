---
title: Migración de aplicaciones WPF a .NET Core 3.0
description: Obtenga información sobre cómo migrar una aplicación para Windows Presentation Foundation (WPF) a .NET Core 3.0.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: ccd2fc5a49d9c2d31c693e48099732614b568c7b
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507460"
---
# <a name="migrating-wpf-apps-to-net-core"></a>Migración de aplicaciones WPF a .NET Core

En este artículo se describen los pasos necesarios para migrar una aplicación para Windows Presentation Foundation (WPF) de .NET Framework a .NET Core 3.0. Si no tiene una aplicación WPF disponible para migrarla, pero quiere probar el proceso, puede usar la aplicación de ejemplo **Bean Trader** disponible en [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader). La aplicación original (que tiene como destino .NET Framework 4.7.2) está disponible en la carpeta NetFx\BeanTraderClient. En primer lugar, se explicarán los pasos necesarios para migrar aplicaciones en general y, después, se analizarán los cambios específicos que se aplican al ejemplo **Bean Trader**.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Para migrar a .NET Core, primero tendrá que:

01. Comprender y actualizar las dependencias de NuGet:

    01. Actualice las dependencias de NuGet al formato `<PackageReference>`.
    01. Revise las dependencias de NuGet de nivel superior para la compatibilidad con .NET Core o .NET Standard.
    01. Actualice los paquetes NuGet a las versiones más recientes.
    01. Use el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para comprender las dependencias de .NET.

01. Migrar el archivo del proyecto al nuevo formato de estilo de SDK:

    01. Elija como destino .NET Core y .NET Framework, o bien solo .NET Core.
    01. Copie las propiedades y elementos pertinentes del archivo del proyecto en el nuevo archivo del proyecto.

01. Corregir problemas de compilación:

    01. Agregue una referencia al paquete [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/).
    01. Busque y corrija las diferencias de nivel de API.
    01. Quite las secciones de *app.config* que no sean `appSettings` o `connectionStrings`.
    01. Vuelva a generar el código generado, si es necesario.

01. Pruebas en tiempo de ejecución:

    01. Confirme que la aplicación que ha migrado funciona según lo previsto.
    01. Tenga cuidado con las excepciones <xref:System.NotSupportedException>.

## <a name="about-the-sample"></a>Sobre el ejemplo

En este artículo se hace referencia a la [aplicación de ejemplo Bean Trader](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) porque usa una serie de dependencias similares a las que pueden tener las aplicaciones WPF del mundo real. La aplicación no es grande, pero está pensada como un paso adicional a "Hola mundo" en términos de complejidad. La aplicación muestra algunos problemas que los usuarios pueden encontrar al migrar aplicaciones reales. Se comunica con un servicio WCF, de modo que para que se ejecute correctamente, también tendrá que ejecutar el proyecto BeanTraderServer (disponible en el mismo repositorio de GitHub) y asegurarse de que la configuración de BeanTraderClient señala al punto de conexión correcto. (De forma predeterminada, en el ejemplo se supone que el servidor se ejecuta en el mismo equipo en *http://localhost:8090* , si inicia BeanTraderServer de manera local).

Tenga en cuenta que esta aplicación de ejemplo está pensada para mostrar las soluciones y los desafíos de portabilidad de .NET Core. No está diseñada para mostrar los procedimientos recomendados de WPF. De hecho, incluye deliberadamente algunos antipatrones para asegurarse de que al menos vea un par de retos interesantes durante la migración.

## <a name="getting-ready"></a>Preparación

El principal desafío de migrar una aplicación .NET Framework a .NET Core es que sus dependencias pueden funcionar de forma diferente o no hacerlo en absoluto. La migración es mucho más fácil de lo que solía ser; ahora muchos paquetes NuGet tienen como destino .NET Standard. A partir de .NET Core 2.0, las áreas expuestas de .NET Framework y .NET Core se han vuelto similares. Aun así, sigue habiendo algunas diferencias (tanto en la compatibilidad de los paquetes NuGet como en las API de .NET disponibles). El primer paso en la migración consiste en revisar las dependencias de la aplicación y asegurarse de que las referencias se encuentran en un formato que se pueda migrar con facilidad a .NET Core.

### <a name="upgrade-to-packagereference-nuget-references"></a>Actualización a las referencias `<PackageReference>` de NuGet

Los proyectos de .NET Framework más antiguos suelen mostrar sus dependencias de NuGet en un archivo *packages.config*. El nuevo formato de archivo del proyecto con estilo de SDK hace referencia a los paquetes NuGet como elementos [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) en el propio archivo csproj en lugar de hacerlo en un archivo de configuración independiente.

Al realizar la migración, el uso de referencias de estilo `<PackageReference>`ofrece dos ventajas:

- Este es el estilo de referencia de NuGet que se requiere para el nuevo archivo del proyecto de .NET Core. Si ya usa `<PackageReference>`, esos elementos de archivo del proyecto se pueden copiar y pegar directamente en el proyecto nuevo.
- A diferencia de un archivo packages.config, los elementos `<PackageReference>` solo hacen referencia a las dependencias de nivel superior de las que depende directamente el proyecto. Todos los demás paquetes NuGet transitivos se determinarán en tiempo de restauración y se registrarán en el archivo obj\project.assets.json generado de forma automática. Esto hace que sea mucho más fácil determinar qué dependencias tiene el proyecto, lo que resulta útil a la hora de determinar si las dependencias necesarias funcionarán en .NET Core o no.

El primer paso para migrar una aplicación de .NET Framework a .NET Core consiste en actualizarla para que use referencias `<PackageReference>` de NuGet. Visual Studio facilita este proceso. Simplemente haga clic con el botón derecho en el archivo *packages.config* del proyecto en el **Explorador de soluciones** de Visual Studio y, después, seleccione **Migrar packages.config a PackageReference**.

![Actualización a PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Aparece un cuadro de diálogo en el que se muestran las dependencias de NuGet de nivel superior calculadas y en el que se pregunta por otros paquetes NuGet que se deban promover al nivel superior. Ninguno de estos paquetes adicionales debe ser de nivel superior para el ejemplo Bean Trader, por lo que puede desactivar todas esas casillas. Después, haga clic en **Aceptar**; se quitará el archivo *packages.config* y se agregarán elementos `<PackageReference>` al archivo del proyecto.

Las referencias de estilo `<PackageReference>` no almacenan los paquetes NuGet localmente en una carpeta de paquetes. En su lugar, se almacenan de forma global como una optimización. Una vez que ha finalizado la migración, edite el archivo csproj y quite los elementos `<Analyzer>` que hacen referencia a los analizadores que anteriormente procedían del directorio *..\packages*. No se preocupe; como todavía tiene las referencias del paquete NuGet, los analizadores se incluirán en el proyecto. Solo tiene que limpiar los elementos `<Analyzer>` de estilo packages.config antiguos.

### <a name="review-nuget-packages"></a>Revisión de los paquetes NuGet

Ahora que puede ver los paquetes NuGet de nivel superior de los que depende el proyecto, puede revisar si están disponibles en .NET Core. Puede determinar si un paquete es compatible con .NET Core si examina sus dependencias en [nuget.org](https://www.nuget.org/). En el sitio [fuget.org](https://www.fuget.org/) creado por la comunidad se muestra esta información de forma destacada en la parte superior de la página de información del paquete.

Cuando el destino es .NET Core 3.0, los paquetes que tienen como destino .NET Core o .NET Standard deberían funcionar (ya que .NET Core implementa el área expuesta .NET Standard). En algunos casos, la versión específica de un paquete que se usa no tiene como destino .NET Core o .NET Standard, pero sí las versiones más recientes. En este caso, debería considerar la posibilidad de actualizar a la versión más reciente del paquete.

También puede usar paquetes que tengan como destino .NET Framework, aunque esto supone cierto riesgo. Se permiten las dependencias de .NET Core a .NET Framework porque las áreas expuestas de .NET Core y .NET Framework son lo suficientemente similares para que esas dependencias *suelan* funcionar. Pero si el paquete intenta usar una API de .NET que no está presente en .NET Core, se producirá una excepción en tiempo de ejecución. Por eso, solo debe hacer referencia a los paquetes de .NET Framework cuando no haya otras opciones disponibles y asumir que esto impone una carga de prueba.

Si hay paquetes a los que se hace referencia y que no tienen como destino .NET Core o .NET Standard, tendrá que pensar en otras alternativas:

- ¿Hay otros paquetes similares que se puedan usar en su lugar? En ocasiones, los autores de NuGet publican versiones ".Core" independientes de sus bibliotecas, destinadas en concreto a .NET Core. Los paquetes de Enterprise Library son un ejemplo de la publicación de alternativas ".NetCore" en la comunidad. En otros casos, hay SDK más recientes para un servicio determinado (a veces con otros nombres de paquete) disponibles para .NET Standard. Si no hay ninguna alternativa disponible, puede seguir usando los paquetes destinados a .NET Framework, pero tenga en cuenta que tendrá que probarlos exhaustivamente una vez que se ejecuten en .NET Core.

El ejemplo Bean Trader tiene las siguientes dependencias de NuGet de nivel superior:

- [**Castle.Windsor, versión 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Este paquete tiene como destino .NET Standard 1.6, por lo que funciona en .NET Core.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, versión 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Se trata de un metapaquete, por lo que no es evidente de inmediato qué plataformas admite, pero en la [documentación](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) se indica que su versión más reciente (2.9.2) funcionará para .NET Framework y .NET Core.

- [**Nito.AsyncEx, versión 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Este paquete no tiene como destino .NET Core, pero la versión más reciente 5.0 sí lo hace. Esto es habitual cuando se realiza la migración, ya que a muchos paquetes NuGet se les ha agregado recientemente compatibilidad con .NET Standard, pero las versiones de proyecto anteriores solo tendrán como destino .NET Framework. Si la diferencia de versión es solo de versión secundaria, a menudo es fácil actualizar a la versión más reciente. Como este es un cambio de versión principal, tendrá que realizar la actualización con precaución, ya que podría haber cambios importantes en el paquete. Pero el futuro parece prometedor.

- [**MahApps.Metro, versión 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Este paquete tampoco tiene como destino .NET Core, pero una versión preliminar más reciente (2.0-alpha) sí lo hace. De nuevo, debe tener en cuenta los cambios importantes, pero el paquete más reciente es alentador.

Todas las dependencias de NuGet del ejemplo Bean Trader tienen como destino .NET Standard o .NET Core, o bien versiones más recientes que sí lo hacen, por lo que no es probable que haya problemas de bloqueo.

### <a name="upgrade-nuget-packages"></a>Actualización de paquetes NuGet

Si es posible, en este momento sería conveniente actualizar las versiones de todos los paquetes que solo tienen como destino .NET Core o .NET Standard con versiones más recientes (con el proyecto todavía destinado a .NET Framework) para detectar y resolver los cambios más importantes al principio.

Si prefiere no realizar cambios sustanciales en la versión de .NET Framework existente de la aplicación, puede esperar hasta que tenga un nuevo archivo del proyecto destinado a .NET Core. Pero la actualización de los paquetes NuGet a versiones compatibles con .NET Core con anterioridad hace que el proceso de migración sea aún más fácil una vez que se crea el archivo del proyecto y se reduce el número de diferencias entre las versiones para .NET Framework y .NET Core de la aplicación.

Con el ejemplo Bean Trader, todas las actualizaciones necesarias se pueden realizar fácilmente (con el administrador de paquetes NuGet de Visual Studio) con una excepción: la actualización desde **MahApps.Metro 1.6.5** a **2.0** revela cambios importantes relacionados con las API de administración de temas y de acentos.

Idealmente, la aplicación se actualizaría para usar la versión más reciente del paquete (ya que es más probable que funcione en .NET Core). Pero en algunos casos, puede que no sea factible. En estos casos, no actualice **MahApps.Metro** porque los cambios necesarios son significativos y este tutorial se centra en la migración a .NET Core 3, no a **MahApps.Metro 2.** Además, se trata de una dependencia de .NET Framework de bajo riesgo porque la aplicación Bean Trader solo ejerce una pequeña parte de **MahApps.Metro**. Por supuesto, será necesario realizar pruebas para asegurarse de que todo funciona una vez que haya finalizado la migración. Si se tratase de un escenario real, sería conveniente registrar una incidencia para realizar el seguimiento del trabajo para cambiar a **MahApps.Metro** versión 2.0, ya que si ahora no se realiza la migración, se mantiene cierta deuda técnica.

Una vez que los paquetes NuGet se actualizan a las versiones recientes, el grupo de elementos `<PackageReference>` del archivo del proyecto del ejemplo Bean Trader debe tener este aspecto.

```xml
<ItemGroup>
  <PackageReference Include="Castle.Windsor">
    <Version>4.1.1</Version>
  </PackageReference>
  <PackageReference Include="MahApps.Metro">
    <Version>1.6.5</Version>
  </PackageReference>
  <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers">
    <Version>2.9.2</Version>
  </PackageReference>
  <PackageReference Include="Nito.AsyncEx">
    <Version>5.0.0</Version>
  </PackageReference>
</ItemGroup>
```

### <a name="net-framework-portability-analysis"></a>Análisis de portabilidad de .NET Framework

Una vez que comprenda el estado de las dependencias de NuGet del proyecto, lo siguiente que debe tener en cuenta son las dependencias de API de .NET Framework. La herramienta [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) es útil para entender cuál de las API de .NET que se usan el proyecto están disponibles en otras plataformas de .NET.

La herramienta se ofrece como [complemento de Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), como [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases), o bien se encapsula en una [GUI sencilla](https://github.com/Microsoft/dotnet-apiport-ui), donde se simplifican sus opciones. Puede leer más sobre el uso del Analizador de portabilidad de .NET (API Port) mediante la interfaz gráfica de usuario en la entrada de blog [Portabilidad de aplicaciones de escritorio a .NET Core](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/). Si prefiere usar la línea de comandos, los pasos necesarios son los siguientes:

1. Descargue el [Analizador de portabilidad de .NET](https://github.com/Microsoft/dotnet-apiport/releases) si todavía no lo tiene.
1. Asegúrese de que la aplicación de .NET Framework que se va a migrar se compila correctamente (en cualquier caso, es recomendable hacerlo antes de la migración).
1. Ejecute API Port con una línea de comandos como esta.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    El argumento `-f` especifica la ruta de acceso que contiene los archivos binarios que se van a analizar. El argumento `-r` especifica el formato del archivo de salida deseado. El argumento `-t` especifica en qué plataforma .NET se va a analizar el uso de la API. En este caso, le interesa .NET Core.

Al abrir el informe HTML, en la primera sección se enumeran todos los archivos binarios analizados y qué porcentaje de las API de .NET que usan están disponibles en la plataforma de destino. El porcentaje por sí solo no es significativo. Lo más útil es ver las API específicas que faltan. Para ello, seleccione un nombre de ensamblado o desplácese hacia abajo hasta los informes de ensamblados individuales.

Céntrese en los ensamblados para los que tiene el código fuente. Por ejemplo, en el informe Bean Trader ApiPort, se muestran muchos archivos binarios, pero la mayoría de ellos pertenecen a paquetes NuGet. `Castle.Windsor` muestra que depende de algunas API de System.Web que faltan en .NET Core. Esto no es un problema porque antes se ha comprobado que `Castle.Windsor` es compatible con .NET Core. Es habitual que los paquetes NuGet tengan distintos archivos binarios para usarlos con distintas plataformas de .NET, por lo que si la versión de .NET Framework de `Castle.Windsor` usa las API de System.Web o no es irrelevante, siempre que el paquete también tenga como destino .NET Standard o .NET Core (que sí lo hace).

Con el ejemplo Bean Trader, el único binario que debe tener en cuenta es **BeanTraderClient** y el informe muestra que solo faltan dos API de .NET: `System.ServiceModel.ClientBase<T>.Close` y `System.ServiceModel.ClientBase<T>.Open`.

![Informe de portabilidad de BeanTraderClient](./media/convert-project-from-net-framework/portability-report.png)

No es probable que sean problemas de bloqueo porque las API de cliente WCF se admiten en .NET Core (en su mayoría), por lo que debe haber alternativas disponibles para estas API centrales. De hecho, al examinar el área expuesta de .NET Core de `System.ServiceModel` (con <https://apisof.net>), verá que en su lugar hay alternativas asincrónicas en .NET Core.

Según este informe y el análisis de dependencias de NuGet anterior, parece que no debería haber ningún problema importante al migrar el ejemplo Bean Trader a .NET Core. Está listo para el siguiente paso en el que iniciará realmente la migración.

## <a name="migrating-the-project-file"></a>Migración del archivo del proyecto

Si la aplicación no usa el nuevo [formato de archivo del proyecto de estilo SDK](../../core/tools/csproj.md), necesitará un nuevo archivo del proyecto con .NET Core como destino. Puede reemplazar el archivo csproj existente o, si prefiere mantener el proyecto existente en su estado actual sin modificarlo, puede agregar un nuevo archivo csproj destinado a .NET Core. Puede compilar versiones de la aplicación para .NET Framework y .NET Core con un solo archivo del proyecto de estilo SDK con [compatibilidad con múltiples versiones](../../standard/library-guidance/cross-platform-targeting.md) (si especifica varios destinos `<TargetFrameworks>`).

Para crear el archivo del proyecto, puede crear un proyecto de WPF en Visual Studio o usar el comando `dotnet new wpf` en un directorio temporal para generar el archivo del proyecto y, después, copiarlo o cambiarle el nombre a la ubicación correcta. También hay una herramienta creada por la comunidad, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), que puede automatizar parte de la migración del archivo del proyecto. La herramienta es útil pero todavía se necesita un humano para revisar los resultados con el fin de asegurarse de que todos los detalles de la migración son correctos. Un área concreta que la herramienta no controla de forma óptima es la migración de paquetes NuGet desde archivos *packages.config*. Si la herramienta se ejecuta en un archivo del proyecto en el que todavía se usa un archivo *packages.config* para hacer referencia a los paquetes NuGet, se migrará automáticamente a elementos `<PackageReference>`, pero agregará elementos `<PackageReference>` para *todos* los paquetes en lugar de solo los de nivel superior. Si ya ha migrado a elementos `<PackageReference>` con Visual Studio (como en este ejemplo), la herramienta puede ayudarle con el resto de la conversión. Como Scott Hanselman recomienda en [su entrada de blog sobre la migración de archivos csproj](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx), la migración manual es educativa y dará mejores resultados si solo tiene unos pocos proyectos para migrar. Pero si va a migrar docenas o cientos de archivos de proyecto, una herramienta como [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) puede ser de utilidad.

Para crear un archivo del proyecto para el ejemplo Bean Trader, ejecute `dotnet new wpf` en un directorio temporal, mueva el archivo *.csproj* generado a la carpeta *BeanTraderClient* y cambie el nombre a **BeanTraderClient.Core.csproj**.

Como el nuevo formato de archivo del proyecto incluye automáticamente archivos de C#, archivos *resx* y archivos XAML que encuentra en el directorio, el archivo del proyecto ya está casi completo. Para finalizar la migración, abra los archivos del proyecto antiguos y nuevos en paralelo, y examine el antiguo para ver si es necesario migrar la información que contiene. En el caso del ejemplo Bean Trader, se deben copiar los elementos siguientes en el nuevo proyecto:

- Se deben copiar las propiedades `<RootNamespace>`, `<AssemblyName>` y `<ApplicationIcon>`.

- También debe agregar una propiedad `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` al nuevo archivo del proyecto, ya que el ejemplo Bean Trader incluye atributos de nivel de ensamblado (como `[AssemblyTitle]`) en un archivo AssemblyInfo.cs. De forma predeterminada, los nuevos proyectos de estilo SDK generarán automáticamente estos atributos en función de las propiedades del archivo csproj. Como en este caso no quiere que suceda (los atributos generados automáticamente entrarían en conflicto con los de AssemblyInfo.cs), deshabilite los atributos generados automáticamente con `<GenerateAssemblyInfo>`.

- Aunque los archivos *resx* se incluyen de forma automática como recursos incrustados, no se incluyen otros elementos `<Resource>` como las imágenes. Por tanto, copie los elementos `<Resource>` para insertar archivos de imagen e icono. Puede simplificar las referencias png a una sola línea mediante la compatibilidad del nuevo formato de archivo del proyecto con los patrones globales: `<Resource Include="**\*.png" />`.

- De forma similar, los elementos `<None>` se incluyen automáticamente, pero no se copian en el directorio de salida de forma predeterminada. Como el proyecto Bean Trader incluye un elemento `<None>` que *se* copia en el directorio de salida (mediante comportamientos `PreserveNewest`), tendrá que actualizar el elemento `<None>` rellenado de forma automática para ese archivo, como se muestra a continuación.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- El ejemplo Bean Trader incluye un archivo XAML (Default.Accent.xaml) como `Content` (en lugar de como objeto `Page`) porque los temas y los acentos definidos en este archivo se cargan desde el código XAML del archivo en tiempo de ejecución, en lugar de insertarse en la propia aplicación. Pero el nuevo sistema del proyecto incluye automáticamente este archivo como `<Page>`, ya que es un archivo XAML. Por tanto, debe quitar el archivo XAML como una página (`<Page Remove="**\Default.Accent.xaml" />`) y agregarlo como contenido.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Por último, para agregar las referencias de NuGet, copie `<ItemGroup>` con todos los elementos `<PackageReference>`. Si no ha actualizado previamente los paquetes NuGet a las versiones compatibles con .NET Core, puede hacerlo ahora que las referencias del paquete se encuentran en un proyecto específico de .NET Core.

En este punto, debería ser posible agregar el nuevo proyecto a la solución BeanTrader y abrirlo en Visual Studio. El proyecto debe tener un aspecto correcto en el **Explorador de soluciones** y `dotnet restore BeanTraderClient.Core.csproj` debe restaurar correctamente los paquetes (con dos advertencias previstas relacionadas con la versión MahApps.Metro que se usa destinada a .NET Framework).

Aunque es posible mantener los dos archivos del proyecto en paralelo (e incluso deseable si quiere seguir compilando el proyecto anterior exactamente como era), complica el proceso de migración (los dos proyectos intentarán usar las mismas carpetas bin y obj), y normalmente no es necesario. Si quiere compilar para los destinos .NET Core y .NET Framework, puede reemplazar la propiedad `<TargetFramework>netcoreapp3.0</TargetFramework>` del nuevo archivo del proyecto por `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>`. En el ejemplo Bean Trader, elimine el archivo del proyecto antiguo (BeanTraderClient.csproj), ya que ya no es necesario. Si prefiere conservar ambos archivos del proyecto, asegúrese de que se compilan en diferentes rutas de acceso de salida e intermedias.

## <a name="fix-build-issues"></a>Solución de problemas de compilación

El tercer paso del proceso de portabilidad es la compilación del proyecto. Algunas aplicaciones se compilarán correctamente una vez que el archivo de proyecto se convierta en un proyecto de estilo SDK. Si ese es el caso de la aplicación, enhorabuena. Puede continuar con el paso 4. Otras aplicaciones necesitarán algunas actualizaciones para que se compilen para .NET Core. Si ahora intenta ejecutar `dotnet build` en el proyecto Bean Trader, por ejemplo, (o compilarlo en Visual Studio), habrá muchos errores, pero conseguirá solucionarlos rápidamente.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>Referencias a System.ServiceModel y Microsoft.Windows.Compatibility

Una fuente común de errores es que faltan referencias para API que están disponibles para .NET Core, pero que no se incluyen de forma automática en el metapaquete de la aplicación .NET Core. Para solucionarlo, debe hacer referencia al paquete `Microsoft.Windows.Compatibility`. El paquete de compatibilidad incluye un amplio conjunto de API comunes en las aplicaciones de escritorio de Windows, como el cliente WCF, los servicios de directorio, el registro, la configuración, las API de ACL, etc.

Con el ejemplo Bean Trader, la mayoría de los errores de compilación se deben a que faltan tipos de <xref:System.ServiceModel>. Para solucionarlos, se hace referencia a los paquetes NuGet de WCF necesarios. Pero las API de cliente WCF son algunas de las que se incluyen en el paquete `Microsoft.Windows.Compatibility`, por lo que hacer referencia al paquete de compatibilidad es una solución todavía mejor (ya que también se soluciona cualquier problema relacionado con las API, así como soluciones para los problemas de WCF que el paquete de compatibilidad pone a disposición). El paquete `Microsoft.Windows.Compatibility` es útil en la mayoría de los escenarios de migración de WPF y WinForms a .NET Core 3.0. Después de agregar la referencia de NuGet a `Microsoft.Windows.Compatibility`, solo queda un error de compilación.

### <a name="cleaning-up-unused-files"></a>Limpieza de los archivos sin usar

Un tipo de problema de migración que surge con frecuencia está relacionado con los archivos de C# y XAML que antes no se incluían en la compilación y que ahora toman los nuevos proyectos de estilo de SDK que incluyen *todo* el origen de forma automática.

El siguiente error de compilación que se ve en el ejemplo de Bean Trader hace referencia a una implementación de interfaz incorrecta en *OldUnusedViewModel.cs*. El nombre de archivo es una sugerencia, pero, tras inspeccionarlo, observará que este archivo de código fuente es incorrecto. No causaba problemas anteriormente porque no se incluía en el proyecto de .NET Framework original. Los archivos de origen que estaban presentes en el disco pero que no se incluían en el archivo *csproj* anterior ahora se incluyen de forma automática.

Para los problemas únicos como este, es fácil comparar con el archivo *csproj* anterior para confirmar que el archivo no es necesario y, después, aplicarle `<Compile Remove="" />` o, si el archivo de origen ya no es necesario, eliminarlo. En este caso, se puede eliminar *OldUnusedViewModel.cs* sin problema.

Si tiene muchos archivos de código fuente que se deban excluir de esta forma, puede deshabilitar la inclusión automática de archivos de C# si establece la propiedad `<EnableDefaultCompileItems>` en false en el archivo del proyecto. Después, puede copiar los elementos `<Compile Include>` desde el archivo del proyecto anterior al nuevo para crear solo los orígenes de compilación que quiera incluir. De forma similar, se puede usar `<EnableDefaultPageItems>` para desactivar la inclusión automática de páginas XAML y `<EnableDefaultItems>` puede controlar ambos con una sola propiedad.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Ahora se ofrecerá un breve apunte adicional sobre los compiladores de pases múltiples

Después de quitar el archivo erróneo del ejemplo Bean Trader, puede volver a compilar y obtendrá cuatro errores. ¿No había solo uno antes? ¿Por qué ha aumentado el número de errores? El compilador de C# es un [compilador de varios pasos](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes). Esto significa que recorre dos veces cada archivo de código fuente. En primer lugar, el compilador solo examina los metadatos y las declaraciones de cada archivo de código fuente e identifica los problemas de nivel de declaración. Esos son los errores que se han corregido. Después, vuelve a pasar por el código para compilar el código fuente de C# en lenguaje intermedio; son el segundo conjunto de errores que se ven ahora.

> [!NOTE]
> El compilador de C# realiza [más de dos pasos](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes), pero el resultado final es que los errores del compilador para cambios de código grandes como este tienden a aparecer en dos oleadas.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Correcciones de dependencia de terceros (Castle.Windsor)

Otra clase de problema que surge en algunos escenarios de migración son las diferencias de API entre las versiones para .NET Framework y .NET Core de las dependencias. Incluso si un paquete NuGet tiene como destino .NET Framework y .NET Standard o .NET Core, puede haber distintas bibliotecas para usarlas con diferentes destinos .NET. Esto permite que los paquetes admitan muchas plataformas .NET diferentes, que pueden requerir otras implementaciones. También significa que puede haber pequeñas diferencias de API en las bibliotecas cuando se seleccionan como destino distintas plataformas .NET.

El siguiente conjunto de errores que verá en el ejemplo Bean Trader se relaciona con las API de `Castle.Windsor`. El proyecto Bean Trader de .NET Core usa la misma versión de `Castle.Windsor` que el proyecto destinado a .NET Framework (4.1.1), pero las implementaciones para esas dos plataformas son ligeramente diferentes.

En este caso, verá los siguientes problemas que deben corregirse:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly` no está disponible en .NET Core. Pero hay una API `Classes.FromAssemblyContaining` similar disponible, por lo que se pueden reemplazar los dos usos de `Classes.FromThisAssembly()` con llamadas a `Classes.FromAssemblyContaining(t)`, donde `t` es el tipo que realiza la llamada.
1. Del mismo modo, en *Bootstrapper.cs*, `Castle.Windsor.Installer.FromAssembly`no está disponible en .NET Core. En su lugar, esta llamada se puede reemplazar por `FromAssembly.Containing(typeof(Bootstrapper))`.

### <a name="updating-wcf-client-usage"></a>Actualización del uso del cliente WCF

Después de corregir las diferencias de `Castle.Windsor`, el último error de compilación en el proyecto Bean Trader de .NET Core es que `BeanTraderServiceClient` (que se deriva de `DuplexClientBase`) no tiene un método `Open`. Esto no es sorprendente, ya que se trata de una API identificada por el Analizador de portabilidad de .NET al principio de este proceso de migración. Pero al examinar `BeanTraderServiceClient`, la atención se centra en un problema mayor. Este cliente WCF se ha generado de forma automática mediante la herramienta [Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).

**Los clientes WCF generados por Svcutil están pensados para usar en .NET Framework.**

Las soluciones que usan clientes WCF generados por Svcutil tendrán que volver a generar clientes compatibles con .NET Standard para su uso con .NET Core. Uno de los motivos principales por los que los clientes antiguos no funcionarán es que dependen de la configuración de la aplicación para definir enlaces y puntos de conexión de WCF. Como las API de WCF de .NET Standard pueden funcionar entre plataformas (donde las API de System.Configuration no están disponibles), los clientes WCF para los escenarios de .NET Core y .NET Standard deben definir enlaces y puntos de conexión mediante programación en lugar de hacerlo en la configuración.

De hecho, cualquier uso de cliente WCF que dependa de la sección `<system.serviceModel>` de app.config (se haya creado con Svcutil o de forma manual) tendrá que cambiarse para que funcione en .NET Core.

Hay dos maneras de generar automáticamente clientes WCF compatibles con .NET Standard:

- La herramienta `dotnet-svcutil` de .NET genera clientes WCF de forma similar a como se ha ejecutado Svcutil antes.
- Visual Studio puede generar clientes WCF mediante la opción [WCF Web Service Reference](../../core/additional-tools/wcf-web-service-reference-guide.md) de su característica Servicios conectados.

Los dos enfoques funcionan bien. Por supuesto, como alternativa puede escribir personalmente el código de cliente WCF. En este ejemplo, se ha optado por usar la característica Servicio conectado de Visual Studio. Para ello, haga clic con el botón derecho en el proyecto *BeanTraderClient.Core* en el explorador de soluciones de Visual Studio y seleccione **Agregar** > **Servicio conectado**. Después, seleccione el proveedor WCF Web Service Reference. Se abrirá un cuadro de diálogo en el que puede especificar la dirección del servicio web Bean Trader de back-end (`localhost:8080` si ejecuta el servidor localmente) y el espacio de nombres que deben usar los tipos generados (**BeanTrader.Service**, por ejemplo).

![Cuadro de diálogo del Servicio conectado WCF Web Service Reference](./media/convert-project-from-net-framework/connected-service-dialog.png)

Después de seleccionar el botón **Finalizar**, se agrega un nuevo nodo Servicios conectados al proyecto y un archivo Reference.cs en ese nodo que contiene el nuevo cliente WCF de .NET Standard para acceder al servicio Bean Trader. Si observa los métodos `GetEndpointAddress` o `GetBindingForEndpoint` de ese archivo, verá que los enlaces y puntos de conexión ahora se generan mediante programación (en lugar de mediante la configuración de la aplicación). La característica "Agregar servicios conectados" también puede agregar al archivo del proyecto referencias a algunos paquetes System.ServiceModel innecesarios, ya que todos los paquetes WCF necesarios se incluyen a través de Microsoft.Windows.Compatibility. Compruebe el archivo csproj para ver si se ha agregado algún elemento `<PackageReference>` de System.ServiceModel adicional y, si es así, quítelo.

Ahora el proyecto tiene nuevas clases de cliente WCF (en *Reference.cs*), pero también las antiguas (en BeanTrader.cs). En este momento, dispone de dos opciones:

- Si quiere poder compilar el proyecto de .NET Framework original (junto con el nuevo destinado a .NET Core), puede usar un elemento `<Compile Remove="BeanTrader.cs" />` en el archivo csproj del proyecto de .NET Core para que las versiones de .NET Framework y .NET Core de la aplicación usen distintos clientes WCF. La ventaja de esto es que el proyecto de .NET Framework existente no cambia, pero la desventaja es que el código que usa los clientes WCF generados sea ligeramente diferente en .NET Core que en el proyecto de .NET Framework, por lo que probablemente tendrá que usar directivas `#if` para compilar de forma condicional algún uso de cliente WCF (por ejemplo, la creación de clientes) para que funcione de una manera cuando se compila para NET Core y de otra para .NET Framework.

- Por otro lado, si se acepta alguna renovación de código en el proyecto para .NET Framework existente, puede quitar *BeanTrader.cs* definitivamente. Como el nuevo cliente WCF se compila para .NET Standard, funcionará en los escenarios de .NET Core y .NET Framework. Si va a compilar para .NET Framework además de .NET Core (ya sea mediante la compatibilidad con múltiples versiones o con dos archivos csproj), puede usar este nuevo archivo *Reference.cs* para los dos destinos. Este enfoque tiene la ventaja de que no es necesario bifurcar el código para admitir dos clientes WCF diferentes: se usará el mismo en todas partes. El inconveniente es que implica cambiar el proyecto de .NET Framework (supuestamente estable).

En el caso del ejemplo Bean Trader, puede realizar pequeños cambios en el proyecto original si eso facilita la migración, por lo que debe seguir estos pasos para conciliar el uso del cliente WCF:

01. Agregue el nuevo archivo Reference.cs al proyecto *BeanTraderClient.csproj* de .NET Framework mediante el menú contextual "Agregar elemento existente" desde el Explorador de soluciones. Asegúrese de agregar "como vínculo" para que ambos proyectos usen el mismo archivo (en lugar de copiar el archivo de C#). Si va a compilar para .NET Core y .NET Framework con un solo archivo csproj (con compatibilidad con múltiples versiones), este paso no es necesario.

01. Elimine *BeanTrader.cs*.

01. El nuevo cliente WCF es similar al anterior, pero varios espacios de nombres del código generado son distintos. Por este motivo, es necesario actualizar el proyecto para que los tipos de cliente WCF se usen desde BeanTrader.Service (o el espacio de nombres que haya elegido) en lugar de BeanTrader.Model o sin un espacio de nombres. La compilación de *BeanTraderClient.Core.csproj* ayudará a identificar dónde se deben realizar estos cambios. Se necesitarán correcciones en C# y en los archivos de código fuente XAML.

01. Por último, descubrirá que hay un error en *BeanTraderServiceClientFactory.cs* porque los constructores disponibles para el tipo `BeanTraderServiceClient` han cambiado. Solía ser posible proporcionar un argumento `InstanceContext` (creado con un elemento `CallbackHandler` del contenedor de IoC `Castle.Windsor`). Los nuevos constructores crean objetos `CallbackHandler`. Pero hay constructores en el tipo base de `BeanTraderServiceClient` que coinciden con lo que quiere. Como todo el código de cliente WCF generado automáticamente existe en clases parciales, puede extenderlo con facilidad. Para ello, cree un archivo llamado *BeanTraderServiceClient.cs* y, después, una clase parcial con ese mismo nombre (mediante el espacio de nombres BeanTrader.Service). Luego, agregue un constructor al tipo parcial como se muestra aquí.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Con esos cambios, en el ejemplo Bean Trader ahora se usará un nuevo cliente WCF compatible con .NET Standard y puede realizar la corrección final del cambio de la llamada a `Open` en *TradingService.cs* para usar `await OpenAsync` en su lugar.

Después de solucionar los problemas de WCF, ahora la versión para .NET Core del ejemplo Bean Trader se compila correctamente.

## <a name="runtime-testing"></a>Pruebas en tiempo de ejecución

Es fácil olvidarse de que el trabajo de migración no termina después de compilar ahora sin problemas en .NET Core. También es importante dejar tiempo para probar la aplicación que se ha migrado. Una vez que todo se haya compilado correctamente, asegúrese de que la aplicación se ejecuta y funciona según lo previsto, especialmente si usa algún paquete destinado a .NET Framework.

Ahora se intentará iniciar la aplicación Bean Trade que se ha migrado para ver lo que sucede. La aplicación no avanza demasiado antes de que se produzca un error con la siguiente excepción.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Esto tiene sentido, por supuesto. Recuerde que WCF ya no usa la configuración de la aplicación, por lo que es necesario quitar la sección system.serviceModel antigua del archivo app.config. El cliente WCF actualizado incluye toda esta misma información en su código, por lo que la sección de configuración ya no es necesaria. Si quiere que el punto de conexión de WCF se pueda configurar en app.config, puede agregarlo como una configuración de aplicación y actualizar el código de cliente WCF para recuperar el punto de conexión de servicio de WCF de la configuración.

Después de quitar la sección system.serviceModel de *app.config*, la aplicación se inicia pero se produce un error con otra excepción cuando un usuario inicia sesión.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

La versión de la API no admitida es `Func<T>.BeginInvoke`. Como se explica en [dotnet/corefx#5940](https://github.com/dotnet/corefx/issues/5940), .NET Core no admite los métodos `BeginInvoke` y `EndInvoke` en los tipos de delegado debido a las dependencias de comunicación remota subyacentes. Este problema y su corrección se explican con más detalle en la entrada de blog [Migración de llamadas a Delegate.BeginInvoke para .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) pero, para resumir, las llamadas a `BeginInvoke` y `EndInvoke` se deben reemplazar por `Task.Run` (o alternativas asincrónicas, si es posible). Si en este caso se aplica la solución general, la llamada a `BeginInvoke` se puede reemplazar por una llamada a `Invoke` iniciada por `Task.Run`.

```csharp
Task.Run(() =>
{
    return userInfoRetriever.Invoke();
}).ContinueWith(result =>
{
    // BeginInvoke's callback is replaced with ContinueWith
    var task = result.ConfigureAwait(false);
    CurrentTrader = task.GetAwaiter().GetResult();
}, TaskScheduler.Default);
```

Después de quitar el uso de `BeginInvoke`, la aplicación Bean Trader se ejecuta correctamente en .NET Core.

![Bean Trader en ejecución en .NET Core](./media/convert-project-from-net-framework/running-on-core.png)

Todas las aplicaciones son diferentes, de modo que los pasos específicos necesarios para migrar aplicaciones propias a .NET Core variarán. Pero es de esperar que el ejemplo Bean Trader sirva para mostrar el flujo de trabajo general y los tipos de problemas previstos. Y, a pesar de la longitud de este artículo, los cambios reales necesarios en el ejemplo Bean Trader para hacer que funcione en .NET Core han sido bastante limitados. Muchas aplicaciones se migran a .NET Core de esta misma manera; con un número limitado de cambios en el código o incluso sin ellos.
