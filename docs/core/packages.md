---
title: Paquetes, metapaquetes y marcos de trabajo
description: Paquetes, metapaquetes y marcos de trabajo
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 609b0845-49e7-4864-957b-21ffe1b93bf2
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2396b2794e88673afc1973b5bdd1e82c28fe5a13
ms.lasthandoff: 03/02/2017

---

# <a name="packages-metapackages-and-frameworks"></a>Paquetes, metapaquetes y marcos de trabajo

.NET Core es una plataforma conformada por paquetes NuGet. Algunas experiencias del producto se benefician de la definición específica de los paquetes, mientras que otras lo hacen de la definición general de las mismas. Para dar cabida a esta dualidad, el producto se distribuye como un conjunto específico de paquetes y, luego, se describe en fragmentos más generales con un tipo de paquete que recibe informalmente el nombre de "metapaquete".

Cada uno de los paquetes de .NET Core admite su ejecución en varios entornos de ejecución de .NET, que se representan como marcos de trabajo. Algunos de estos son marcos de trabajo tradicionales, como `net46`, que representa a .NET Framework. Otro conjunto son marcos de trabajo nuevos que se pueden considerar "marcos de trabajo basados en paquete", que establecen un modelo nuevo para definir los marcos de trabajo. Estos marcos de trabajo basados en paquete están completamente formadas y definidas como paquetes, lo que establece una fuerte relación entre los paquetes y los marcos de trabajo.

## <a name="packages"></a>Paquetes

