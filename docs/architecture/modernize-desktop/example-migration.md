---
title: Ejemplo de migración a .NET 5
description: Se muestra cómo realizar la migración a .NET 5 de una aplicación de ejemplo que tiene como destino .NET Framework.
ms.date: 01/19/2021
ms.openlocfilehash: 02a45859dfca891598e235e3de1ed968aefb5bf4
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605170"
---
# <a name="example-of-migrating-to-net"></a>Ejemplo de migración a .NET

En este capítulo, se presentan instrucciones prácticas que le ayudarán a realizar una migración de la aplicación existente desde .NET Framework a .NET.

Se presenta un proceso bien estructurado que se puede seguir, además de los aspectos más importantes que hay que tener en cuenta en cada paso.

Luego, se documenta el proceso de migración paso a paso de una aplicación de escritorio de ejemplo, tanto para WinForms como WPF.

## <a name="migration-process-overview"></a>Introducción al proceso de migración

El proceso de migración consta de cuatro pasos secuenciales:

1. **Preparación**: se describen las dependencias que tiene el proyecto para hacerse una idea de lo que está por venir. En este paso, se lleva el proyecto actual a un estado que simplifica el punto de inicio de la migración.

2. **Migración del archivo del proyecto:** los proyectos de .NET usan el nuevo formato de proyecto de estilo SDK. Cree un archivo del proyecto con este formato o actualice el que tenga para usar el estilo de SDK.

3. **Corrección del código y compilación:** compile el código en .NET para resolver las diferencias de nivel de API entre .NET Framework y .NET. Si es necesario, actualice los paquetes de terceros con los que admiten .NET.

4. **Ejecución y pruebas:** es posible que haya diferencias que no se muestren hasta el tiempo de ejecución. Por tanto, no olvide ejecutar la aplicación y comprobar que todo funciona según lo previsto.

### <a name="preparation"></a>Preparación

#### <a name="migrate-packagesconfig-file"></a>Migración del archivo packages.config

En una aplicación .NET Framework, todas las referencias a los paquetes externos se declaran en el archivo *packages.config*. En .NET, ya no es necesario usar el archivo *packages.config*. En su lugar, use la propiedad [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) del archivo del proyecto para especificar los paquetes NuGet para la aplicación.

Por tanto, debe realizar la transición de un formato a otro. Puede realizar la actualización manualmente, tomar las dependencias incluidas en el archivo *packages.config* y migrarlas al archivo del proyecto con el formato `PackageReference`. También puede dejar que Visual Studio lo haga automáticamente: haga clic con el botón derecho en el archivo *packages.config* y seleccione la opción **Migrar packages.config a PackageReference**.

#### <a name="verify-every-dependency-compatibility-in-net"></a>Comprobación de la compatibilidad de todas las dependencias en .NET

