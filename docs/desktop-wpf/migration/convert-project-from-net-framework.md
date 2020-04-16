---
title: Migración de aplicaciones WPF a .NET Core 3.0
description: Aprenda a migrar una aplicación de Windows Presentation Foundation (WPF) a .NET Core 3.0.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: f52005e7c8a6312b8c4e09a950f1f635af1894e4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "81432597"
---
# <a name="migrating-wpf-apps-to-net-core"></a>Migración de aplicaciones WPF a .NET Core

En este artículo se describen los pasos necesarios para migrar una aplicación de Windows Presentation Foundation (WPF) de .NET Framework a .NET Core 3.0. Si no tiene una aplicación WPF a mano a puerto, pero le gustaría probar el proceso, puede usar la aplicación de ejemplo **Bean Trader** disponible en [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader). La aplicación original (dirigida a .NET Framework 4.7.2) está disponible en la carpeta NetFx-BeanTraderClient. Primero explicaremos los pasos necesarios para portar aplicaciones en general, y luego le explicaremos los cambios específicos que se aplican a la muestra **de Bean Trader.**

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Para migrar a .NET Core, primero debe:

01. Comprender y actualizar las dependencias de NuGet:

    01. Actualice las dependencias de `<PackageReference>` NuGet para usar el formato.
    01. Revise las dependencias de NuGet de nivel superior para la compatibilidad con .NET Core o .NET Standard.
    01. Actualice los paquetes NuGet a versiones más recientes.
    01. Use el Analizador de portabilidad de [.NET](../../standard/analyzers/portability-analyzer.md) para comprender las dependencias de .NET.

01. Migre el archivo de proyecto al nuevo formato de estilo SDK:

    01. Elija si desea tener como destino .NET Core y .NET Framework, o solo .NET Core.
    01. Copie las propiedades y los elementos relevantes del archivo de proyecto en el nuevo archivo de proyecto.

01. Solucionar problemas de compilación:

    01. Agregue una referencia al paquete [Microsoft.Windows.Compatibility.](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/)
    01. Busque y corrija las diferencias a nivel de API.
    01. Quite las secciones *app.config* que no sean `appSettings` o `connectionStrings`.
    01. Regenere el código generado, si es necesario.

01. Pruebas en tiempo de ejecución:

    01. Confirme que la aplicación porteada funciona según lo esperado.
    01. Tenga cuidado <xref:System.NotSupportedException> con las excepciones.

## <a name="about-the-sample"></a>Sobre el ejemplo