.NET Core se divide en un conjunto de paquetes, que proporcionan primitivas, tipos de datos de nivel superior, tipos de composición de aplicaciones y utilidades comunes. Cada uno de estos paquetes representa un solo ensamblado con el mismo nombre. Por ejemplo, [System.Runtime](https://www.nuget.org/packages/System.Runtime) contiene System.Runtime.dll. 

Hay ventajas si los paquetes se definen de manera específica:

- Los paquetes específicos se pueden enviar según su propia programación con una prueba relativamente limitada de los otros paquetes.
- Los paquetes específicos pueden brindar compatibilidad con distintos SO y CPU.
- Los paquetes específicos pueden tener dependencias específicas solo para una biblioteca.
- Las aplicaciones son más pequeñas, porque los paquetes a los que no se hace referencia no forman parte de la distribución de aplicaciones.

Algunas de estas ventajas solo se usan bajo ciertas circunstancias. Por ejemplo, los paquetes de .NET Core normalmente se envían en la misma programación con la misma compatibilidad de plataforma. En el caso del mantenimiento, las correcciones se pueden distribuir e instalar como pequeñas actualizaciones de paquetes únicos. Debido al alcance limitado del cambio, la validación y el tiempo para que una corrección esté disponible están limitados a las necesidades de una biblioteca única.

A continuación se muestra una lista de los paquetes NuGet clave para .NET Core:

- [System.Runtime](https://www.nuget.org/packages/System.Runtime): el paquete más fundamental de .NET Core, que incluye [Object](http://docs.microsoft.com/dotnet/core/api/System.Object), [String](http://docs.microsoft.com/dotnet/core/api/System.String), [Array](http://docs.microsoft.com/dotnet/core/api/System.Array), [Action](http://docs.microsoft.com/dotnet/core/api/System.Action), además de [IList&lt;T&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1).
- [System.Collections](https://www.nuget.org/packages/System.Collections): un conjunto de colecciones genéricas (principalmente), que incluye [List&lt;T&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) y [Dictionary&lt;K,V&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2).
- [System.Net.Http](https://www.nuget.org/packages/System.Net.Http): un conjunto de tipos de comunicación de red HTTP, que incluye [HttpClient](http://docs.microsoft.com/dotnet/core/api/System.Net.Http.HttpClient) y [HttpResponseMessage](http://docs.microsoft.com/dotnet/core/api/System.Net.Http.HttpResponseMessage).
- [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem): un conjunto de tipos de lectura y escritura en un almacenamiento basado en disco local o en red, y que incluye [File](http://docs.microsoft.com/dotnet/core/api/System.IO.File) y [Directory](http://docs.microsoft.com/dotnet/core/api/System.IO.Directory).
- [System.Linq](https://www.nuget.org/packages/System.Linq): un conjunto de tipos para consultar objetos, que incluye Enumerable y [ILookup&lt;TKey, TElement&gt;](http://docs.microsoft.com/dotnet/core/api/System.Linq.ILookup-2).
- [System.Reflection](https://www.nuget.org/packages/System.Reflection): un conjunto de tipos para cargar, inspeccionar y activar tipos, que incluye [Assembly](http://docs.microsoft.com/dotnet/core/api/System.Reflection.Assembly), [TypeInfo](http://docs.microsoft.com/dotnet/core/api/System.Reflection.TypeInfo) y [MethodInfo](http://docs.microsoft.com/dotnet/core/api/System.Reflection.MethodInfo).

Se hace referencia a los paquetes en project.json. En el ejemplo siguiente, se hace referencia al paquete[System.Runtime](https://www.nuget.org/packages/System.Runtime/). 

```json
{
  "dependencies": {
    "System.Runtime": "4.1.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

En la mayoría de los casos, no se hará referencia directamente a los paquetes de .NET Core de nivel inferior, puesto que así terminará con demasiados paquetes que administrar. En lugar de eso, deberá hacer referencia a un metapaquete.

## <a name="metapackages"></a>Metapaquetes

Los metapaquetes son una conversión de paquetes NuGet que se usa para describir un conjunto de paquetes que tienen sentido juntos. Para representar este conjunto de paquetes, los transforman en dependencias. De manera opcional, pueden especificar un marco de trabajo a fin de establecer uno para este conjunto de paquetes. 

Si hace referencia a un metapaquete, en realidad agrega una referencia a cada uno de sus paquetes dependientes como gesto único. Esto significa que todas las bibliotecas existentes en esos paquetes (refs o libs) están disponibles para IntelliSense (o una experiencia similar) y para publicar la aplicación (solo libs). 

Nota: Los términos 'lib" y "ref" se refieren a las carpetas que se encuentran en los paquetes NuGet. Las carpetas "ref" describen la API pública de un paquete a través de metadatos de ensamblado. Las carpetas "lib" contienen la implementación de esa API pública para un marco de trabajo determinado. 

Usar metapaquetes tiene ventajas:

- Proporciona una experiencia del usuario adecuada para hacer referencia a un gran conjunto de paquetes específicos. 
- Define un conjunto de paquetes (incluidas las versiones específicas) que se prueban y trabajan correctamente en conjunto.

El metapaquete de la Biblioteca estándar de .NET:

- [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library): describe las bibliotecas que forman parte de la "Biblioteca estándar de .NET". Se aplica a todas las implementaciones .NET (por ejemplo, .NET Framework, .NET Core y Mono) que admite la Biblioteca estándar de .NET. Establece el marco de trabajo "netstandard".

Los siguientes son los metapaquetes clave de .NET Core:

- [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App): describe las bibliotecas que forman parte de la distribución de .NET Core. Establece el [`.NETCoreApp`marco de trabajo](https://github.com/dotnet/core-setup/blob/master/pkg/projects/Microsoft.NETCore.App/Microsoft.NETCore.App.pkgproj). Depende del `NETStandard.Library` más pequeño.
- [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility): un conjunto de fachadas de compatibilidad que permite que las Bibliotecas de clases portables (PCL) basadas en mscorlib se ejecuten en .NET Core.

Se hace referencia a los metapaquetes del mismo modo que con cualquier paquete NuGet en project.json. 

En el ejemplo siguiente, se hace referencia al metapaquete `NETStandard.Library`, que se usa para crear bibliotecas portátiles entre los entornos de ejecución .NET.

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

En el ejemplo siguiente, se hace referencia al metapaquete `Microsoft.NETCore.App`, que se usa para crear aplicaciones y bibliotecas pensadas para ejecutarse en .NET Core y aprovecharlo al máximo. Proporciona acceso a un conjunto de bibliotecas más grande que proporciona `NETStandard.Library`.

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  },
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

## <a name="frameworks"></a>Marcos de trabajo

Cada uno de los paquetes de .NET Core admite un conjunto de marcos de trabajo, declarados con carpetas de marcos (dentro de las carpetas lib y ref que se mencionaron anteriormente). Los marcos de trabajo describen un conjunto de API disponible (y posiblemente también otras características) en que puede basarse cuando tiene como destino un marco de trabajo determinado. Se crean versiones suyas cada vez que se agregan API nuevas.

Por ejemplo, [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem) admite los siguientes marcos de trabajo:

- .NETFramework,Version=4.6
- .NETStandard,Version=1.3
- 6 plataformas Xamarin (por ejemplo, xamarinios10)

Es útil contrastar los dos primeros de estos marcos de trabajo, debido a que son ejemplos de las dos formas distintas en que se definen los marcos de trabajo.

El marco de trabajo `.NETFramework,Version=4.6` representa las API disponibles en .NET Framework 4.6. Puede generar bibliotecas compiladas con los ensamblados de referencia de .NET Framework 4.6 y, luego, distribuir esas bibliotecas en paquetes NuGet en una carpeta net46 lib. Se usará para las aplicaciones que tienen como destino .NET Framework 4.6 o que son compatibles con esa plataforma. Esta es la forma de trabajar tradicional de todos los marcos de trabajo.

El marco de trabajo `.NETStandard,Version=1.3` está basado en paquete. Se basa en paquetes que tienen como destino el marco de trabajo para definir y exponer las API en términos del marco de trabajo.

## <a name="package-based-frameworks"></a>Marcos de trabajo basadas en paquete

Existe una relación recíproca entre los marcos de trabajo y los paquetes. La primera parte es definir las API disponibles para un marco de trabajo determinado, por ejemplo, `netstandard1.3`. Los paquetes que tienen como destino `netstandard1.3` (o marcos de trabajo compatibles, como `netstandard1.0`) definen las API disponibles para `netstandard1.3`. Esto puede parecer una definición circular, pero no lo es. En virtud de estar "basada en paquete", la definición de API del marco de trabajo proviene de los paquetes. El marco de trabajo mismo no define a ninguna API.

La segunda parte de la relación es la selección de recursos. Los paquetes pueden incluir recursos para varios marcos de trabajo. Dada una referencia a un conjunto de paquetes o metapaquetes, el marco de trabajo es necesario para determinar el recurso que se debe seleccionar, por ejemplo `net46` o `netstandard1.3`. Es importante seleccionar el recurso correcto. Por ejemplo, es poco probable que un recurso de `net46` sea compatible con .NET Framework 4.0 o .NET Core 1.0.

![Composición del marco de trabajo basado en paquete](./media/packages/package-framework.png)

Puede ver esta relación en la imagen anterior. La *API* tiene como destino el *marco de trabajo* y lo define. El *marco de trabajo* se usa para la *selección de recursos*. El *recurso* le brinda la API.

Una pregunta interesante es dónde finaliza la definición de un marco de trabajo basado en paquete y dónde comienza el consumo de esa definición. La vista del marco de trabajo se puede considerar como una función de un archivo project.json determinado. Las dependencias crean la vista del marco de trabajo, independiente de los publicadores de esas dependencias.

Los dos principales marcos de trabajo basados en paquete que se usan con .NET Core son los siguientes:

- `netstandard`
- `netcoreapp`

### <a name="net-standard"></a>Estándar .NET

El marco de trabajo del estándar .NET (TFM: `netstandard`) representa las API definidas por la [Biblioteca estándar de .NET](../standard/library.md) y que se basan en ella. Las bibliotecas diseñadas para ejecutarse en varios entornos de ejecución deben tener como destino este marco de trabajo. Se admitirán en cualquier entorno de ejecución compatible con el estándar .NET, como .NET Core, .NET Framework y Mono/Xamarin. Cada uno de estos entornos de ejecución admite un conjunto de versiones del estándar .NET, en función de las API que implementan. 

El metapaquete `NETStandard.Library` tiene como destino el marco de trabajo `netstandard`. La manera más común de establecer como destino `netstandard` consiste en hacer referencia a este metapaquete. Describe y proporciona acceso a las aproximadamente&40; bibliotecas de .NET y las API asociadas que definen la Biblioteca estándar de .NET. Puede hacer referencia a paquetes adicionales que tienen como destino `netstandard` para obtener acceso a otras API.

Una [versión de NETStandard.Library](versions/index.md) coincide con la versión más alta de `netstandard` que se expuso (a través de su clausura). La referencia de marco de trabajo en project.json se usa para seleccionar los recursos correctos en los paquetes subyacentes. En este caso, se requieren los recursos de `netstandard1.6`, en contraposición a `netstandard1.4` o `net46`, por ejemplo. 

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

No es necesario que las referencias de marco de trabajo y metapaquete de project.json coincidan. Por ejemplo, el siguiente archivo project.son es válido.

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.3": {}
  }
}
```

Puede parecer extraño establecer `netstandard1.3` como destino pero usa la versión 1.6.0 de `NETStandard.Library`. Se trata de un caso de uso válido, debido a que el metapaquete mantiene la compatibilidad con versiones anteriores de `netstandard`. Podría ser el caso que estandarizó en la versión 1.6.0 del metapaquete y úselo para todas las bibliotecas, que establecen como destino distintas versiones de `netstandard`. Con este enfoque, solo necesita restaurar `NETStandard.Library` 1.6.0 y no las versiones anteriores. 

Lo contrario no sería válido: establecer `netstandard1.6` como destino con la versión 1.3.0 de `NETStandard.Library`. No puede establecer como destino un marco de trabajo superior con un metapaquete inferior, debido a que el metapaquete de una versión inferior no expondrá ningún recurso para ese marco de trabajo superior. El [esquema de control de versiones] para los metapaquetes afirma que los metapaquetes coinciden con la versión superior del marco de trabajo que describen. En virtud del esquema de control de versiones, la primera versión de `NETStandard.Library` es v1.6.0, siempre que contenga recursos de `netstandard1.6`. La versión v1.3.0 se usa en el ejemplo anterior, para lograr una simetría con el ejemplo anterior, pero no existe realmente.

### <a name="net-core-application"></a>Aplicación .NET Core

El marco de trabajo de la aplicación .NET Core (TFM: `netcoreapp`) representa los paquetes y las API asociadas que se incluyen en la distribución de .NET Core y el modelo de aplicación de consola que proporciona. Las aplicaciones .NET Core deben usar este marco de trabajo, debido a que intentan establecer el modelo de aplicación de consola como destino, al igual que las bibliotecas que se pretende ejecutar solo en .NET Core. Usar este marco de trabajo restringe a las aplicaciones y bibliotecas solo a su ejecución en .NET Core. 

El metapaquete `Microsoft.NETCore.App` tiene como destino el marco de trabajo `netcoreapp`. Proporciona acceso aproximadamente a&60; bibliotecas, de las cuales el paquete `NETStandard.Library` proporciona unas&40;, además de otras&20;. Puede hacer referencia a bibliotecas adicionales que establecen como destino a `netcoreapp` o marcos de trabajo compatibles, como `netstandard`, para obtener acceso a API adicionales. 

La mayoría de las bibliotecas adicionales que `Microsoft.NETCore.App` proporciona también establecen como destino a `netstandard`, dado que otras bibliotecas `netstandard` satisfacen sus dependencias. Esto significa que las bibliotecas `netstandard` también pueden hacer referencia a esos paquetes como dependencias. 
