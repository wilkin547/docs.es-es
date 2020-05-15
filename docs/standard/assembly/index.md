---
title: Ensamblados de .NET
description: Los ensamblados son las unidades fundamentales de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad para las aplicaciones basadas en .NET.
ms.date: 08/15/2019
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.openlocfilehash: 87030bf9770c464709559b2fb8f4c0004009e48d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379912"
---
# <a name="assemblies-in-net"></a>Ensamblados de .NET

Los ensamblados componen las unidades fundamentales de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad para las aplicaciones basadas en .NET. Un ensamblado es una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad. Los ensamblados adoptan la forma de un archivo ejecutable ( *.exe*) o de biblioteca de vínculos dinámicos ( *.dll*), y son los bloques de creación de las aplicaciones .NET. Proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos.

En .NET Core y .NET Framework, puede crear un ensamblado a partir de uno o varios archivos de código fuente. En .NET Framework, los ensamblados pueden contener uno o varios módulos. Esto permite que los proyectos más grandes se planeen para que varios desarrolladores individuales puedan trabajar en archivos de código fuente o módulos independientes, que se combinan para crear un ensamblado único. Para más información sobre los módulos, vea el tema [Procedimiento para compilar un ensamblado de varios archivos](../../framework/app-domains/build-multifile-assembly.md).

Los ensamblados tienen las propiedades siguientes:

- Los ensamblados se implementan como archivos *.exe* o *.dll*.

- Para las bibliotecas destinadas a .NET Framework, puede compartir los ensamblados entre aplicaciones si los coloca en la [caché global de ensamblados (GAC)](../../framework/app-domains/gac.md). Debe asignar nombres seguros a los ensamblados antes de poder incluirlos en la GAC. Para obtener más información, vea [Ensamblados con nombre seguro](strong-named.md).

- Los ensamblados solo se cargan en memoria si son necesarios. Si no se usan, no se cargan. Esto significa que los ensamblados pueden ser una manera eficaz de administrar recursos en proyectos más grandes.

