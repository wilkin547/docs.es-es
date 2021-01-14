---
title: Ejemplo de migración a .NET Core 3.1
description: Muestra cómo migrar una aplicación de ejemplo que tiene como destino .NET Framework a .NET Core 3,1.
ms.date: 05/12/2020
ms.openlocfilehash: dc0d3d825847bd72a38469615cfc5b2d793f1977
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188782"
---
# <a name="example-of-migrating-to-net-core-31"></a>Ejemplo de migración a .NET Core 3.1

En este capítulo, presentamos instrucciones prácticas que le ayudarán a realizar una migración de la aplicación existente desde .NET Framework a .NET Core.

Presentamos un proceso bien estructurado que puede seguir y los aspectos más importantes que se deben tener en cuenta en cada paso.

A continuación, documentamos un proceso de migración paso a paso para una aplicación de escritorio de ejemplo, tanto de las versiones de WinForms como de WPF.

## <a name="migration-process-overview"></a>Introducción al proceso de migración

El proceso de migración consta de cuatro pasos secuenciales:

1. **Preparación**: comprenda las dependencias que el proyecto tiene para tener una idea del avance. En este paso, se toma el proyecto actual en un estado que simplifica el punto de inicio de la migración.

2. **Migrar archivo de proyecto:** los proyectos de .net Core usan el nuevo formato de proyecto de estilo de SDK. Cree un nuevo archivo de proyecto con este formato o actualice el que tenga para usar el estilo SDK.

3. **Corregir código y compilar:** Compile el código en .NET Core para resolver las diferencias de nivel de API entre .NET Framework y .NET Core. Si es necesario, actualice los paquetes de terceros a los que admiten .NET Core.

4. **Ejecutar y probar:** Puede haber diferencias que no se muestren hasta el tiempo de ejecución. Por lo tanto, no olvide ejecutar la aplicación y comprobar que todo funciona según lo previsto.

### <a name="preparation"></a>Preparación

#### <a name="migrate-packagesconfig-file"></a>Migrar archivo de packages.config

En una aplicación .NET Framework, todas las referencias a paquetes externos se declaran en el archivo de *packages.config* . En .NET Core, ya no es necesario usar el archivo de *packages.config* . En su lugar, use la propiedad [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) en el archivo de proyecto para especificar los paquetes de NuGet para la aplicación.

Por lo tanto, debe realizar la transición de un formato a otro. Puede realizar la actualización manualmente, tomando las dependencias contenidas en el archivo de *packages.config* y migrarlas al archivo de proyecto con el `PackageReference` formato. O bien, puede dejar que Visual Studio haga el trabajo por usted: haga clic con el botón derecho en el archivo de *packages.config* y seleccione la opción **migrar packages.config a PackageReference** .

#### <a name="verify-every-dependency-compatibility-in-net-core"></a>Comprobar la compatibilidad de todas las dependencias en .NET Core

