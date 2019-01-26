---
title: Habilitar o deshabilitar las redirecciones de enlace generado automáticamente
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: f646445d5fa4556646700bb5daf8ac859631da2c
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083670"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Procedimiento Habilitar y deshabilitar la redirección de enlace automática

Al compilar aplicaciones en Visual Studio que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores, redirecciones de enlace se pueden agregar automáticamente al archivo de configuración de la aplicación para invalidar la unificación de ensamblados. Las redirecciones de enlace se agregan si la aplicación o sus componentes hacen referencia a más de una versión del mismo ensamblado, incluso si se especifican manualmente las redirecciones de enlace en el archivo de configuración de la aplicación. La característica de redirección de enlace automática afecta a las aplicaciones de escritorio y aplicaciones web que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] o una versión posterior, aunque el comportamiento es ligeramente diferente para una aplicación web. Puede habilitar la redirección de enlace automática si tiene aplicaciones existentes destinadas a versiones anteriores de .NET Framework o puede deshabilitar esta característica si desea crear manualmente las redirecciones de enlace.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Deshabilitar las redirecciones de enlace automáticas en aplicaciones de escritorio

Redirecciones de enlace automáticas están habilitadas de forma predeterminada para las aplicaciones de escritorio de Windows que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores. Las redirecciones de enlace se agregan a la configuración de salida (**app.config**) cuando se compila la aplicación de archivo y anular la unificación de ensamblados que en caso contrario, es posible que tienen lugar. El origen **app.config** no se modifica el archivo. Puede deshabilitar esta característica si modifica el archivo de proyecto para la aplicación o anulando la selección de una casilla en las propiedades del proyecto en Visual Studio.

### <a name="disable-through-project-properties"></a>Deshabilitar a través de las propiedades del proyecto

Si tiene Visual Studio 2017 versión 15.7 o posterior, puede deshabilitar fácilmente las redirecciones de enlace generado automáticamente en páginas de propiedades del proyecto.

1. Haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.

2. En el **aplicación** página, desactive la **generar automáticamente redirecciones de enlace** opción.

3. Presione **Ctrl**+**S** para guardar el cambio.

### <a name="disable-manually-in-the-project-file"></a>Deshabilitar manualmente en el archivo de proyecto

1. Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:

   - En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual. En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.
   - En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**. Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.

2. En el archivo de proyecto, busque la siguiente entrada de propiedad:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Cambie `true` a `false`:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Habilitar redirecciones de enlace automáticas manualmente

Puede habilitar las redirecciones de enlace automáticas en las aplicaciones existentes destinadas a versiones anteriores de .NET Framework, o en casos donde se le pide automáticamente que agregue una redirección. Si tiene como destino una versión más reciente de framework, pero no se le pide automáticamente que agregue una redirección, probablemente obtendrá resultados de compilación que le sugiere que reasignar los ensamblados.

1. Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:

   - En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual. En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.
   - En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**. Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.

2. Agregue el siguiente elemento en el primer grupo de propiedades de configuración (bajo la \<PropertyGroup > etiqueta):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   La siguiente muestra un ejemplo de archivo de proyecto con el elemento insertado:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. Compile la aplicación.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Habilitar las redirecciones de enlace automáticas en aplicaciones web

Las redirecciones de enlace automáticas se implementan de forma diferente para las aplicaciones web. Dado que la configuración de origen (**web.config**) archivo debe modificarse para las aplicaciones web, las redirecciones de enlace no se agregan automáticamente al archivo de configuración. Sin embargo, Visual Studio le notifica los conflictos de enlace, por lo que podrá agregar redirecciones de enlace para resolverlos. Dado que siempre se le pedirá que agregue redirecciones de enlace, no es necesario deshabilitar explícitamente esta característica para una aplicación web.

Para agregar redirecciones de enlace a un **web.config** archivo:

1. En Visual Studio, compile la aplicación y compruebe si hay advertencias de compilación.

   ![Advertencia de compilación para conflictos de referencia de ensamblado](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. Si hay conflictos de enlace de ensamblados, se mostrará una advertencia. Haga doble clic en la advertencia, o seleccione la advertencia y presione **ENTRAR**.

   Un cuadro de diálogo que le permite agregar automáticamente el enlace es necesario que se redirige al origen de **web.config** aparece el archivo.

   ![Cuadro de diálogo de permiso de redireccionamiento de enlace](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Vea también

- [\<bindingRedirect > elemento](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [Redirigir versiones de ensamblado](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