Cuando haya migrado las referencias de paquete, debe comprobar la compatibilidad de cada una de ellas. Puede explorar las dependencias de cada paquete NuGet que la aplicación usa en [nuget.org](https://www.nuget.org/). Si el paquete tiene dependencias de .NET Standard, funcionará en .NET 5.0, ya que .NET [admite](../../standard/net-standard.md#net-implementation-support) todas las versiones de .NET Standard. En la imagen siguiente se muestran las dependencias del paquete `Castle.Windsor`:

![Captura de pantalla de las dependencias de NuGet del paquete Castle.Windsor](./media/example-migration-core/nuget-dependencies.png)

Para comprobar la compatibilidad del paquete, puede usar la herramienta <https://fuget.org>, que ofrece información más detallada sobre las versiones y las dependencias.

Es posible que el proyecto haga referencia a versiones anteriores de paquetes que no son compatibles con .NET, pero podría encontrar versiones más recientes que sí lo sean. Por tanto, la actualización de paquetes a versiones más recientes suele ser una buena recomendación. Pero debe tener en cuenta que la actualización de la versión del paquete puede introducir algunos cambios importantes que le obligarían a actualizar el código.

¿Qué ocurre si no encuentra una versión admitida? ¿Qué ocurre si no quiere actualizar la versión de un paquete debido a estos cambios importantes? No se preocupe, ya que es posible depender de paquetes de .NET Framework desde una aplicación .NET. No olvide probarla exhaustivamente porque puede provocar errores en tiempo de ejecución si el paquete externo llama a una API que no está disponible en .NET. Esto resulta útil cuando se usa un paquete antiguo que no se va a actualizar y se puede simplemente redestinar para que funcione en .NET.

#### <a name="check-for-api-compatibility"></a>Comprobación de la compatibilidad de la API

Como la superficie de API en .NET Framework y .NET es similar pero no idéntica, hay que comprobar qué API están disponibles en .NET y cuáles no. Puede usar la herramienta Analizador de portabilidad de .NET para exponer las API usadas que no están presentes en .NET. Examina el nivel binario de la aplicación, extrae todas las API a las que se llama y, después, muestra las API que no están disponibles en la plataforma de destino (.NET 5.0 en este caso).

Puede encontrar más información sobre esta herramienta en:

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

Un aspecto interesante de esta herramienta es que solo expone las diferencias del código propio, no del código de paquetes externos, que no se puede cambiar. Recuerde que debe haber actualizado la mayoría de estos paquetes para que funcionen con .NET.

### <a name="migrate-with-try-convert-tool"></a>Migración con la herramienta try-convert

La herramienta [try-convert](https://github.com/dotnet/try-convert/releases) es una excelente manera de migrar un proyecto. Se trata de una herramienta global que intenta actualizar el archivo del proyecto del estilo anterior al nuevo estilo del SDK y redestina los proyectos aplicables a .NET 5. Después de instalarla, puede ejecutar los siguientes comandos:

```dotnetcli
try-convert -p "<path to your project file>"
```

O:

```dotnetcli
try-convert -w "<path to your solution>"
```

> [!NOTE]
> La herramienta try-convert se ejecuta automáticamente como parte de la [herramienta Asistente para actualización de .NET](https://aka.ms/dotnet-upgrade-assistant). Considere la posibilidad de ejecutar el Asistente para actualización completo y no solo try-convert.

Después de que la herramienta intente la conversión, vuelva a cargar los archivos en Visual Studio para ejecutarlos y probarlos. Existe la posibilidad de que try-convert no pueda realizar la conversión debido a aspectos concretos del proyecto. En ese caso, puede consultar los pasos siguientes.

#### <a name="migrate-manually"></a>Migración manual

1. Creación del proyecto de .NET

En la mayoría de los casos, querrá actualizar el proyecto existente al nuevo formato de .NET. Pero también puede crear otro proyecto mientras mantiene el anterior. La principal desventaja de actualizar el proyecto anterior es que pierde la compatibilidad con el diseñador, que puede ser importante para usted y el equipo de desarrollo. Si quiere seguir usando el diseñador, debe crear un proyecto de .NET en paralelo con el antiguo y compartir los recursos. Si tiene que modificar elementos de la interfaz de usuario en el diseñador, puede cambiar al proyecto anterior para hacerlo. Y como los recursos están vinculados, también se actualizarán en el proyecto de .NET.

El [proyecto de estilo del SDK](../../core/project-sdk/msbuild-props.md) para .NET es mucho más sencillo que el formato de proyecto de .NET Framework. Aparte de las entradas `PackageReference` anteriormente mencionadas, no tendrá que hacer mucho más. El nuevo formato de proyecto [incluye archivos con determinadas extensiones de forma predeterminada](../../core/project-sdk/overview.md#default-includes-and-excludes), como los archivos `.cs` y `.xaml`, sin necesidad de incluirlos explícitamente en el archivo del proyecto.

#### <a name="assemblyinfo-considerations"></a>Consideraciones de AssemblyInfo

En los proyectos de .NET, los atributos se generan de forma automática. Si el proyecto contiene un archivo *AssemblyInfo.cs*, las definiciones se duplicarán, lo que provocará conflictos de compilación. Puede eliminar el archivo *AssemblyInfo.cs* anterior o deshabilitar la generación automática si agrega la siguiente entrada al archivo del proyecto de .NET:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>Recursos

Los recursos incrustados se incluyen de forma automática, pero no los recursos, por lo que debe migrarlos al nuevo archivo del proyecto.

#### <a name="package-references"></a>Referencias de paquete

Con la opción **Migrar packages.config a PackageReference**, puede trasladar fácilmente las referencias de paquetes externos al nuevo formato, como se ha mencionado antes.

#### <a name="update-package-references"></a>Actualización de las referencias del paquete

Actualice las versiones de los paquetes que ha comprobado que se admiten, tal como se ha mostrado en la sección anterior.

### <a name="fix-the-code-and-build"></a>Corrección y compilación del código

#### <a name="microsoftwindowscompatibility"></a>Microsoft.Windows.Compatibility

Si la aplicación depende de API que no están disponibles en .NET, como las de Registro, listas de control de acceso o WCF, tiene que incluir una referencia al paquete `Microsoft.Windows.Compatibility` para agregar estas API específicas de Windows. Funcionan en .NET, pero no se incluyen porque no son multiplataforma.

Hay una herramienta denominada Analizador de API (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) que le ayuda a identificar las API que no son compatibles con el código.

#### <a name="use-if-directives"></a>Uso de directivas \#if

Si necesita otras rutas de ejecución al establecer .NET Framework y .NET como destino, debe utilizar constantes de compilación. Agregue algunas directivas \#if al código para mantener la misma base de código para los dos destinos.

#### <a name="technologies-not-available-on-net"></a>Tecnologías no disponibles en .NET

Algunas tecnologías no están disponibles en .NET, como las siguientes:

* Dominios de aplicaciones
* Comunicación remota
* Seguridad de acceso del código
* Servidor WCF
* Windows Workflow

Por este motivo, tendrá que buscar algo que reemplace a estas tecnologías si las usa en la aplicación. Para obtener más información, vea el artículo [Tecnologías de .NET Framework no disponibles en .NET Core y .NET 5+](../../core/porting/net-framework-tech-unavailable.md).

#### <a name="regenerate-autogenerated-clients"></a>Regeneración de clientes generados automáticamente

Si la aplicación usa código generado automáticamente, como un cliente de WCF, es posible que tenga que volver a generar este código para seleccionar .NET como destino. En ocasiones, puede descubrir que faltan algunas referencias, ya que no se incluyen como parte del conjunto de ensamblados de .NET predeterminado. Con una herramienta como <https://apisof.net/>, puede encontrar fácilmente el ensamblado en el que reside la referencia que falta y agregarlo desde NuGet.

#### <a name="rolling-back-package-versions"></a>Reversión de versiones de paquetes

Como norma general, ya se ha indicado que es mejor actualizar cada versión del paquete para que sea compatible con .NET. Pero puede descubrir que seleccionar como destino una versión actualizada y admitida de un ensamblado no vale la pena. Si el costo del cambio no es aceptable, puede plantearse revertir versiones de paquetes y conservar las que use en .NET Framework. Aunque es posible que no tengan como destino .NET, deben funcionar bien, a menos que llamen a API no admitidas.

### <a name="run-and-test"></a>Ejecución y prueba

Una vez que la aplicación se compila sin errores, puede iniciar el último paso de la migración y probar cada funcionalidad.

En este paso final, puede encontrar varios problemas diferentes en función de la complejidad de la aplicación y de las dependencias y las API que use.

Por ejemplo, si usa archivos de configuración (*app.config*), puede detectar algunos errores en tiempo de ejecución, como la ausencia de secciones de configuración. El uso del paquete NuGet `Microsoft.Extensions.Configuration` debe corregir este error.

Otro motivo de los errores es el uso de los métodos `BeginInvoke` y `EndInvoke`, ya que no se admiten en .NET. No se admiten en .NET porque tienen una dependencia en la comunicación remota, que no existe en .NET. Para solucionar este problema, intente usar la palabra clave `await` (si está disponible) o el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>.

Puede usar analizadores de compatibilidad que le permitan identificar las API y los patrones de código del código que pueden causar problemas en tiempo de ejecución con .NET. Vaya a <https://github.com/dotnet/platform-compat> y use el Analizador de API de .NET en el proyecto.

## <a name="migrating-a-windows-forms-application"></a>Migración de una aplicación de Windows Forms

Para mostrar un proceso completo de migración de una aplicación de Windows Forms, se ha optado por migrar la aplicación de ejemplo eShop disponible en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>. Puede ver el resultado completo de la migración en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.

Esta aplicación muestra un catálogo de productos y permite al usuario navegar por los productos, filtrarlos y buscarlos. Desde el punto de vista de la arquitectura, la aplicación se basa en un servicio WCF externo que sirve de fachada a una base de datos de back-end.

Puede ver la ventana principal de la aplicación en la siguiente imagen:

![Ventana principal de la aplicación](./media/example-migration-core/main-application-window.png)

Si abre el archivo *.csproj* del proyecto, puede ver algo parecido a lo siguiente:

![Captura de pantalla del contenido del archivo .csproj](./media/example-migration-core/csproj-file.png)

Como se ha mencionado antes, el proyecto de .NET tiene un estilo más compacto y hay que migrar la estructura del proyecto al nuevo estilo del SDK de .NET.

En el Explorador de soluciones, haga clic con el botón derecho en el proyecto de Windows Forms y seleccione **Descargar el proyecto** > **Editar**.

Ahora puede actualizar el archivo .csproj. Eliminará todo el contenido y lo reemplazará por el código siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

Guarde el proyecto y vuelva a cargarlo. Ya ha terminado de actualizar el archivo del proyecto y el proyecto tiene como destino .NET.

Si compila el proyecto en este momento, encontrará algunos errores relacionados con la referencia de cliente de WCF. Como este código se genera automáticamente, debe volver a generarlo para que tenga como destino .NET.

![Lista de errores con errores en Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

Elimine el archivo *Reference.cs* y genere un nuevo cliente de servicio.

Haga clic con el botón derecho en **Servicios conectados** y seleccione la opción **Agregar servicio conectado**.

![Captura de pantalla del menú Servicios conectados con la opción Agregar servicio conectado seleccionada](./media/example-migration-core/add-connected-service.png)

Se abre la ventana Servicios conectados. Seleccione la opción  **Microsoft WCF Web Service Reference Provider**.

![Captura de pantalla de la ventana Servicios conectados](./media/example-migration-core/connected-services-window.png)

Si tiene el servicio WCF en la misma solución que en este ejemplo, puede seleccionar la opción **Descubrir** en lugar de especificar una dirección URL de servicio.

![Captura de pantalla de la ventana Configurar referencia de servicio web de WCF](./media/example-migration-core/configure-wcf-reference.png)

Una vez que se encuentra el servicio, la herramienta refleja el contrato de API implementado por el servicio. Cambie el nombre del espacio de nombres por `eShopServiceReference`, como se muestra en la siguiente imagen:

![Captura de pantalla del contrato de API y el espacio de nombres cambiado](./media/example-migration-core/api-contract-namespace.png)

Seleccione el botón **Finalizar**. Después de un tiempo, verá el código generado.

Debería ver tres archivos generados automáticamente:

1. *Introducción*: vínculo a GitHub para proporcionar información sobre WCF.
2. *ConnectedService.json*: parámetros de configuración para conectarse al servicio.
3. *Reference.cs*: el código de cliente de WCF real.

![Captura de pantalla de la ventana Explorador de soluciones con los tres archivos autogenerados](./media/example-migration-core/autogenerated-files.png)

Si vuelve a compilar, verá muchos errores procedentes de archivos *.cs* dentro de la carpeta *Asistentes*. Esta carpeta estaba presente en la versión de .NET Framework pero no en el archivo *.csproj* anterior. Pero, con el nuevo proyecto de estilo del SDK, todos los archivos de código presentes en la ubicación del archivo del proyecto se incluyen de forma predeterminada. Es decir, el nuevo proyecto de .NET Core intenta compilar los archivos dentro de la carpeta *Asistentes*. Como esa carpeta no es necesaria, puede eliminarla de forma segura.

Si vuelve a compilar el proyecto y lo ejecuta, no verá las imágenes del producto. El problema es que ahora la ruta de acceso a los archivos ha cambiado ligeramente. Para corregir este problema, debe agregar otro nivel de profundidad en la ruta de acceso y actualizar la línea siguiente en el archivo `CatalogView.cs`:

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

en

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

Después de este cambio, puede comprobar que la aplicación se inicia y se ejecuta según lo previsto en .NET Core.

## <a name="migrating-a-wpf-application"></a>Implementación de una aplicación WPF

Para realizar la migración se usará la aplicación de ejemplo `Shop.ClassicWPF`. En la imagen siguiente se muestra una captura de pantalla de la aplicación antes de la migración:

![Aplicación de ejemplo antes de la migración](./media/example-migration-core/app-before-migration.png)

En esta aplicación se usa una base de datos de SQL Server Express local para almacenar la información del catálogo de productos. A esta base de datos se accede directamente desde la aplicación WPF.

En primer lugar, debe actualizar el archivo *.csproj* al nuevo estilo del SDK que usan las aplicaciones .NET Core. Seguirá los mismos pasos descritos en la migración de Windows Forms: descargará el proyecto, abrirá el archivo *.csproj*, actualizará su contenido y volverá a cargar el proyecto.

En este caso, elimine todo el contenido del archivo *.csproj* y reemplácelo por el código siguiente:

```xml
 <Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWpf>true</UseWpf>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

Si vuelve a cargar el proyecto y lo compila, obtendrá el error siguiente:

![Lista de errores en Visual Studio en la que se muestra un error CS0234](./media/example-migration-core/wpf-compilation-error.png)

Como ha eliminado todo el contenido de *.csproj*, ha perdido una especificación de referencia de proyecto presente en el proyecto anterior. Solo tiene que agregar esta línea al archivo *.csproj* para volver a incluir la referencia de proyecto:

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

También puede dejar que Visual Studio le ayude si hace clic con el botón derecho en el nodo **Dependencias** y selecciona **Agregar referencia de proyecto**. Seleccione el proyecto de la solución y haga clic en **Aceptar**:

![Captura de pantalla del cuadro de diálogo Administrador de referencias con el proyecto eShop.SqlProvider seleccionado](./media/example-migration-core/reference-manager.png)

Una vez que se agrega la referencia de proyecto que falta, la aplicación se compila y se ejecuta según lo previsto en .NET.

>[!div class="step-by-step"]
>[Anterior](windows-migration.md)
>[Siguiente](deploy-modern-applications.md)