Este artículo hace referencia a la aplicación de [ejemplo Bean Trader](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) porque usa una variedad de dependencias similares a las que pueden tener las aplicaciones WPF del mundo real. La aplicación no es grande, pero está destinada a ser un paso adelante de 'Hello World' en términos de complejidad. La aplicación muestra algunos problemas que los usuarios pueden encontrar al migrar aplicaciones reales. La aplicación se comunica con un servicio WCF, por lo que para que se ejecute correctamente, también tendrá que ejecutar el proyecto BeanTraderServer (disponible en el mismo repositorio GitHub) y asegurarse de que la configuración de BeanTraderClient apunta al punto de conexión correcto. (De forma predeterminada, el ejemplo supone que el *http://localhost:8090*servidor se está ejecutando en el mismo equipo en , que será true si inicia BeanTraderServer localmente.)

Tenga en cuenta que esta aplicación de ejemplo está diseñada para demostrar soluciones y desafíos de portabilidad de .NET Core. No está diseñado para demostrar las prácticas recomendadas de WPFWPF. De hecho, deliberadamente incluye algunos anti-patrones para asegurarse de que se encuentra con al menos un par de desafíos interesantes durante la portabilidad.

## <a name="getting-ready"></a>Preparación

El principal desafío de migrar una aplicación de .NET Framework a .NET Core es que sus dependencias pueden funcionar de forma diferente o no funcionar en absoluto. La migración es mucho más fácil de lo que solía ser; muchos paquetes NuGet ahora se dirigen a .NET Standard. A partir de .NET Core 2.0, las áreas de superficie de .NET Framework y .NET Core se han vuelto similares. Aún así, algunas diferencias (tanto en la compatibilidad con paquetes NuGet como en las API de .NET disponibles) permanecen. El primer paso para migrar es revisar las dependencias de la aplicación y asegurarse de que las referencias están en un formato que se migra fácilmente a .NET Core.

### <a name="upgrade-to-packagereference-nuget-references"></a>Actualización `<PackageReference>` a referencias NuGet

Los proyectos de .NET Framework más antiguos suelen enumerar sus dependencias NuGet en un archivo *packages.config.* El nuevo formato de archivo de proyecto [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) de estilo SDK hace referencia a paquetes NuGet como elementos en el propio archivo csproj en lugar de en un archivo de configuración independiente.

Al migrar, hay dos ventajas `<PackageReference>`en el uso de referencias de estilo:

- Este es el estilo de referencia NuGet necesario para el nuevo archivo de proyecto de .NET Core. Si ya está `<PackageReference>`utilizando , esos elementos del archivo de proyecto se pueden copiar y pegar directamente en el nuevo proyecto.
- A diferencia de un `<PackageReference>` archivo packages.config, los elementos solo hacen referencia a las dependencias de nivel superior de las que depende el proyecto directamente. Todos los demás paquetes NuGet transitivos se determinarán en el momento de la restauración y se registrarán en el archivo de obj.assets.json generado automáticamente. Esto hace que sea mucho más fácil determinar qué dependencias tiene el proyecto, lo que resulta útil a la hora de determinar si las dependencias necesarias funcionarán en .NET Core o no.

El primer paso para migrar una aplicación de .NET Framework `<PackageReference>` a .NET Core es actualizarla para usar referencias nuGet. Visual Studio hace esto simple. Simplemente haga clic con el botón secundario en el archivo *packages.config* del proyecto en el **Explorador**de soluciones de Visual Studio y, a continuación, seleccione **Migrar packages.config a PackageReference**.

![Actualización a PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Aparece un cuadro de diálogo que muestra las dependencias NuGet calculadas de nivel superior y que pregunta qué otros paquetes NuGet se deben promocionar a nivel superior. Ninguno de estos otros paquetes necesita ser de nivel superior para la muestra de Bean Trader, por lo que puede desmarcar todas esas casillas. A continuación, haga clic en **Aceptar** `<PackageReference>` y se quita el archivo *packages.config* y los elementos se agregan al archivo de proyecto.

`<PackageReference>`Las referencias de estilo no almacenan paquetes NuGet localmente en una carpeta de paquetes. En su lugar, se almacenan globalmente como una optimización. Una vez completada la migración, edite el `<Analyzer>` archivo csproj y quite los elementos que hacen referencia a los analizadores que anteriormente procedían del *archivo .. Directorio de paquetes.* No te preocupes; puesto que todavía tiene las referencias de paquete NuGet, los analizadores se incluirán en el proyecto. Sólo tiene que limpiar los elementos `<Analyzer>` antiguos packages.config-style.

### <a name="review-nuget-packages"></a>Revisar paquetes NuGet

Ahora que puede ver los paquetes NuGet de nivel superior de los que depende el proyecto, puede revisar si esos paquetes están disponibles en .NET Core. Puede determinar si un paquete admite .NET Core examinando sus dependencias en [nuget.org](https://www.nuget.org/). El sitio [de fuget.org](https://www.fuget.org/) creado por la comunidad muestra esta información de forma prominente en la parte superior de la página de información del paquete.

Al tener como destino .NET Core 3.0, los paquetes destinados a .NET Core o .NET Standard deben funcionar (ya que .NET Core implementa el área de superficie de .NET Standard). En algunos casos, la versión específica de un paquete que se usa no tendrá como destino .NET Core o .NET Standard, pero las versiones más recientes. En este caso, debe considerar la posibilidad de actualizar a la versión más reciente del paquete.

También puede usar paquetes destinados a .NET Framework, pero eso introduce algún riesgo. Las dependencias de .NET Core a .NET Framework se permiten porque las áreas de superficie de .NET Core y .NET Framework son lo suficientemente similares como para que dichas dependencias *funcionen con frecuencia.* Sin embargo, si el paquete intenta usar una API de .NET que no está presente en .NET Core, encontrará una excepción en tiempo de ejecución. Por este motivo, solo debe hacer referencia a paquetes de .NET Framework cuando no hay otras opciones disponibles y comprender que al hacerlo se impone una carga de prueba.

Si hay paquetes a los que se hace referencia que no tienen como destino .NET Core o .NET Standard, tendrá que pensar en otras alternativas:

- ¿Hay otros paquetes similares que se pueden utilizar en su lugar? A veces, los autores de NuGet publican por separado '. Las versiones principales de sus bibliotecas se dirigen específicamente a .NET Core. Los paquetes de Enterprise Library son un ejemplo de la publicación de la comunidad ". NetCore". En otros casos, los DEPARTAMENTOS de dominio más recientes para un servicio determinado (a veces con nombres de paquetes diferentes) están disponibles para .NET Standard. Si no hay alternativas disponibles, puede continuar con los paquetes de objeto de .NET Framework, teniendo en cuenta que deberá probarlos a fondo una vez que se ejecute n.o.NET Core.

El ejemplo Bean Trader tiene las siguientes dependencias NuGet de nivel superior:

- [**Castle.Windsor, versión 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Este paquete tiene como destino .NET Standard 1.6, por lo que funciona en .NET Core.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, versión 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Se trata de un metapaquete, por lo que no es inmediatamente obvio qué plataformas admite, pero la [documentación](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) indica que su versión más reciente (2.9.2) funcionará tanto para .NET Framework como para .NET Core.

- [**Nito.AsyncEx, versión 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Este paquete no tiene como destino .NET Core, pero la versión 5.0 más reciente sí. Esto es común al migrar porque muchos paquetes NuGet han agregado compatibilidad con .NET Standard recientemente, pero las versiones anteriores del proyecto solo tendrán como destino .NET Framework. Si la diferencia de versión es solo una diferencia de versión menor, a menudo es fácil actualizar a la versión más reciente. Dado que se trata de un cambio de versión importante, debe tener cuidado con la actualización, ya que podría haber cambios importantes en el paquete. Sin embargo, hay un camino hacia adelante, que es bueno.

- [**MahApps.Metro, versión 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Este paquete tampoco tiene como destino .NET Core, pero tiene una versión preliminar más reciente (2.0-alpha) que lo hace. Una vez más, usted tiene que mirar hacia fuera para los cambios de última hora, pero el paquete más nuevo es alentador.

Las dependencias NuGet del ejemplo Bean Trader tienen como destino .NET Standard/.NET Core o tienen versiones más recientes, por lo que es poco probable que haya problemas de bloqueo aquí.

### <a name="upgrade-nuget-packages"></a>Actualizar paquetes NuGet

Si es posible, sería bueno actualizar las versiones de los paquetes que solo se dirigen a .NET Core o .NET Standard con versiones más recientes en este momento (con el proyecto todavía destinado a .NET Framework) para detectar y solucionar los cambios importantes antes de tiempo.

Si prefiere no realizar ningún cambio importante en la versión existente de .NET Framework de la aplicación, esto puede esperar hasta que tenga un nuevo archivo de proyecto destinado a .NET Core. Sin embargo, la actualización de los paquetes NuGet a versiones compatibles con .NET Core hace que el proceso de migración sea aún más fácil una vez que se crea el nuevo archivo de proyecto y se reduce el número de diferencias entre las versiones de .NET Framework y .NET Core de la aplicación.

Con el ejemplo Bean Trader, todas las actualizaciones necesarias se pueden realizar fácilmente (mediante el administrador de paquetes NuGet de Visual Studio) con una excepción: la actualización de **MahApps.Metro 1.6.5** a **2.0** revela cambios importantes relacionados con las API de administración de temas y acentos.

Idealmente, la aplicación se actualizaría para usar la versión más reciente del paquete (ya que es más probable que funcione en .NET Core). En algunos casos, sin embargo, eso puede no ser factible. En estos casos, no actualice **MahApps.Metro** porque los cambios necesarios no son triviales y este tutorial se centra en migrar a .NET Core 3, no a **MahApps.Metro 2.** Además, se trata de una dependencia de bajo riesgo de .NET Framework porque la aplicación Bean Trader solo ejerce una pequeña parte de **MahApps.Metro.** Por supuesto, requerirá pruebas para asegurarse de que todo funciona una vez completada la migración. Si esto fuera un escenario del mundo real, sería bueno presentar un problema para realizar un seguimiento del trabajo para pasar a **MahApps.Metro** versión 2.0 ya que no hacer la migración ahora deja alguna deuda técnica.

Una vez que los paquetes NuGet se actualizan a versiones recientes, el `<PackageReference>` grupo de elementos en el archivo de proyecto del ejemplo de Bean Trader debe tener este aspecto.

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

### <a name="net-framework-portability-analysis"></a>Análisis de portabilidad de .NET Framework

Una vez que comprenda el estado de las dependencias NuGet del proyecto, lo siguiente que debe tener en cuenta son las dependencias de la API de .NET Framework. La herramienta Analizador de portabilidad de [.NET](../../standard/analyzers/portability-analyzer.md) es útil para comprender cuáles de las API de .NET usa el proyecto están disponibles en otras plataformas .NET.

La herramienta viene como un plugin de [Visual Studio,](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)una [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases)o envuelta en una [sencilla GUI,](https://github.com/Microsoft/dotnet-apiport-ui)que simplifica sus opciones. Puede obtener más información sobre el uso del Analizador de portabilidad de .NET (puerto API) mediante la GUI de la entrada de blog [Porting desktop apps to .NET Core.](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) Si prefiere utilizar la línea de comandos, los pasos necesarios son:

1. Descargue el Analizador de portabilidad de [.NET](https://github.com/Microsoft/dotnet-apiport/releases) si aún no lo tiene.
1. Asegúrese de que la aplicación de .NET Framework que se va a migrar se compila correctamente (esta es una buena idea antes de la migración independientemente).
1. Ejecute API Port con una línea de comandos como esta.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    El `-f` argumento especifica la ruta de acceso que contiene los archivos binarios que se va a analizar. El `-r` argumento especifica qué formato de archivo de salida desea. El `-t` argumento especifica con qué plataforma .NET analizar el uso de la API. En este caso, desea .NET Core.

Al abrir el informe HTML, la primera sección enumerará todos los archivos binarios analizados y qué porcentaje de las API de .NET que usan están disponibles en la plataforma de destino. El porcentaje no es significativo por sí mismo. Lo que es más útil es ver las API específicas que faltan. Para ello, seleccione un nombre de ensamblado o desplácese hacia abajo hasta los informes para ensamblajes individuales.

Céntrese en los ensamblados para los que es propietario del código fuente. En el informe ApiPort de Bean Trader, por ejemplo, hay muchos binarios enumerados, pero la mayoría de ellos pertenecen a paquetes NuGet. `Castle.Windsor`muestra que depende de algunas API de System.Web que faltan en .NET Core. Esto no es un problema porque `Castle.Windsor` se verificó anteriormente que admite .NET Core. Es común que los paquetes NuGet tengan diferentes archivos binarios para su uso `Castle.Windsor` con diferentes plataformas .NET, por lo que si la versión de .NET Framework de usa las API de System.Web o no es irrelevante siempre que el paquete también tenga como destino .NET Standard o .NET Core (lo que hace).

Con el bean Trader ejemplo, el único binario que debe tener en cuenta es **BeanTraderClient** y el informe muestra que solo faltan dos API de .NET: `System.ServiceModel.ClientBase<T>.Close` y `System.ServiceModel.ClientBase<T>.Open`.

![Informe de portabilidad de BeanTraderClient](./media/convert-project-from-net-framework/portability-report.png)

Es poco probable que se bloqueen los problemas porque las API de cliente WCF (principalmente) se admiten en .NET Core, por lo que debe haber alternativas disponibles para estas API centrales. De hecho, `System.ServiceModel`al examinar el área de <https://apisof.net>superficie de .NET Core de 's (using ), verá que hay alternativas asincrónicas en .NET Core en su lugar.

Según este informe y el análisis de dependencia nuGet anterior, parece que no debería haber problemas importantes al migrar el ejemplo de Bean Trader a .NET Core. Está listo para el siguiente paso en el que realmente iniciará la migración.

## <a name="migrating-the-project-file"></a>Migración del archivo del proyecto

Si la aplicación no usa el nuevo formato de [archivo de proyecto de estilo SDK,](../../core/tools/csproj.md)necesitará un nuevo archivo de proyecto para tener como destino .NET Core. Puede reemplazar el archivo csproj existente o, si prefiere mantener el proyecto existente intacto en su estado actual, puede agregar un nuevo archivo csproj destinado a .NET Core. Puede crear versiones de la aplicación para .NET Framework y .NET Core con un único `<TargetFrameworks>` archivo de proyecto de estilo SDK con varias [destinos](../../standard/library-guidance/cross-platform-targeting.md) (especificando varios destinos).

Para crear el nuevo archivo de proyecto, puede crear un `dotnet new wpf` nuevo proyecto WPF en Visual Studio o usar el comando en un directorio temporal para generar el archivo de proyecto y, a continuación, copiarlo o cambiarle el nombre a la ubicación correcta. También hay una herramienta creada por la comunidad, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), que puede automatizar parte de la migración de archivos de proyecto. La herramienta es útil, pero todavía necesita un humano para revisar los resultados para asegurarse de que todos los detalles de la migración son correctos. Un área concreta que la herramienta no controla de manera óptima es la migración de paquetes NuGet desde archivos *packages.config.* Si la herramienta se ejecuta en un archivo de proyecto que todavía utiliza un archivo *packages.config* para hacer referencia a paquetes NuGet, se migrará a `<PackageReference>` elementos automáticamente, pero agregará `<PackageReference>` elementos para todos *los* paquetes en lugar de solo los de nivel superior. Si ya ha`<PackageReference>` migrado a elementos con Visual Studio (como ha hecho en este ejemplo), la herramienta puede ayudar con el resto de la conversión. Al igual que Scott Hanselman recomienda en su entrada de blog sobre la migración de [archivos csproj,](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx)la portabilidad a mano es educativa y dará mejores resultados si solo tienes unos pocos proyectos por acarrear. Pero si usted está porteando docenas o cientos de archivos de proyecto, entonces una herramienta como [CsprojToVs2017] puede ser de ayuda.

Para crear un nuevo archivo de proyecto `dotnet new wpf` para el ejemplo Bean Trader, ejecute en un directorio temporal y mueva el archivo *.csproj* generado a la carpeta *BeanTraderClient* y cámbiele el nombre a **BeanTraderClient.Core.csproj**.

Debido a que el nuevo formato de archivo de proyecto incluye automáticamente archivos de C, archivos *resx* y archivos XAML que encuentra en o debajo de su directorio, ¡el archivo de proyecto ya está casi completo! Para finalizar la migración, abra los archivos de proyecto antiguos y nuevos en paralelo y examine el antiguo para ver si es necesario migrar cualquier información que contenga. En el caso de ejemplo de Bean Trader, se deben copiar los siguientes elementos en el nuevo proyecto:

- Las `<RootNamespace>` `<AssemblyName>`propiedades `<ApplicationIcon>` , , y todas deben copiarse.

- También debe agregar `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` una propiedad al nuevo archivo de proyecto, ya que `[AssemblyTitle]`el ejemplo Bean Trader incluye atributos de nivel de ensamblado (como ) en un archivo AssemblyInfo.cs. De forma predeterminada, los nuevos proyectos de estilo SDK generarán automáticamente estos atributos en función de las propiedades del archivo csproj. Dado que no desea que eso suceda en este caso (los atributos generados automáticamente entrarían `<GenerateAssemblyInfo>`en conflicto con los de AssemblyInfo.cs), deshabilite los atributos generados automáticamente con .

- Aunque los archivos *resx* se incluyen `<Resource>` automáticamente como recursos incrustados, otros elementos como imágenes no lo son. Por lo `<Resource>` tanto, copie los elementos para incrustar archivos de imagen e icono. Puede simplificar las referencias png a una sola línea utilizando la compatibilidad del `<Resource Include="**\*.png" />`nuevo formato de archivo de proyecto para patrones de globbing: .

- Del `<None>` mismo modo, los elementos se incluyen automáticamente, pero no se copian en el directorio de salida, de forma predeterminada. Dado que el proyecto `<None>` Bean Trader incluye un elemento `PreserveNewest` que *se* copia en el directorio de salida (mediante comportamientos), debe actualizar el elemento rellenado `<None>` automáticamente para ese archivo, como este.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- El ejemplo de Bean Trader incluye un archivo `Content` XAML (Default.Accent.xaml) como (en lugar de como un `Page`) porque los temas y acentos definidos en este archivo se cargan desde el XAML del archivo en tiempo de ejecución, en lugar de estar incrustados en la propia aplicación. Sin embargo, el nuevo `<Page>`sistema de proyectos incluye automáticamente este archivo como un archivo , ya que es un archivo XAML. Por lo tanto, debe quitar el archivo`<Page Remove="**\Default.Accent.xaml" />`XAML como una página ( ) y agregarlo como contenido.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Por último, agregue referencias NuGet copiando el `<ItemGroup>` con todos los `<PackageReference>` elementos. Si no había actualizado previamente los paquetes NuGet a versiones compatibles con .NET Core, podría hacerlo ahora que las referencias de paquete están en un proyecto específico de .NET Core.

En este punto, debería ser posible agregar el nuevo proyecto a la solución BeanTrader y abrirlo en Visual Studio. El proyecto debe tener un `dotnet restore BeanTraderClient.Core.csproj` aspecto correcto en el Explorador de **soluciones**y debe restaurar correctamente los paquetes (con dos advertencias esperadas relacionadas con la versión de MahApps.Metro que usa .NET Framework).

Aunque es posible mantener ambos archivos de proyecto en paralelo (e incluso puede ser deseable si desea seguir construyendo el proyecto antiguo exactamente como era), complica el proceso de migración (los dos proyectos intentarán usar las mismas carpetas bin y obj) y normalmente no es necesario. Si desea compilar para los destinos de .NET Core y `<TargetFramework>netcoreapp3.0</TargetFramework>` .NET Framework, `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` puede reemplazar la propiedad en el nuevo archivo de proyecto con en su lugar. Para el ejemplo de Bean Trader, elimine el archivo de proyecto antiguo (BeanTraderClient.csproj) ya que ya no es necesario. Si prefiere mantener ambos archivos de proyecto, asegúrese de que se compilan en diferentes rutas de salida e intermedio.

## <a name="fix-build-issues"></a>Solucionar problemas de compilación

El tercer paso del proceso de portabilidad es conseguir que el proyecto se compile. Algunas aplicaciones ya se compilarán correctamente una vez que el archivo de proyecto se convierta en un proyecto de estilo SDK. Si ese es el caso de su aplicación, ¡felicidades! Puede continuar con el paso 4. Otras aplicaciones necesitarán algunas actualizaciones para que se estén creando para .NET Core. Si intenta ejecutar `dotnet build` en el proyecto de ejemplo Bean Trader ahora, por ejemplo, (o compilarlo en Visual Studio), habrá muchos errores, pero los corregirá rápidamente.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>Referencias system.ServiceModel y Microsoft.Windows.Compatibility

A un origen común de errores le faltan referencias para las API que están disponibles para .NET Core pero que no se incluyen automáticamente en el metapaquete de la aplicación .NET Core. Para solucionar este tema, `Microsoft.Windows.Compatibility` debe hacer referencia al paquete. El paquete de compatibilidad incluye un amplio conjunto de API que son comunes en las aplicaciones de escritorio de Windows, como el cliente WCF, los servicios de directorio, el registro, la configuración, las API de ACL y mucho más.

Con el ejemplo de Bean Trader, la mayoría <xref:System.ServiceModel> de los errores de compilación se deben a tipos que faltan. Estos podrían solucionarse haciendo referencia a los paquetes NuGet de WCF necesarios. Sin embargo, las API `Microsoft.Windows.Compatibility` de cliente WCF se encuentran entre las presentes en el paquete, por lo que hacer referencia al paquete de compatibilidad es una solución aún mejor (ya que también aborda los problemas relacionados con las API, así como las soluciones a los problemas de WCF que el paquete de compatibilidad pone a disposición). El `Microsoft.Windows.Compatibility` paquete ayuda en la mayoría de los escenarios de portabilidad de WPF y WinForms de .NET Core 3.0. Después de agregar `Microsoft.Windows.Compatibility`la referencia NuGet a , ¡solo queda un error de compilación!

### <a name="cleaning-up-unused-files"></a>Limpieza de archivos no utilizados

Un tipo de problema de migración que surge a menudo se relaciona con los archivos XAML y de C que no se incluyeron anteriormente en la compilación que se recogen en los nuevos proyectos de estilo SDK que incluyen *todo* el origen automáticamente.

El siguiente error de compilación que ve en el ejemplo Bean Trader se refiere a una implementación de interfaz incorrecta en *OldUnusedViewModel.cs*. El nombre del archivo es una sugerencia, pero en la inspección, encontrará que este archivo de origen es incorrecto. No provocaba problemas anteriormente porque no se incluía en el proyecto original de .NET Framework. Los archivos de origen que estaban presentes en el disco pero no se incluyeban en el *antiguo csproj* ahora se incluyen automáticamente.

Para problemas únicos como este, es fácil comparar con el *csproj* anterior para confirmar que `<Compile Remove="" />` el archivo no es necesario y, a continuación, o bien o, si el archivo de origen ya no es necesario en cualquier lugar, elimínelo. En este caso, es seguro simplemente eliminar *OldUnusedViewModel.cs*.

Si tiene muchos archivos de origen que tendrían que excluirse de esta manera, `<EnableDefaultCompileItems>` puede deshabilitar la inclusión automática de archivos de C- estableciendo la propiedad en false en el archivo de proyecto. A continuación, `<Compile Include>` puede copiar elementos del archivo de proyecto antiguo en el nuevo para crear solo los orígenes que pretendía incluir. De `<EnableDefaultPageItems>` forma similar, se puede usar para `<EnableDefaultItems>` desactivar la inclusión automática de páginas XAML y puede controlar ambas con una sola propiedad.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Un breve aparte en los compiladores de varias pasadas

Después de eliminar el archivo infractor de la muestra de Bean Trader, puede volver a crear y obtendrá cuatro errores. ¿No tenías uno antes? ¿Por qué saqué el número de errores? El compilador de C. es un [compilador de varias pasadas.](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes) Esto significa que pasa a través de cada archivo de origen dos veces. En primer lugar, el compilador solo examina los metadatos y las declaraciones de cada archivo de origen e identifica los problemas de nivel de declaración. Esos son los errores que has corregido. A continuación, pasa por el código de nuevo para compilar el origen de C- en IL; esos son el segundo conjunto de errores que estás viendo ahora.

> [!NOTE]
> El compilador de C- hace [más que solo dos pasadas,](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)pero el resultado final es que los errores del compilador para cambios de código grandes como este tienden a venir en dos oleadas.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Correcciones de dependencia sin terceros (Castle.Windsor)

Otra clase de problema que surge en algunos escenarios de migración es las diferencias de API entre las versiones de dependencias de .NET Framework y .NET Core. Incluso si un paquete NuGet tiene como destino .NET Framework y .NET Standard o .NET Core, puede haber bibliotecas diferentes para su uso con diferentes destinos de .NET. Esto permite que los paquetes admitan muchas plataformas .NET diferentes, que pueden requerir implementaciones diferentes. También significa que puede haber pequeñas diferencias de API en las bibliotecas al dirigirse a diferentes plataformas .NET.

El siguiente conjunto de errores que verá en el `Castle.Windsor` ejemplo de Bean Trader está relacionado con las API. El proyecto de .NET Core Bean `Castle.Windsor` Trader usa la misma versión que el proyecto de .NET Framework (4.1.1), pero las implementaciones para esas dos plataformas son ligeramente diferentes.

En este caso, verá los siguientes problemas que deben corregirse:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`no está disponible en .NET Core. Hay, sin embargo, `Classes.FromAssemblyContaining` la API similar disponible, `Classes.FromThisAssembly()` por `Classes.FromAssemblyContaining(t)`lo `t` que podemos reemplazar ambos usos de con llamadas a , donde está el tipo que realiza la llamada.
1. Del mismo modo, en *Bootstrapper.cs*, `Castle.Windsor.Installer.FromAssembly`. Esto no está disponible en .NET Core. En su lugar, esa `FromAssembly.Containing(typeof(Bootstrapper))`llamada se puede reemplazar con .

### <a name="updating-wcf-client-usage"></a>Actualización del uso del cliente WCF

Una vez `Castle.Windsor` fijadas las diferencias, el último error de compilación `BeanTraderServiceClient` restante en el `DuplexClientBase`proyecto de .NET Core Bean Trader es que (que deriva de ) no tiene un `Open` método. Esto no es sorprendente, ya que se trata de una API que el Analizador de portabilidad de .NET destacó al principio de este proceso de migración. Sin `BeanTraderServiceClient` embargo, mirar nos llama la atención sobre un tema más amplio. Este cliente WCF se generó automáticamente por la herramienta [Svcutil.exe.](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

**Los clientes WCF generados por Svcutil están diseñados para su uso en .NET Framework.**

Las soluciones que usan clientes WCF generados por svcutil necesitarán volver a generar clientes compatibles con .NET Standard para su uso con .NET Core. Una de las principales razones por las que los clientes antiguos no funcionarán es que dependen de la configuración de la aplicación para definir enlaces WCF y extremos. Dado que las API de WCF estándar de .NET pueden trabajar multiplataforma (donde las API de System.Configuration no están disponibles), los clientes WCF para escenarios de .NET Core y .NET Standard deben definir enlaces y extremos mediante programación en lugar de en la configuración.

De hecho, cualquier uso de `<system.serviceModel>` cliente WCF que depende de la sección app.config (si se crea con Svcutil o manualmente) deberá cambiarse para que funcione en .NET Core.

Hay dos maneras de generar automáticamente clientes WCF compatibles con .NET Standard:

- La `dotnet-svcutil` herramienta es una herramienta de .NET que genera clientes WCF de una manera similar a cómo Svcutil funcionaba anteriormente.
- Visual Studio puede generar clientes WCF mediante la opción [Referencia de servicio Web WCF](../../core/additional-tools/wcf-web-service-reference-guide.md) de su característica Servicios conectados.

Cualquiera de los dos enfoques funciona bien. Como alternativa, por supuesto, podría escribir el código de cliente WCF usted mismo. Para este ejemplo, elegí usar la característica de servicio conectado de Visual Studio. Para ello, haga clic con el botón derecho en el proyecto *BeanTraderClient.Core* en el explorador de soluciones de Visual Studio y seleccione **Agregar** > **servicio conectado**. A continuación, elija el proveedor de referencia de servicio Web WCF. Esto abrirá un cuadro de diálogo donde puede especificar la dirección`localhost:8080` del servicio web backend Bean Trader (si está ejecutando el servidor localmente) y el espacio de nombres que los tipos generados deben utilizar (**BeanTrader.Service**, por ejemplo).

![Cuadro de diálogo Servicio conectado de referencia de servicio Web WCF](./media/convert-project-from-net-framework/connected-service-dialog.png)

Después de seleccionar **el** finalizar botón, se agrega un nuevo servicios conectados nodo se agrega al proyecto y se agrega un archivo de Reference.cs bajo ese nodo que contiene el nuevo cliente WCF estándar de .NET para tener acceso al servicio Bean Trader. Si observa los `GetEndpointAddress` `GetBindingForEndpoint` métodos o en ese archivo, verá que los enlaces y los extremos ahora se generan mediante programación (en lugar de a través de la configuración de la aplicación). La característica 'Agregar servicios conectados' también puede agregar referencias a algunos paquetes System.ServiceModel en el archivo de proyecto, que no son necesarios, ya que todos los paquetes WCF necesarios se incluyen a través de Microsoft.Windows.Compatibility. Compruebe el csproj para ver si `<PackageReference>` se han agregado elementos System.ServiceModel adicionales y, si es así, quitarlos.

Nuestro proyecto tiene nuevas clases de cliente WCF ahora (en *Reference.cs*), pero también tiene las antiguas (en BeanTrader.cs). Hay dos opciones en este punto:

- Si desea poder compilar el proyecto original de .NET Framework (junto con el nuevo de `<Compile Remove="BeanTrader.cs" />` objeto de .NET Core), puede usar un elemento en el archivo csproj del proyecto de .NET Core para que las versiones de .NET Framework y .NET Core de la aplicación usen diferentes clientes WCF. Esto tiene la ventaja de dejar el proyecto de .NET Framework existente sin cambios, pero tiene la desventaja de que el código que usa los clientes `#if` WCF generados puede necesitar ser ligeramente diferente en el caso de .NET Core que en el proyecto de .NET Framework, por lo que es probable que tenga que usar directivas para compilar condicionalmente algún uso de cliente WCF (crear clientes, por ejemplo) para trabajar de una manera cuando se compila para .NET Core y otra manera cuando se compila para .NET Framework.

- Si, por otro lado, alguna renovación de código en el proyecto de .NET Framework existente es aceptable, puede quitar *BeanTrader.cs* todos juntos. Dado que el nuevo cliente WCF está compilado para .NET Standard, funcionará en escenarios de .NET Core y .NET Framework. Si está creando para .NET Framework además de .NET Core (ya sea por segmentación múltiple o por tener dos archivos csproj), puede usar este nuevo archivo *de Reference.cs* para ambos destinos. Este enfoque tiene la ventaja de que el código no tendrá que bifurcarse para admitir dos clientes WCF diferentes; el mismo código se utilizará en todas partes. El inconveniente es que implica cambiar el proyecto de .NET Framework (presumiblemente estable).

En el caso del ejemplo Bean Trader, puede realizar pequeños cambios en el proyecto original si facilita la migración, por lo que siga estos pasos para conciliar el uso del cliente WCF:

01. Agregue el nuevo archivo Reference.cs al proyecto *BeanTraderClient.csproj* de .NET Framework mediante el menú contextual 'Agregar elemento existente' del explorador de soluciones. Asegúrese de agregar 'as link' para que ambos proyectos utilicen el mismo archivo (en lugar de copiar el archivo de C-). Si está creando para .NET Core y .NET Framework con un único csproj (mediante la segmentación múltiple), este paso no es necesario.

01. Eliminar *BeanTrader.cs*.

01. El nuevo cliente WCF es similar al anterior, pero un número de espacios de nombres en el código generado son diferentes. Por este motivo, es necesario actualizar el proyecto para que los tipos de cliente WCF se utilicen desde BeanTrader.Service (o cualquier nombre de espacio de nombres que haya elegido) en lugar de BeanTrader.Model o sin un espacio de nombres. La creación de *BeanTraderClient.Core.csproj* ayudará a identificar dónde se deben realizar estos cambios. Se necesitarán correcciones tanto en C- como en archivos de código fuente XAML.

01. Por último, descubrirá que hay un error en *BeanTraderServiceClientFactory.cs* porque `BeanTraderServiceClient` los constructores disponibles para el tipo han cambiado. Solía ser posible proporcionar `InstanceContext` un argumento (que `CallbackHandler` se `Castle.Windsor` creó mediante un contenedor de IoC). Los nuevos constructores `CallbackHandler`crean nueva s. Sin embargo, hay `BeanTraderServiceClient`constructores en el tipo base de 's que coinciden con lo que desea. Puesto que el código de cliente WCF generado automáticamente existe en clases parciales, puede ampliarlo fácilmente. Para ello, cree un nuevo archivo denominado *BeanTraderServiceClient.cs* y, a continuación, cree una clase parcial con el mismo nombre (utilizando el espacio de nombres BeanTrader.Service). A continuación, agregue un constructor al tipo parcial como se muestra aquí.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Con los cambios realizados, el bean Trader ejemplo ahora usará un nuevo cliente WCF compatible `Open` con .NET `await OpenAsync` Standard y puede realizar la corrección final de cambiar la llamada en *TradingService.cs* usar en su lugar.

Con los problemas de WCF solucionados, la versión de .NET Core de la bean Trader ejemplo ahora se compila limpiamente!

## <a name="runtime-testing"></a>Pruebas en tiempo de ejecución

Es fácil olvidar que el trabajo de migración no se realiza tan pronto como el proyecto se compila limpiamente en .NET Core. También es importante dejar tiempo para probar la aplicación porteada. Una vez que las cosas se compilan correctamente, asegúrese de que la aplicación se ejecuta y funciona según lo esperado, especialmente si usa paquetes destinados a .NET Framework.

Vamos a tratar de iniciar la aplicación portado Bean Trader y ver qué pasa. La aplicación no llega mucho antes de fallar con la siguiente excepción.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Esto tiene sentido, por supuesto. Recuerde que WCF ya no usa la configuración de la aplicación, por lo que debe quitarse la sección system.serviceModel anterior del archivo app.config. El cliente WCF actualizado incluye toda la misma información en su código, por lo que la sección de configuración ya no es necesaria. Si desea que el extremo WCF sea configurable en app.config, podría agregarlo como una configuración de aplicación y actualizar el código de cliente WCF para recuperar el extremo del servicio WCF de la configuración.

Después de quitar la sección system.serviceModel de *app.config*, la aplicación se inicia pero se produce un error con otra excepción cuando un usuario inicia sesión.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

La API no `Func<T>.BeginInvoke`admitida es . Como se explica en [dotnet/corefx-5940](https://github.com/dotnet/corefx/issues/5940), .NET `BeginInvoke` `EndInvoke` Core no admite los métodos y en los tipos de delegado debido a las dependencias de comunicación remota subyacentes. Este problema y su corrección se explican con más detalle en la entrada de blog [Migrating Delegate.BeginInvoke Calls for .NET Core,](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) pero la esencia es esa `BeginInvoke` y `EndInvoke` las llamadas deben reemplazarse por `Task.Run` (o alternativas asincrónicas, si es posible). Aplicando la solución `BeginInvoke` general aquí, la `Invoke` llamada se `Task.Run`puede substituir con una llamada lanzada por .

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

Después `BeginInvoke` de eliminar el uso, la aplicación Bean Trader se ejecuta con éxito en .NET Core!

![Bean Trader que se ejecuta en .NET Core](./media/convert-project-from-net-framework/running-on-core.png)

Todas las aplicaciones son diferentes, por lo que los pasos específicos necesarios para migrar sus propias aplicaciones a .NET Core variarán. Pero esperemos que el ejemplo de Bean Trader muestre el flujo de trabajo general y los tipos de problemas que se pueden esperar. Y, a pesar de la duración de este artículo, los cambios reales necesarios en la muestra de Bean Trader para que funcionara en .NET Core eran bastante limitados. Muchas aplicaciones migran a .NET Core de esta misma manera; con cambios de código limitados o incluso sin necesidad de cambios de código.