- Mediante programación, puede obtener información sobre un ensamblado mediante reflexión. Para más información, vea [Reflexión (C#)](../../csharp/programming-guide/concepts/reflection.md) o [Reflexión (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- Puede cargar un ensamblado solo para inspeccionarlo mediante la clase <xref:System.Reflection.MetadataLoadContext> en .NET Core y los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> en .NET Core y .NET Framework.

## <a name="assemblies-in-the-common-language-runtime"></a>Ensamblados en Common Language Runtime

Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.

Un ensamblado define la información siguiente:

- El código que ejecuta Common Language Runtime. Tenga en cuenta que cada ensamblado solo puede tener un punto de entrada: `DllMain`, `WinMain` o `Main`.

- Límite de seguridad. Un ensamblado es la unidad en la que se solicitan y conceden los permisos. Para obtener más información sobre los límites de seguridad en los ensamblados, vea [Consideraciones de seguridad sobre ensamblados](security-considerations.md).

- Límite de tipos. La identidad de cada tipo incluye el nombre del ensamblado en que reside. Por ello, un tipo `MyType` cargado en el ámbito de un ensamblado no es igual que un tipo denominado `MyType` cargado en el ámbito de otro ensamblado.

- Límite del ámbito de referencia. El [manifiesto del ensamblado](#assembly-manifest) contiene los metadatos que se usan para resolver tipos y satisfacer solicitudes de recursos. En el manifiesto se especifican los tipos y recursos que se exponen fuera del ensamblado y se enumeran otros ensamblados de los que depende. El código del lenguaje intermedio de Microsoft (MSIL) de un archivo ejecutable portable (PE) no se ejecutará a menos que tenga un [manifiesto del ensamblado](#assembly-manifest) asociado.

- Límite de versión. El ensamblado es la unidad versionable más pequeña de Common Language Runtime. Todos los tipos y recursos del mismo ensamblado tienen la misma versión, como una unidad. El [manifiesto del ensamblado](#assembly-manifest) describe las dependencias de versión que especifique para los ensamblados dependientes. Para obtener más información sobre el control de versiones, vea [Versiones de los ensamblados](versioning.md).

- Unidad de implementación. Cuando se inicia una aplicación, sólo deben estar presentes los ensamblados a los que llama la aplicación inicialmente. Los demás ensamblados, como los que contengan recursos de localización o clases de utilidad, se pueden recuperar a petición. Esto permite que las aplicaciones sean sencillas y ligeras la primera vez que se descargan. Para obtener más información sobre cómo implementar ensamblados, vea [Implementación de aplicaciones](../../framework/deployment/index.md).

- Unidad de ejecución en paralelo. Para obtener más información sobre la ejecución de varias versiones de un ensamblado, vea [Ensamblados y ejecución en paralelo](side-by-side-execution.md).

## <a name="create-an-assembly"></a>Creación de un ensamblado

Los ensamblados pueden ser estáticos o dinámicos. Los ensamblados estáticos se almacenan en el disco, en archivos ejecutables portables PE. Los ensamblados estáticos pueden incluir interfaces, clases y recursos como mapas de bits, archivos JPEG y otros archivos de recursos. También puede crear ensamblados dinámicos, que se ejecutan directamente desde la memoria y no se guardan en el disco antes de su ejecución. Los ensamblados dinámicos se pueden guardar en el disco una vez que se hayan ejecutado.

Existen varias formas de crear ensamblados. Puede usar herramientas de desarrollo, como Visual Studio, que permite crear archivos *.dll* o *.exe*. Puede usar las herramientas de Windows SDK para crear ensamblados con módulos de otros entornos de programación. También puede utilizar las API de Common Language Runtime, como <xref:System.Reflection.Emit?displayProperty=nameWithType>, para crear ensamblados dinámicos.

Para compilar ensamblados puede hacerlo en Visual Studio, con las herramientas de la interfaz de la línea de comandos de .NET Core o, para los ensamblados de .NET Framework, con un compilador de línea de comandos. Para más información sobre cómo compilar los ensamblados con la CLI de .NET Core, consulte [Información general sobre la CLI de .NET Core](../../core/tools/index.md). Para compilar ensamblados con los compiladores de línea de comandos, vea [Compilar la línea de comandos con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) para C#, o bien [Compilar desde la línea de comandos (Visual Basic)](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) para Visual Basic.

> [!NOTE]
> Para compilar un ensamblado en Visual Studio, seleccione **Compilar** en el menú **Compilar**.

## <a name="assembly-manifest"></a>Manifiesto del ensamblado

Todos los ensamblados tienen un archivo de *manifiesto del ensamblado*. De forma similar a una tabla de contenido, el manifiesto del ensamblado contiene lo siguiente:

- La identidad del ensamblado (su nombre y versión).

- Una tabla de archivos en la que se describen todos los demás archivos que componen el ensamblado, como otros ensamblados que haya creado y en los que se basa el archivo *.exe* o *.dll*, archivos de mapa de bits o Léame.

- Una *lista de referencias de ensamblado*, que es una lista de todas las dependencias externas, como archivos *.dll* o de otro tipo. Las referencias de ensamblado contienen referencias a objetos globales y privados. Los objetos globales están disponibles para todas las demás aplicaciones. En .NET Core, los objetos globales están acoplados con un runtime de .NET Core determinado. En .NET Framework, los objetos globales residen en la caché global de ensamblados (GAC). *System.IO.dll* es un ejemplo de un ensamblado en la GAC. Los objetos privados deben estar en un directorio del mismo nivel o debajo del directorio en el que se instala la aplicación.

Como los ensamblados contienen información sobre contenido, control de versiones y dependencias, las aplicaciones que los usan no confían en orígenes externos, como el Registro de los sistemas Windows, para funcionar correctamente. Los ensamblados reducen los conflictos de *.dll* y hacen que las aplicaciones sean más confiables y fáciles de implementar. En muchos casos, puede instalar una aplicación basada en .NET con tan solo copiar sus archivos en el equipo de destino. Para obtener más información, vea [Manifiesto del ensamblado](manifest.md).

## <a name="add-a-reference-to-an-assembly"></a>Incorporación de una referencia a un ensamblado

Para usar un ensamblado en una aplicación, debe agregar una referencia a él. Una vez que se hace referencia a un ensamblado, todos los tipos accesibles, propiedades, métodos y otros miembros de sus espacios de nombres están disponibles para la aplicación como si su código formara parte del archivo de origen.

> [!NOTE]
> La referencia a la mayoría de los ensamblados de la biblioteca de clases de .NET se hace automáticamente. Si no se hace referencia a un ensamblado del sistema de forma automática, para .NET Core puede agregar una referencia al paquete NuGet que contiene el ensamblado. Use el administrador de paquetes NuGet de Visual Studio, o bien agregue un elemento [\<PackageReference>](../../core/tools/dependencies.md#the-packagereference-element) para el ensamblado al proyecto *.csproj* o *.vbproj*. En .NET Framework, puede agregar una referencia al ensamblado mediante el cuadro de diálogo **Agregar referencia** de Visual Studio o mediante la opción de la línea de comandos `-reference` para los compiladores de [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) o [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md).

En C#, puede usar dos versiones del mismo ensamblado en una misma aplicación. Para obtener más información, vea [alias externo](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="related-content"></a>Contenido relacionado

|Title|Descripción|
|-----------|-----------------|
|[Contenido de los ensamblados](contents.md)|Elementos que componen un ensamblado.|
|[Manifiesto del ensamblado](manifest.md)|Datos del manifiesto del ensamblado y cómo se almacenan en los ensamblados.|
|[Caché global de ensamblados](../../framework/app-domains/gac.md)|Cómo almacena y usa los ensamblados la GAC.|
|[Ensamblados con nombre seguro](strong-named.md)|Características de los ensamblados con nombre seguro.|
|[Consideraciones de seguridad sobre ensamblados](security-considerations.md)|Cómo funciona la seguridad de los ensamblados.|
|[Control de versiones de los ensamblados](versioning.md)|Información general sobre la directiva de control de versiones de .NET Framework.|
|[Colocación de ensamblados](../../framework/app-domains/assembly-placement.md)|Dónde ubicar los ensamblados.|
|[Ensamblados y ejecución en paralelo](side-by-side-execution.md)|Uso de varias versiones del runtime o de un ensamblado simultáneamente.|
|[Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Cómo crear ensamblados dinámicos.|
|[Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|Cómo resuelve .NET Framework las referencias de ensamblado en tiempo de ejecución.|

## <a name="reference"></a>Referencia

<xref:System.Reflection.Assembly?displayProperty=nameWithType>

## <a name="see-also"></a>Vea también

- [Formato de archivo de ensamblado .NET](file-format.md)
- [Ensamblados de confianza](friend.md)
- [Ensamblados de referencia](reference-assemblies.md)
- [Cómo: para cargar y descargar ensamblados](load-unload.md)
- [Cómo: para usar y depurar la descargabilidad de ensamblados en .NET Core](unloadability.md)
- [Cómo: para determinar si un archivo es un ensamblado](identify.md)
- [Cómo: Inspect assembly contents using MetadataLoadContext](inspect-contents-using-metadataloadcontext.md) (Procedimiento para inspeccionar el contenido de un ensamblado con MetadataLoadContext)