Una vez que haya migrado las referencias de paquete, debe comprobar la compatibilidad de cada referencia. Puede explorar las dependencias de cada paquete NuGet que está usando la aplicación en [Nuget.org](https://www.nuget.org/). Si el paquete tiene dependencias .NET Standard, se va a trabajar en .NET Core porque .NET Core 3,1 [es compatible con](../../standard/net-standard.md#net-implementation-support) todas las versiones de .net Standard. En la imagen siguiente se muestran las dependencias del `Castle.Windsor` paquete:

![Captura de pantalla de las dependencias de NuGet para el paquete de. Windsor](./media/example-migration-core/nuget-dependencies.png)

Para comprobar la compatibilidad del paquete, puede usar la herramienta <https://fuget.org> que ofrece información más detallada sobre las versiones y las dependencias.

Es posible que el proyecto haga referencia a versiones anteriores de paquetes que no son compatibles con .NET Core, pero puede que encuentre versiones más recientes que las admitan. Por lo tanto, la actualización de paquetes a versiones más recientes suele ser una buena recomendación. Sin embargo, debe tener en cuenta que la actualización de la versión del paquete puede introducir algunos cambios importantes que le obligarían a actualizar el código.

¿Qué ocurre si no encuentra una versión compatible? ¿Qué ocurre si no desea actualizar la versión de un paquete debido a estos cambios importantes? No se preocupe porque es posible depender de .NET Framework paquetes desde una aplicación de .NET Core. No olvide probarla exhaustivamente porque puede provocar errores en tiempo de ejecución si el paquete externo llama a una API que no está disponible en .NET Core. Esto resulta útil cuando se usa un paquete antiguo que no se va a actualizar y se puede simplemente redestinar para que funcione en .NET Core.

#### <a name="check-for-api-compatibility"></a>Comprobar la compatibilidad de API

Dado que la superficie de API en .NET Framework y .NET Core es similar pero no idéntica, debe comprobar qué API están disponibles en .NET Core y cuáles no. Puede usar la herramienta analizador de portabilidad de .NET para Surface API que no está presente en .NET Core. Examina el nivel binario de la aplicación, extrae todas las API a las que se llama y, después, muestra las API que no están disponibles en la plataforma de destino (.NET Core 3,1 en este caso).

Puede encontrar más información sobre esta herramienta en:

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

Un aspecto interesante de esta herramienta es que solo muestra las diferencias de su propio código y no el código de los paquetes externos, que no se pueden cambiar. Recuerde que debe haber actualizado la mayoría de estos paquetes para que funcionen con .NET Core.

### <a name="migrate-project-file"></a>Migrar archivo de proyecto

#### <a name="create-the-new-net-core-project"></a>Crear el nuevo proyecto de .NET Core

En la mayoría de los casos, querrá actualizar el proyecto existente al nuevo formato de .NET Core. Sin embargo, también puede crear un nuevo proyecto manteniendo el anterior. El principal inconveniente de actualizar el proyecto anterior es que pierde la compatibilidad con el diseñador, que puede ser importante para usted. Si desea seguir usando el diseñador, debe crear un nuevo proyecto de .NET Core en paralelo con el antiguo y compartir los recursos. Si necesita modificar los elementos de la interfaz de usuario en el diseñador, puede cambiar al proyecto anterior para hacerlo. Y como los activos están vinculados, también se actualizarán en el proyecto de .NET Core.

El [proyecto de estilo SDK](../../core/project-sdk/msbuild-props.md) para .net Core es mucho más sencillo que el formato de proyecto de .NET Framework. Además de las entradas mencionadas anteriormente `PackageReference` , no tendrá que hacer mucho más. El nuevo formato de proyecto [incluye archivos con determinadas extensiones de forma predeterminada](../../core/project-sdk/overview.md#default-includes-and-excludes), `.cs` como `.xaml` archivos y, sin necesidad de incluirlos explícitamente en el archivo de proyecto.

#### <a name="assemblyinfo-considerations"></a>Consideraciones sobre Assembly.info

Los atributos se generan automáticamente en los proyectos de .NET Core. Si el proyecto contiene un archivo *AssemblyInfo.CS* , las definiciones se duplicarán, lo que provocará conflictos de compilación. Puede eliminar el archivo *AssemblyInfo.CS* anterior o deshabilitar la generación de perfiles agregando la siguiente entrada al archivo de proyecto de .net Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>Recursos

Los recursos incrustados se incluyen automáticamente, pero no los recursos, por lo que debe migrar los recursos al nuevo archivo de proyecto.

#### <a name="package-references"></a>Referencias de paquete

Con la opción **migrar packages.config a PackageReference** , puede trasladar fácilmente las referencias de paquetes externos al nuevo formato, como se mencionó anteriormente.

#### <a name="update-package-references"></a>Actualización de las referencias del paquete

Actualice las versiones de los paquetes que ha encontrado como compatibles, tal como se muestra en la sección anterior.

### <a name="fix-the-code-and-build"></a>Corregir el código y compilar

#### <a name="microsoftwindowscompatibility"></a>Microsoft. Windows. Compatibility

Si su aplicación depende de las API que no están disponibles en .NET Core, como registro, ACL o WCF, tiene que incluir una referencia al `Microsoft.Windows.Compatibility` paquete para agregar estas API específicas de Windows. Funcionan en .NET Core, pero no se incluyen porque no son multiplataforma.

Hay una herramienta denominada API Analyzer ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ) que le ayuda a identificar las API que no son compatibles con el código.

#### <a name="use-if-directives"></a>Usar \# directivas if

Si necesita diferentes rutas de ejecución al tener como destino .NET Framework y .NET Core, debe usar constantes de compilación. Agregue algunas \# directivas if al código para mantener la misma base de código para ambos destinos.

#### <a name="technologies-not-available-on-net-core"></a>Tecnologías no disponibles en .NET Core

Algunas tecnologías no están disponibles en .NET Core, como:

* Dominios de aplicaciones
* Comunicación remota
* Seguridad de acceso del código
* Servidor WCF
* Flujo de trabajo de Windows

Esta es la razón por la que necesita buscar una sustitución para estas tecnologías si las usa en la aplicación. Para obtener más información, consulte el artículo [.NET Framework Technologies no está disponible en .net Core](../../core/porting/net-framework-tech-unavailable.md) .

#### <a name="regenerate-autogenerated-clients"></a>Regenerar clientes generados automáticamente

Si la aplicación usa código generado automáticamente, como un cliente de WCF, es posible que tenga que volver a generar este código para tener como destino .NET Core. A veces, puede encontrar algunas referencias que faltan, ya que no se incluyen como parte del conjunto de ensamblados de .NET Core predeterminados. Con una herramienta como <https://apisof.net/> , puede encontrar fácilmente el ensamblado en el que reside la referencia que falta y agregarlo desde NuGet.

#### <a name="rolling-back-package-versions"></a>Revertir versiones de paquetes

Como norma general, ya hemos indicado que se actualizan mejor todas las versiones de paquete único para que sean compatibles con .NET Core. Sin embargo, puede encontrar que el destino de una versión actualizada y compatible de un ensamblado no se pague. Si el costo del cambio no es aceptable, puede considerar la posibilidad de revertir versiones de paquetes manteniendo las que usa en .NET Framework. Aunque es posible que no tengan como destino .NET Core, deben funcionar bien a menos que llamen a algunas API no admitidas.

### <a name="run-and-test"></a>Ejecución y prueba

Una vez que la aplicación se compila sin errores, puede iniciar el último paso de la migración probando cada funcionalidad.

En este paso final, puede encontrar varios problemas diferentes en función de la complejidad de la aplicación y de las dependencias y las API que esté usando.

Por ejemplo, si usa archivos de configuración (*app.config*), puede encontrar algunos errores en tiempo de ejecución, como las secciones de configuración que no están presentes. El uso del `Microsoft.Extensions.Configuration` paquete NuGet debe corregir este error.

Otro motivo de los errores es el uso de `BeginInvoke` los `EndInvoke` métodos y porque no se admiten en .net Core. No se admiten en .NET Core porque tienen una dependencia en la comunicación remota, que no existe en .NET Core. Para solucionar este problema, intente usar la `await` palabra clave (si está disponible) o el <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> método.

Puede usar analizadores de compatibilidad para permitirle identificar API y patrones de código en el código que pueden causar problemas en tiempo de ejecución con .NET Core. Vaya a <https://github.com/dotnet/platform-compat> y use el analizador de API de .net en el proyecto.

## <a name="migrating-a-windows-forms-application"></a>Migración de una aplicación Windows Forms

Para exhibir un proceso de migración completo de una aplicación Windows Forms, hemos elegido migrar la aplicación de ejemplo de eShop disponible en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> . Puede encontrar el resultado completo de la migración en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .

Esta aplicación muestra un catálogo de productos y permite al usuario navegar, filtrar y buscar productos. Desde el punto de vista de la arquitectura, la aplicación se basa en un servicio WCF externo que sirve de fachada a una base de datos back-end.

Puede ver la ventana principal de la aplicación en la siguiente imagen:

![Ventana principal de la aplicación](./media/example-migration-core/main-application-window.png)

Si abre el archivo de proyecto *. csproj* , puede ver algo parecido a esto:

![Captura de pantalla del contenido del archivo csproj](./media/example-migration-core/csproj-file.png)

Como se mencionó anteriormente, el proyecto de .NET Core tiene un estilo más compacto y debe migrar la estructura del proyecto al nuevo estilo de SDK de .NET Core.

En el explorador de soluciones, haga clic con el botón derecho en el proyecto Windows Forms y seleccione **descargar el proyecto**  >  **Editar**.

Ahora puede actualizar el archivo. csproj. Eliminará todo el contenido y lo reemplazará por el código siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Guarde y vuelva a cargar el proyecto. Ahora ha terminado de actualizar el archivo de proyecto y el proyecto tiene como destino .NET Core.

Si compila el proyecto en este momento, encontrará algunos errores relacionados con la referencia de cliente de WCF. Dado que este código se genera automáticamente, debe volver a generarlo para tener como destino .NET Core.

![Captura de pantalla de errores de compilación en Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

Elimine el archivo *Reference.CS* y genere un nuevo cliente de servicio.

Haga clic con el botón derecho en **servicios conectados** y seleccione la opción **Agregar servicio conectado** .

![Captura de pantalla del menú Servicios conectados con la opción Agregar servicio conectado seleccionada](./media/example-migration-core/add-connected-service.png)

Se abre la ventana Servicios conectados. Seleccione la opción **servicio Web WCF de Microsoft** .

![Captura de pantalla de la ventana de Servicios conectados](./media/example-migration-core/connected-services-window.png)

Si tiene el servicio WCF en la misma solución que en este ejemplo, puede seleccionar la opción **Discover** en lugar de especificar una dirección URL de servicio.

![Captura de pantalla de la ventana Configurar referencia de servicio Web WCF](./media/example-migration-core/configure-wcf-reference.png)

Una vez que se encuentra el servicio, la herramienta refleja el contrato de API implementado por el servicio. Cambie el nombre del espacio de nombres para que sea `eShopServiceReference` como se muestra en la siguiente imagen:

![Captura de pantalla del contrato de API y el espacio de nombres cambiado](./media/example-migration-core/api-contract-namespace.png)

Seleccione el botón **Finalizar** . Después de un tiempo, verá el código generado.

Debería ver tres archivos generados automáticamente:

1. *Introducción*: un vínculo a GitHub para proporcionar información sobre WCF.
2. *ConnectedService.jsen*: parámetros de configuración para conectarse al servicio.
3. *Reference.CS*: el código de cliente de WCF real.

![Captura de pantalla de la ventana de Explorador de soluciones con los tres archivos autogenerados](./media/example-migration-core/autogenerated-files.png)

Si vuelve a compilar, verá muchos errores procedentes de archivos *. CS* dentro de la carpeta *auxiliar* . Esta carpeta estaba presente en la versión .NET Framework pero no en el antiguo *. csproj*. Pero con el nuevo proyecto de estilo SDK, todos los archivos de código presentes bajo la ubicación del archivo de proyecto se incluyen de forma predeterminada. Es decir, el nuevo proyecto de .NET Core intenta compilar los archivos dentro de la carpeta *auxiliar* . Dado que esa carpeta no es necesaria, puede eliminarla de forma segura.

Si compila el proyecto de nuevo y lo ejecuta, no verá las imágenes del producto. El problema es que ahora la ruta de acceso a los archivos ha cambiado ligeramente. Para corregir este problema, debe agregar otro nivel de profundidad en la ruta de acceso y actualizar en el archivo `CatalogView.cs` la línea:

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

por

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

Después de este cambio, puede comprobar que la aplicación se inicia y se ejecuta según lo previsto en .NET Core.

## <a name="migrating-a-wpf-application"></a>Migración de una aplicación WPF

Usaremos la `Shop.ClassicWPF` aplicación de ejemplo para realizar la migración. En la imagen siguiente se muestra una captura de pantalla de la aplicación antes de la migración:

![Aplicación de ejemplo antes de la migración](./media/example-migration-core/app-before-migration.png)

Esta aplicación utiliza una base de datos de SQL Server Express local para almacenar la información del catálogo de productos. Se tiene acceso a esta base de datos directamente desde la aplicación WPF.

En primer lugar, debe actualizar el archivo *. csproj* al nuevo estilo de SDK que usan las aplicaciones de .net Core. Siga los mismos pasos descritos en la Windows Forms migración: descargará el proyecto, abrirá el archivo *. csproj* , actualizará su contenido y volverá a cargar el proyecto.

En este caso, elimine todo el contenido del archivo *. csproj* y reemplácelo por el código siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWpf>true</UseWpf>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Si vuelve a cargar el proyecto y lo compila, obtendrá el siguiente error:

![Captura de pantalla de errores de compilación en Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

Como ha eliminado todo el contenido de *. csproj* , ha perdido una especificación de referencia de proyecto presente en el proyecto anterior. Solo tiene que agregar esta línea al archivo *. csproj* para incluir la referencia de proyecto de nuevo:

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

También puede dejar que Visual Studio le ayude haciendo clic con el botón derecho en el nodo **dependencias** y seleccionando **Agregar referencia de proyecto**. Seleccione el proyecto de la solución y haga clic en **Aceptar**:

![Captura de pantalla del cuadro de diálogo Administrador de referencias con el proyecto eShop. SqlProvider seleccionado](./media/example-migration-core/reference-manager.png)

Una vez que se agrega la referencia de proyecto que falta, la aplicación se compila y se ejecuta según lo previsto en .NET Core.

>[!div class="step-by-step"]
>[Anterior](windows-migration.md)
>[Siguiente](deploy-modern-applications.md)
